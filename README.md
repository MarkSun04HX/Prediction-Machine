# Easy-ML Documentation

## Overview
Easy-ML is a user-friendly machine learning library that provides easy-to-use implementations of popular algorithms. This documentation covers setup, file structure, CSV format requirements, per-model feature requirements, and evaluation metrics.

Open **`models.html`** in the project root to pick a model; each tool opens as its own page under **`models/`** (for example `models/XGBoost.html`).

Keep **`models.html`** next to the **`models/`** folder so links like `./models/XGBoost.html` resolve correctly. If you only copy files elsewhere, copy both `models.html` and the whole **`models/`** directory together.

If a preview blocks `file://`, run a local server from the project folder and open `http://localhost:8000/models.html`:

```bash
cd /path/to/Easy-ML && python3 -m http.server 8000
```

## Supported Models
1. **XGBoost**  
   XGBoost is an optimized gradient boosting approach designed for high performance on tabular data.

2. **Random Forest**  
   Random Forest builds many trees and aggregates predictions to improve robustness and reduce overfitting.

3. **Linear Regression**  
   A foundational model that fits a linear relationship between input features and a numeric target.

4. **Elastic Net**  
   Combines L1 and L2 regularization for stable linear modeling with correlated features.

5. **Decision Tree**  
   A tree-based model that recursively splits features into decision rules.

6. **Neural Networks**  
   Layer-based models for learning non-linear patterns from numerical feature vectors.

7. **CatBoost**  
   Gradient boosting with strong handling for tabular data and categorical features.

8. **SVMs**  
   Support Vector Machines that separate data with maximum-margin hyperplanes (or kernels).

9. **KNNs**  
   K-Nearest Neighbors predicts from the local neighborhood of similar samples.

10. **LightGBM**  
   LightGBM is a gradient boosting framework focused on high efficiency and strong performance for tabular data.

11. **Logistic Regression**  
   A linear probabilistic model commonly used for binary and multiclass classification.

12. **Naive Bayes**  
   A probabilistic classifier that is especially effective for high-dimensional, sparse-feature tasks.

## Setup Instructions
1. Clone the repository:
   ```
   git clone https://github.com/MarkSun04HX/Easy-ML.git
   ```
2. Install the required packages:
   ```
   pip install -r requirements.txt
   ```
3. Run your first model:
   ```
   python example.py
   ```

## File Structure
- `models.html` - Hub page that links to each standalone model tool.
- `models/` - One HTML file per model (CV & prediction UI for each).
- `source_code/` - Optional folder for Python/model source implementations and shared utilities.
- `data/` - Input CSV files.
- `requirements.txt` - Python dependencies.
- `example.py` - Example usage script.

## CSV Format Requirements
- CSV files must include a header row.
- Each row should represent one observation/sample.
- Missing values should be handled before training (or consistently represented).
- Train/test files used together must follow the same schema.

## Feature Type Requirements by Model
- **Linear Regression / Elastic Net / Neural Networks / SVMs / KNNs**: all input features must be numeric.
- **XGBoost / Random Forest / Decision Tree / CatBoost**: this project’s HTML tools currently expect numeric input values in CSVs. If categorical fields exist, encode them to numeric values first.
- **Target column (Y)**:
  - For current pages and metrics (RMSE), the target is treated as numeric.
  - If you run a classification task, encode class labels consistently and interpret RMSE with care.

## Practical Notes
- Scale-sensitive models (especially **SVMs**, **KNNs**, and **Neural Networks**) generally perform better when features are normalized/standardized.
- Keep feature columns in the same order between training and test files.
- Avoid mixing text and numeric values within the same column.

## Metrics Explanation
- **RMSE (Root Mean Square Error)**: primary metric used across current model pages; lower values indicate better fit for numeric targets.
- **Accuracy / Precision / Recall / F1**: classification metrics you may add or use in future extensions.

## Future Enhancements
- Add explicit preprocessing utilities (encoding, scaling, missing-value handling).
- Expand model-specific validation checks and warnings in each HTML page.
- Add additional metrics for classification workflows.

---
This documentation is designed to help you prepare data correctly and use Easy-ML model tools with fewer input-format issues.
