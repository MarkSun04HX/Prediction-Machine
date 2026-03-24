# Easy-ML Documentation

## Overview
Easy-ML is a user-friendly machine learning library that provides easy-to-use implementations of popular algorithms. This documentation covers setup, file structure, CSV format requirements, per-model feature requirements, and evaluation metrics.

There is **no hub page**. Open the **model file you want** in the models folder directly in your browser (double-click the file, or “Open with” your browser). Each model is a standalone HTML page in the project root, for example **`XGBoost.html`**, **`RandomForest.html`**, **`LinearRegression.html`**, and so on.

All model `.html` files can live in the same folder together; you only need the file for the model you are using. Copy that single file anywhere you like and it will still run on its own.

If a preview blocks `file://`, run a local server from the project folder and open the page by URL, for example `http://localhost:8000/XGBoost.html`:

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
- **Model tools (project root)** — one HTML file per model (each includes cross-validation and prediction UI):
  - `XGBoost.html`, `RandomForest.html`, `LinearRegression.html`, `ElasticNet.html`, `DecisionTree.html`, `NeuralNetworks.html`, `CatBoost.html`, `SVMs.html`, `KNNs.html`, `LightGBM.html`, `LogisticRegression.html`, `NaiveBayes.html`
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
