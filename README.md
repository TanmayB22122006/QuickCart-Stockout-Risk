# 🛒 QuickCart: Stockout Risk Predictor

A production-grade Supervised Machine Learning engine designed to predict inventory stockouts across dark stores, preventing supply chain inefficiencies and lost revenue.

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Data Manipulation & Cleaning:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (RandomForestClassifier)
* **Environment:** Jupyter Notebook / Google Colab

## 💡 Project Highlights & Architecture
Real-world inventory management isn't about perfect datasets; it involves complex relational architectures, data traps, and asymmetric business costs. This project processes daily inventory data for 60 SKUs across 12 QuickCart dark stores by joining 5 distinct relational tables to catch stockout risks classified into three operational tiers: **Safe**, **At-Risk**, and **Imminent**.

* **Mastering the Data Joins:** Engineered a consolidated modeling dataset from 5 raw dimension and fact tables (`stores`, `skus`, `suppliers`, `events`, `inventory`), maintaining strict relational integrity.
* **Bypassing the "Silent Pandas" Trap:** Safely parsed literal string `'N/A'` supplier reliability scores by explicitly defining `na_values` during the CSV load to prevent Pandas from improperly casting columns.
* **Preventing Data Leakage:** Implemented a strict chronological Train-Test Split (Training on days 1-23, Testing on days 24-30) rather than random splitting, ensuring the model generalizes accurately to unseen future dates.
* **Asymmetric Cost & Metric Focus:** In supply chain, missing a stockout (False Negative) is costlier than an early alert. The model focuses heavily on optimizing the **Recall score for the 'Imminent' class**, successfully capturing 65% of actual stockouts with 92% precision from highly imbalanced data (Imminent class was only 10.6% of the dataset).
* **Feature Engineering:** Derived critical business metrics like `reorder_gap` and `cover_ratio`, and dynamically imputed missing supplier data using category-wise medians.

## ⚙️ Step-by-Step Local Setup
Follow these instructions to set up and run the machine learning pipeline locally.

### Prerequisites
* Python 3.8+ installed on your machine.
* Jupyter Notebook or JupyterLab.

### Installation Steps

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/TanmayB22122006/QuickCart-Stockout-Risk.git
   cd QuickCart-Stockout-Risk

2) Install Required Libraries:
Make sure you have the required Python libraries installed:
*     pip install pandas numpy scikit-learn jupyter

3) Launch the Notebook:

4) Run the Analysis:

* Open QuickCart_Stockout_Risk.ipynb in the Jupyter interface.
* Ensure the 5 CSV datasets are in the same working directory.
* Run the cells sequentially to observe data loading, cleaning, temporal splitting, and final model evaluation.

* 👨‍💻 About the Author
* Tanmay Purushottam Bokade
* Computer Engineering Student @ VESIT | Tech, AI & Data Enthusiast
* Let's connect and build cool things!
* 💼 LinkedIn: linkedin.com/in/tanmay-bokade
* 🐙 GitHub: github.com/TanmayB22122006
