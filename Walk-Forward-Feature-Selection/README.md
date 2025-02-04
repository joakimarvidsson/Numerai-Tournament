# Walk-Forward Feature Selection

This folder contains the implementation of **Walk-Forward Feature Selection** for the **Numerai Tournament**. The pipeline evaluates feature importance dynamically over time and selects stable, high-performing features for model training.

## 📂 Files
- **`Feature_Selection_Pipeline.ipynb`** - Jupyter Notebook containing the walk-forward feature selection process.
- **`feature_selection.json`** - JSON file storing the selected features across different methods.

## 🛠️ Usage

### 1️⃣ Clone the Repository
```sh
git clone https://github.com/YOUR_GITHUB_USERNAME/Numerai-Tournament.git
cd Numerai-Tournament/Walk-Forward-Feature-Selection
```

### 2️⃣ Load the Feature Selection Data in Python
```python
import json

with open("feature_selection.json", "r") as f:
    feature_data = json.load(f)

print(feature_data.keys())  # Available feature sets
```

### 3️⃣ Open and Run the Jupyter Notebook
```sh
jupyter notebook Feature_Selection_Pipeline.ipynb
```

## 📈 Methodology
The feature selection pipeline analyzes feature importance using multiple methods and then refines selections using **era-walk-forward analysis**:

1. **Cumulative Feature Importance** from **LightGBM** - Tracks the importance of each feature in the example LightGBM model.
2. **SHAP Values** - Estimates feature impact using SHAP (SHapley Additive exPlanations).
3. **Mean Decrease Accuracy (MDA)** - Measures feature importance by randomly permuting feature values and observing model performance changes.

### 🔍 Combining Feature Importance
The selected features can be aggregated using:
- **Union** (includes any feature selected by at least one method)
- **Intersection** (includes only features consistently selected by all methods)

Additionally, features are validated using an **era-walk-forward approach**, ensuring stability and predictive power over multiple time periods.

## ❓ Why Use Walk-Forward Feature Selection?
- Prevents **lookahead bias** by selecting features based on past performance while testing on future data.
- Helps avoid **overfitting** by ensuring selected features generalize well across eras.
- Uses **multiple feature importance methods** to create a robust selection.

## 📜 License
MIT License
