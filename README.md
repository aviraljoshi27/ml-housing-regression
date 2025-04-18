# ml-housing-regression

# 🏡 Real Estate Price Prediction using Linear Regression

## 📌 Overview

This project demonstrates the use of **Linear Regression** to predict real estate prices based on various property features. The workflow begins with a simple model using **only two features** and then scales up to include **all relevant features**, enabling a comparison of performance and interpretability.

---

## 📂 Dataset Used

**Filename**: `real_estate_dataset.csv`  
**Target Variable**: `Price`  
**Initial Features Used**:
- `Square_Feet`
- `Num_Floors`

**Full Feature Set** (after cleaning and preprocessing):
- `Square_Feet`
- `Num_Bedrooms`
- `Num_Bathrooms`
- `Num_Floors`
- `Year_Built`
- `Has_Garden`
- `Has_Pool`
- `Garage_Size`
- `Location_Score`
- `Distance_to_Center`

---

## 🔁 Project Workflow

### Step 1: 🧪 Baseline Model with Two Features
- A basic Linear Regression model is built using only `Square_Feet` and `Num_Floors`.
- This step helps build intuition and allows easy visualization (including a 3D scatter plot with a prediction surface).
- Performance is evaluated using **Mean Absolute Error (MAE)**.

### Step 2: 🔍 Data Cleaning
- **Dropped** columns with more than **50% null values**.
- **Dropped** categorical columns with:
  - **Low cardinality**: Very few unique values (e.g., binary flags that add no predictive power).
  - **High cardinality**: Mostly unique values like `ID` or `URL` that don’t generalize well.

### Step 3: 📈 Full Model with All Cleaned Features
- Re-trained the model using all relevant cleaned features listed above.
- Evaluated and compared against the two-feature model using MAE.

---

## 📊 Evaluation Metrics

- **Baseline Model (Two Features)**:
  - MAE gives an initial benchmark.
  - 3D visualization used to understand the prediction surface.

- **Full Feature Model**:
  - Lower MAE confirms improved prediction performance.
  - Model coefficients and intercepts are printed for interpretation.

---

## ⚠️ Data Leakage Awareness

Care is taken to avoid **data leakage**. For example, we don’t use features that would not be available before making a prediction (like final scores or future knowledge).

---

## 🧠 Key Learnings

- Simpler models are easier to interpret and visualize, making them good starting points.
- Adding relevant features can significantly improve model accuracy.
- Data cleaning — especially handling null values and cardinality — is critical before training.
- Always validate assumptions to avoid leakage and bias.

---

## 🛠️ Requirements

Install required libraries using:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn plotly
