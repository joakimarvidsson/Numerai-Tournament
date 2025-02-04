# Walk-Forward Feature Selection

This folder contains the implementation of **Walk-Forward Feature Selection** for the **Numerai Tournament**. The method evaluates feature importance dynamically over eras using a walk-forward approach.

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
Walk-Forward Feature Selection ensures robust feature selection by:
1. **Training models over rolling windows** of past eras.
2. **Evaluating feature importance dynamically** to adapt to changing market conditions.
3. **Selecting a stable subset of features** that perform well across time.

## 🔍 Why Use Walk-Forward Feature Selection?
- Traditional feature selection methods often **overfit to historical data**.
- This approach ensures that **only stable and predictive features** are chosen for live trading.
- Helps **avoid lookahead bias** by testing features only on future data.

## 📜 License
MIT License

