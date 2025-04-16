      
# 📊 Distribution Visualization Dashboard

A simple web application built with [Streamlit](https://streamlit.io/) to visualize different probability distributions (Normal, Exponential, Uniform, Binomial) using histograms and density plots.

## ✨ Demo

*(**Инструкция:** Замените строку ниже, чтобы вставить GIF-демонстрацию вашего приложения. Сначала загрузите GIF-файл в ваш репозиторий, затем используйте синтаксис `![Описание GIF](имя_файла.gif)`)*

![App Demo Placeholder - Replace Me!](https://via.placeholder.com/600x300.png?text=App+Demo+GIF+Goes+Here)

## ✨ Features

*   Generates random data for four common probability distributions:
    *   Normal
    *   Exponential
    *   Uniform
    *   Binomial
*   Interactive interface using Streamlit to select the distribution to view.
*   Displays clear histograms using Matplotlib and Seaborn.
*   Includes Kernel Density Estimation (KDE) overlay for continuous distributions.
*   Shows basic data generation parameters in the sidebar.
*   Uses a fixed random seed (`142`) for reproducible results.

## 🚀 Setup and Run

Follow these steps to run the application locally:

### 1. Clone the Repository

```bash
git clone https://github.com/orangegreen212/Distributions.git
cd Distributions

    

IGNORE_WHEN_COPYING_START
Use code with caution.Markdown
IGNORE_WHEN_COPYING_END
2. Install Dependencies

Make sure you have Python 3 installed. Then install the required libraries using pip:

      
pip install streamlit numpy matplotlib seaborn

    

IGNORE_WHEN_COPYING_START
Use code with caution.Bash
IGNORE_WHEN_COPYING_END

(Note: pyngrok mentioned in some development environments is not required for running the Streamlit app locally.)
3. Run the Streamlit App

      
streamlit run app.py

    

IGNORE_WHEN_COPYING_START
Use code with caution.Bash
IGNORE_WHEN_COPYING_END

This command will start the Streamlit server and should automatically open the application in your default web browser.
⚙️ Default Generation Parameters

The data is generated with the following settings:

    Sample Size: 1000

    Normal: Mean (loc) = 0, Standard Deviation (scale) = 1

    Exponential: Scale (scale) = 1.0

    Uniform: Low (low) = -2, High (high) = 2

    Binomial: Number of Trials (n) = 10, Probability of Success (p) = 0.5

🛠️ Technologies Used

    Python 3

    Streamlit

    NumPy

    Matplotlib

    Seaborn

🐍 Code

The core logic for the Streamlit application is located in the app.py file.
