# 📊 Data Documentation

## Wisconsin Breast Cancer Dataset

This project uses the **Wisconsin Breast Cancer Dataset** from scikit-learn.

### Dataset Overview

- **Total Samples**: 569
- **Training Samples**: 455 (80%)
- **Test Samples**: 114 (20%)
- **Total Features**: 30
- **Target Classes**: 2
  - **0 - Benign**: Non-cancerous tumors (357 samples)
  - **1 - Malignant**: Cancerous tumors (212 samples)

### Source

The original dataset is from:
- **Citation**: Dua, D. and Karra Taniskidou, E. (2017). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]
- **Dataset**: [Breast Cancer Wisconsin (Diagnostic)](https://archive.ics.uci.edu/ml/datasets/breast+cancer+wisconsin+(diagnostic))

### Features

All 30 features are computed from digitized images of fine needle aspirate (FNA) of breast mass.

#### Feature List:

1. **mean radius**
2. **mean texture**
3. **mean perimeter**
4. **mean area**
5. **mean smoothness**
6. **mean compactness**
7. **mean concavity**
8. **mean concave points**
9. **mean symmetry**
10. **mean fractal dimension**
11. **radius error** (standard error)
12. **texture error**
13. **perimeter error**
14. **area error**
15. **smoothness error**
16. **compactness error**
17. **concavity error**
18. **concave points error**
19. **symmetry error**
20. **fractal dimension error**
21. **worst radius**
22. **worst texture**
23. **worst perimeter**
24. **worst area**
25. **worst smoothness**
26. **worst compactness**
27. **worst concavity**
28. **worst concave points**
29. **worst symmetry**
30. **worst fractal dimension**

### Data Characteristics

- **No Missing Values**: Complete dataset with no missing values
- **Numerical Features**: All features are continuous numerical values
- **Standardization**: Features are standardized using StandardScaler before model training
- **Balanced Split**: Data is stratified during train-test split to maintain class distribution

### Class Distribution

```
Benign (0):    357 samples (62.7%)
Malignant (1): 212 samples (37.3%)
```

### Data Preprocessing

Before model training, the data undergoes:

1. **Loading**: Dataset loaded from `sklearn.datasets.load_breast_cancer()`
2. **Splitting**: 80% training, 20% testing (stratified)
3. **Standardization**: Features scaled to zero mean and unit variance using StandardScaler
4. **Cross-Validation**: 5-fold cross-validation for robust evaluation

### Usage in Code

```python
from sklearn.datasets import load_breast_cancer
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler

# Load dataset
cancer = load_breast_cancer()
X = cancer.data          # Features (569, 30)
y = cancer.target        # Labels (569,)

# Split data
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

# Standardize features
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

### Data Insights

- **Feature Range**: Features have different scales (typically 0-100+)
- **Feature Importance**: Some features are more predictive than others
- **Correlation**: Features show varying degrees of correlation
- **Linear Separability**: Data shows reasonable linear separability

### Statistics

**Mean Values** (across training set):
- Benign samples: Generally lower feature values
- Malignant samples: Generally higher feature values
- This difference allows classifiers to distinguish between classes

### References

- Original creators: Dr. William H. Wolberg, General Surgery Dept., University of Wisconsin
- Citation: Wolberg, W. H., Street, W. N., & Mangasarian, O. L. (1995). Machine Learning, 1(2), 141-160.
- Repository: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/)

---

**Note**: This dataset is automatically downloaded by scikit-learn. No manual download is required.
