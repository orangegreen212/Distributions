# 📊 Distribution Visualization Dashboard

**A simple interactive web app built with [Streamlit](https://streamlit.io/)**  
🔬 Visualizes different **probability distributions** — Normal, Exponential, Uniform, and Binomial — using histograms and density plots.

---

## 🌐 Live Demo

<img src="https://github.com/orangegreen212/Distributions/blob/main/8%20day.gif?raw=true" width="700"/>

---

## ⚙️ Features

✅ Generates random data for **4 popular probability distributions**:
- **Normal (Gaussian)** — Bell-shaped, symmetric around the mean  
- **Exponential** — Models the time between events in a Poisson process  
- **Uniform** — All outcomes are equally likely  
- **Binomial** — Number of successes in a sequence of yes/no experiments  

✅ **Interactive Streamlit UI** — Select the distribution type from the sidebar  
✅ **Matplotlib & Seaborn plots** — Clean histograms with KDE overlays  
✅ **Sidebar parameters** — Easily adjust values for sample size, mean, std, etc.  
✅ **Reproducible results** — Random seed (`142`) ensures consistency  


## 🐍 Code Structure

The main logic is inside:

📄 [`distribution_4_diff.py`](distribution_4_diff.py)  
It includes:
- Distribution selection logic
- Parameter sliders in sidebar
- Plotting histograms with density curves
- Handling both continuous and discrete distributions

---

## 🧠 Learn More

📚 This project was built to explore statistical distributions visually

📈 Great for educational purposes or quick demos of probability theory in action.

## 🚀 Setup and Run

Follow these steps to run the application locally:

### 1. Clone the Repository

```bash
git clone https://github.com/orangegreen212/Distributions.git
cd Distributions

###  2. Install Dependencies

Make sure you have Python 3 installed. Then install the required libraries using pip:
      
pip install streamlit numpy matplotlib seaborn

###  3. Run the Streamlit App
      
streamlit run app.py

    

    
