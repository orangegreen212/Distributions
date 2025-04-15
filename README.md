# 📊 Distribution Visualization Dashboard

A simple web application built with Streamlit to visualize different probability distributions (Normal, Exponential, Uniform, Binomial) using histograms.

## ✨ Features

*   Generates random data for four common probability distributions.
*   Provides an interactive interface using Streamlit to select which distribution to view.
*   Displays histograms for the selected distribution using Matplotlib and Seaborn.
*   Includes Kernel Density Estimation (KDE) for continuous distributions.
*   Shows basic generation parameters in the sidebar.

## 🚀 Setup and Run

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/orangegreen212/Distributions
    cd Distributions
    ```

2.  **Install dependencies:**
    Make sure you have Python 3 installed. Then install the required libraries:
    ```bash
    pip install streamlit numpy matplotlib seaborn
    ```
    *(Note: `pyngrok` is used in the original Colab notebook for tunneling but is not strictly required for running the Streamlit app locally.)*

3.  **Run the Streamlit app:**
    ```bash
    streamlit run app.py
    ```
    This will automatically open the application in your default web browser.

## 🐍 Code (`app.py`)

Here is the Python code used for the Streamlit application:

```python
# -*- coding: utf-8 -*-
"""
Streamlit app to visualize different probability distributions.
"""
import streamlit as st
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Set the appearance of the plots
sns.set_style("whitegrid")

# Generate data
np.random.seed(142) # for reproducibility

# --- Function to Generate Data ---
def generate_distributions(size=1000):
    """Generates data for multiple distributions."""
    distributions = {
        "Normal": np.random.normal(loc=0, scale=1, size=size),
        "Exponential": np.random.exponential(scale=1.0, size=size),
        "Uniform": np.random.uniform(low=-2, high=2, size=size),
        "Binomial": np.random.binomial(n=10, p=0.5, size=size) # Discrete distribution
    }
    return distributions

# --- Color Mapping ---
color_map = {
    "Normal": "skyblue",
    "Exponential": "lightcoral",
    "Uniform": "mediumseagreen",
    "Binomial": "mediumpurple"
}

# --- Main Streamlit Interface ---
st.title("🎲 Distribution Dashboard")
st.write("Select a distribution to see its histogram.")

# Generate the data using the function
distributions_data = generate_distributions()

# Get the list of distribution names
distribution_names = list(distributions_data.keys())

# Create the radio button selection
selected_distribution = st.radio(
    "Select Distribution:",
    distribution_names
)

# --- Plotting ---
st.subheader(f"Histogram for: {selected_distribution}")

fig, ax = plt.subplots()

# Get the specific data array and color
data_to_plot = distributions_data[selected_distribution]
plot_color = color_map[selected_distribution]

# Decide whether to show KDE (Kernel Density Estimate)
# Don't show KDE for the discrete Binomial distribution
use_kde = selected_distribution != "Binomial"

# Plot the histogram using Seaborn
sns.histplot(
    data_to_plot,
    kde=use_kde,
    bins=30,
    ax=ax,
    color=plot_color
)

ax.set_title(f"Distribution: {selected_distribution}")
ax.set_xlabel("Value")
ax.set_ylabel("Frequency" if not use_kde else "Density") # Label changes based on KDE

# Display the plot in Streamlit
st.pyplot(fig)

# --- Optional: Display some info about generation ---
st.sidebar.header("Generation Info")
st.sidebar.markdown(f"""
*   **Sample Size:** 1000
*   **Normal:** Mean=0, StdDev=1
*   **Exponential:** Scale=1.0
*   **Uniform:** Low=-2, High=2
*   **Binomial:** Trials (n)=10, Probability (p)=0.5
*   *Random Seed:* 142
""")

https://4c54-35-221-191-251.ngrok-free.app/
