# 💻 Laptop Price Analysis and Prediction

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-green?logo=scikit-learn&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

A complete end-to-end machine learning project that analyzes laptop specifications and predicts laptop prices in **Euros (€)** using **Linear Regression**, **Ridge Regression**, and **Random Forest**. This project covers the full data science pipeline — from raw data cleaning to model evaluation and price prediction.

---

## 📌 Problem Statement

With hundreds of laptop models available across different brands and specifications, it can be difficult for buyers and sellers to determine a fair price. This project aims to:

- Identify which laptop specifications have the greatest impact on price
- Build a regression model that can accurately estimate a laptop's market price based on its features

---

## 🗂️ Project Structure

```
laptop-price-analysis-and-prediction/
│
├── data/
│   ├── laptop_data.csv              # Raw dataset
│   └── laptop_price_cleaned.csv     # Cleaned & feature-engineered dataset
│
├── notebooks/
│   ├── data_preprocessing.ipynb     # Data cleaning and feature engineering
│   ├── exploratory_analysis.ipynb   # EDA with visualizations
│   └── price_prediction_modeling.ipynb  # Model training and evaluation
│
├── README.md
└── requirements.txt
```

---

## 🔍 Dataset

The cleaned dataset (`laptop_price_cleaned.csv`) contains **1,303 laptop records** with **49 features** after preprocessing and one-hot encoding.

| Feature | Description |
|---|---|
| `Inches` | Screen size in inches |
| `Ram` | RAM in GB |
| `Weight` | Laptop weight in kg |
| `Price_euros` | Target variable — laptop price in Euros |
| `Has_SSD` | Binary flag — SSD present (1) or not (0) |
| `Has_HDD` | Binary flag — HDD present (1) or not (0) |
| `Screen_Width` | Horizontal screen resolution in pixels |
| `Screen_Height` | Vertical screen resolution in pixels |
| `Company_*` | One-hot encoded brand features (Acer, Apple, Dell, etc.) |
| `TypeName_*` | One-hot encoded laptop type (Notebook, Gaming, Ultrabook, etc.) |
| `OpSys_*` | One-hot encoded OS features (Windows 10, macOS, etc.) |
| `Cpu_Brand_*` | One-hot encoded CPU brand (Intel, AMD, Samsung) |
| `Gpu_Brand_*` | One-hot encoded GPU brand (Nvidia, Intel, AMD, ARM) |

**Price range:** €174 — €6,099

---

## 🚀 Workflow

```
Raw Data → Cleaning → Feature Engineering → Train/Test Split → Model Training → Evaluation → Prediction
```

1. **Data Preprocessing** — Clean noisy columns (e.g., RAM, Storage, Screen Resolution), extract numeric values, encode categorical features via one-hot encoding
2. **Exploratory Data Analysis** — Visualize price distributions, correlations, and feature impact
3. **Train/Test Split** — 80% training (1,042 samples) / 20% testing (261 samples), `random_state=42`
4. **Model Training** — Train Linear Regression, Ridge Regression, and Random Forest
5. **Model Evaluation** — Compare models using R², RMSE, and MAE
6. **Price Prediction** — Use the best model to predict prices for new configurations

---

## 🤖 Models Used

| Model | Description |
|---|---|
| Linear Regression | Baseline model; interprets feature coefficients |
| Ridge Regression | Regularized linear model (`alpha=1.0`); handles multicollinearity |
| Random Forest | Ensemble of 100 decision trees (`n_estimators=100`); handles non-linearity |

---

## 📈 Model Performance

| Model | R² Score | MAE (€) | RMSE (€) |
|---|---|---|---|
| Linear Regression | 0.7457 | 253.65 | 359.43 |
| Ridge Regression | 0.7425 | 253.34 | 361.63 |
| **Random Forest** | **0.7741** | **214.04** | **338.76** |

✅ **Best Model: Random Forest** — highest R² and lowest error metrics.

---

## 🔑 Top 15 Most Important Features (Random Forest)

| Feature | Importance |
|---|---|
| Ram | 0.5881 |
| Weight | 0.1224 |
| TypeName_Notebook | 0.0551 |
| Inches | 0.0318 |
| Screen_Width | 0.0234 |
| TypeName_Workstation | 0.0214 |
| Screen_Height | 0.0189 |
| OpSys_Windows 7 | 0.0176 |
| Has_SSD | 0.0158 |
| Company_Razer | 0.0157 |
| Company_HP | 0.0106 |
| Company_Lenovo | 0.0090 |
| Company_Asus | 0.0085 |
| Company_Dell | 0.0078 |
| TypeName_Ultrabook | 0.0077 |

**RAM** is by far the most significant predictor of laptop price (~59% importance).

---

## 🛠️ Tech Stack

- **Language:** Python 3.8+
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn (LinearRegression, Ridge, RandomForestRegressor)
- **Environment:** Jupyter Notebook

---

## ⚙️ Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/NikitaRakhade29/laptop-price-analysis-and-prediction.git
cd laptop-price-analysis-and-prediction
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the notebooks in the following order for best understanding:

1. `notebooks/data_preprocessing.ipynb`
2. `notebooks/exploratory_analysis.ipynb`
3. `notebooks/price_prediction_modeling.ipynb`

---

## 📦 Requirements

```
numpy
pandas
matplotlib
seaborn
scikit-learn
jupyter
```

Install all at once:

```bash
pip install -r requirements.txt
```

---

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

1. Fork the repository
2. Create a new branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 👩‍💻 Author

**Nikita Rakhade**

[![GitHub](https://img.shields.io/badge/GitHub-NikitaRakhade29-black?logo=github)](https://github.com/NikitaRakhade29)

---

⭐ If you found this project helpful, consider giving it a star!
