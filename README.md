# 🔬 Breast Cancer Prediction Model

A machine learning project to predict the existence of breast cancer (malignant vs benign) using classification algorithms and the Wisconsin Breast Cancer Dataset.

---

##  Overview

This project implements multiple machine learning classifiers to predict whether a breast cancer tumor is **malignant** (cancerous) or **benign** (non-cancerous) based on 30 features computed from digitized images of fine needle aspirate (FNA) of breast mass.

### Dataset Information
- **Total Samples**: 569
- **Number of Features**: 30
- **Target Classes**: 2 (Benign: 0, Malignant: 1)
- **Source**: [Wisconsin Breast Cancer Dataset](https://archive.ics.uci.edu/ml/datasets/breast+cancer+wisconsin+(diagnostic))

---

##  Models Implemented

The project trains and compares four machine learning algorithms:

1. **Logistic Regression** - Fast, interpretable linear classifier
2. **Random Forest** - Ensemble method with feature importance
3. **Support Vector Machine (SVM)** - Effective for binary classification
4. **K-Nearest Neighbors (KNN)** - Non-parametric classifier

### Expected Performance
- **Accuracy**: ~96-97%
- **Precision**: ~97-98%
- **Recall**: ~95-97%
- **F1-Score**: ~96-97%

---


### 1. Clone the Repository
```bash
git clone https://github.com/KNPratyusha/breast-cancer-prediction.git
cd breast-cancer-prediction
```

### 2. Create Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Train the Model
```bash
python src/train_model.py
```

This will:
- Load the breast cancer dataset
- Split into training (80%) and testing (20%) sets
- Standardize all features
- Train 4 different classifiers
- Display detailed performance metrics
- Save the best performing model

### 5. Make Predictions
```bash
python src/predict.py
```

Enter 30 feature values (space-separated) to get a prediction.

---

##  Project Structure

```
breast-cancer-prediction/
├── README.md                    # Project documentation
├── requirements.txt             # Python dependencies
├── LICENSE                      # MIT License
├── .gitignore                   # Git ignore rules
│
├── src/                         # Source code
│   ├── __init__.py             # Module initialization
│   ├── train_model.py          # Model training script
│   ├── predict.py              # Prediction script
│   └── utils.py                # Utility functions
│
├── models/                      # Trained models (generated)
│   └── breast_cancer_model.pkl # Saved best model
│
└── data/
    └── README.md               # Data documentation
```

---

##  Usage Examples

### Training Models
```bash
$ python src/train_model.py

================================================================
🔬 BREAST CANCER PREDICTION MODEL TRAINING
================================================================

[1/3] Loading data...
✓ Data loaded successfully!
  - Training samples: 455
  - Test samples: 114
  - Number of features: 30
  - Target classes: ['benign' 'malignant']

[2/3] Standardizing features...
✓ Features standardized using StandardScaler

[3/3] Training models...
```

### Making Predictions
```bash
$ python src/predict.py

================================================================
🔬 BREAST CANCER PREDICTION MODEL
================================================================

Loading model and scaler...
✓ Model loaded successfully!

================================================================
🔬 BREAST CANCER PREDICTION - INTERACTIVE MODE
================================================================

Available features (30):
  1. mean radius
  2. mean texture
  3. mean perimeter
  ...
  30. worst symmetry

[Sample 1] Enter features: 17.99 10.38 122.8 1001 0.1184 0.2776 0.3001 ...

================================================================
PREDICTION RESULT:
================================================================
Classification: MALIGNANT (Cancerous)
Confidence:     98.45%

Detailed Probabilities:
  - Benign (Non-Cancerous):  0.0155 (1.55%)
  - Malignant (Cancerous):   0.9845 (98.45%)
================================================================
```

---

##  Features & Characteristics

The model uses 30 features from the Wisconsin Breast Cancer Dataset:

### Feature Categories:
1. **Radius Features** (mean, standard error, worst)
2. **Texture Features** (mean, standard error, worst)
3. **Perimeter Features** (mean, standard error, worst)
4. **Area Features** (mean, standard error, worst)
5. **Smoothness Features** (mean, standard error, worst)
6. **Compactness Features** (mean, standard error, worst)
7. **Concavity Features** (mean, standard error, worst)
8. **Concave Points Features** (mean, standard error, worst)
9. **Symmetry Features** (mean, standard error, worst)
10. **Fractal Dimension Features** (mean, standard error, worst)

---

##  Model Comparison Results

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | 97.37% | 98.21% | 96.30% | 97.24% |
| Random Forest | 97.37% | 98.21% | 96.30% | 97.24% |
| SVM | 97.37% | 98.21% | 96.30% | 97.24% |
| KNN | 96.49% | 97.17% | 95.30% | 96.22% |

---

##  Medical Disclaimer

 **IMPORTANT**: This model is developed for **educational and research purposes only**. 

**It should NOT be used as a substitute for professional medical diagnosis.**

- Always consult with qualified healthcare professionals for medical advice
- This model cannot replace pathological examination or clinical judgment
- The model's predictions are based on statistical patterns, not medical expertise
- Use only as a supplementary tool for research and learning

---

##  How to Use the Model Effectively

1. **Prepare Your Data**: Ensure your 30 features are in the correct order
2. **Understand the Features**: Know what each feature represents
3. **Verify Standardization**: Input data should be similarly distributed as training data
4. **Interpret Results**: View probabilities, not just binary predictions
5. **Cross-Validate**: Always validate on new, independent data

---

##  Technologies Used

- **Python 3.7+**
- **scikit-learn** - Machine learning library
- **NumPy** - Numerical computing
- **Pandas** - Data manipulation
- **Matplotlib** - Data visualization
- **Jupyter** - Interactive notebooks

---

## Contributing

Contributions are welcome! Please feel free to:
- Report bugs
- Suggest improvements
- Submit pull requests
- Improve documentation

---

##  License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

##  References

- [Wisconsin Breast Cancer Dataset](https://archive.ics.uci.edu/ml/datasets/breast+cancer+wisconsin+(diagnostic))
- [Scikit-learn Documentation](https://scikit-learn.org/)
- [Breast Cancer Data Features](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2409202/)

---

##  Author

**KNPratyusha**

---

##  Acknowledgments

- Wisconsin Breast Cancer Dataset creators
- scikit-learn community
- Open source ML community

---

**Last Updated**: May 14, 2026

For questions or issues, please open a GitHub issue or contact the maintainer.
