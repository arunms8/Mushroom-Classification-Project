# 🍄 Mushroom Edibility Classification

## Project Overview

This repository contains a machine learning project focused on classifying mushrooms as either edible or poisonous based on their physical characteristics. Using the UCI Machine Learning Repository's Secondary Mushroom dataset with 61,069 samples, we developed models that achieve up to 98.8% accuracy in distinguishing safe from dangerous mushrooms.

## 🔑 Key Features

- **Robust Preprocessing Pipeline**: Implemented data leakage prevention techniques including train/test splitting before preprocessing, feature scaling fitted only on training data, and outlier removal from training data only
- **Multiple Model Comparison**: Evaluated linear models (Logistic Regression) and tree-based ensemble methods (Random Forest, XGBoost)
- **Safety-Focused Metrics**: Prioritized minimizing the misclassification of poisonous mushrooms as edible
- **Feature Importance Analysis**: Identified key physical characteristics that best predict mushroom edibility
- **Deployment-Ready Code**: Includes model packaging and example code for production deployment

## 📊 Results

| Model | Accuracy | F1 (Poisonous) | F1 (Edible) | False Safe Rate* |
|-------|----------|---------------|-------------|-----------------|
| Random Forest | 98.81% | 0.986 | 0.989 | 2.63% |
| XGBoost | 98.67% | 0.985 | 0.988 | 2.96% |
| Logistic Regression (Balanced) | 62.78% | 0.603 | 0.650 | 36.61% |
| Logistic Regression | 62.33% | 0.517 | 0.691 | 54.71% |

*False Safe Rate: Percentage of poisonous mushrooms incorrectly classified as edible (lower is better)

## 🧪 Methodology

1. **Data Preparation**:
   - Removed sparse columns (>50% missing values)
   - Encoded categorical features 
   - Imputed missing values
   - Detected and removed outliers from training data only
   - Scaled numerical features

2. **Model Development**:
   - Trained baseline linear models and advanced tree-based ensembles
   - Used hyperparameter tuning via GridSearchCV for XGBoost
   - Applied threshold optimization for safety-critical performance
   - Validated with stratified 5-fold cross-validation

3. **Evaluation**:
   - Assessed models using accuracy, precision, recall, F1-score
   - Created ROC curves, precision-recall plots, and learning curves
   - Analyzed feature importance for model interpretability
   - Validated absence of data leakage through statistical tests

## 🔬 Key Insights

- Tree-based models dramatically outperformed linear models, demonstrating the non-linear nature of mushroom edibility classification
- Physical features like stem width, gill attachment, and cap surface emerged as the most important predictors
- Models achieved high confidence predictions with extremely stable performance across different threshold values
- Excellent performance was maintained even with reduced training data size

## 🛠️ Technologies Used

- **Python**: Primary programming language
- **Pandas/NumPy**: Data manipulation and analysis
- **Scikit-learn**: Machine learning framework for preprocessing and modeling
- **XGBoost**: Advanced gradient boosting implementation
- **Matplotlib/Seaborn**: Data visualization
- **Joblib**: Model serialization

## 💡 Applications

This project has practical applications in:
- Mushroom foraging safety tools
- Educational applications for mycology
- Field guide development
- Ecological research support

## 🚀 Getting Started

### Prerequisites
- Python 3.7+
- Required packages listed in requirements.txt

### Installation
```bash
git clone https://github.com/yourusername/mushroom-classification.git
cd mushroom-classification
pip install -r requirements.txt
```

### Usage
The repository includes Jupyter notebooks demonstrating:
1. Data preprocessing with data leakage prevention
2. Model training and evaluation
3. Prediction on new samples

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- UCI Machine Learning Repository for the Secondary Mushroom dataset
- The scientific community studying mycology and mushroom identification
