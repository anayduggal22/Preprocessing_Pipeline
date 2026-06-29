# 🔧 Data Preprocessing Pipelines — Scikit-learn

![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat-square&logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-Pipeline-F7931E?style=flat-square&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

> Building clean, reusable preprocessing pipelines using scikit-learn's `Pipeline` and `ColumnTransformer`.  
> Part of my Phase 6 Data Science Roadmap.

---

## 📌 What This Covers

- `SimpleImputer` for handling missing values
- `StandardScaler` for numeric feature scaling
- `OneHotEncoder` for categorical encoding
- `ColumnTransformer` to apply different pipelines to different columns
- Full end-to-end `Pipeline` with a RandomForest model
- Saving and loading pipelines with `joblib`

---

## 📁 Project Structure

```
preprocessing-pipelines/
├── Pipeline.ipynb           # Main notebook
├── titanic_pipeline.pkl     # Saved pipeline (gitignored)
├── train.csv                # Titanic training data (gitignored)
└── README.md
```

---

## 🔧 Pipeline Architecture

```
ColumnTransformer
├── num_pipeline → [SimpleImputer(median)] → [StandardScaler]
│   └── Age, Fare, FamilySize, SibSp, Parch, IsAlone
└── cat_pipeline → [SimpleImputer(most_frequent)] → [OneHotEncoder]
    └── Sex, Embarked, Title, Pclass
        ↓
RandomForestClassifier(n_estimators=100, max_depth=5)
```

---

## 📊 Results

| Metric | Score |
|---|---|
| Validation Accuracy | 0.8324 |
| CV Accuracy (5-fold) | 0.8305 ± 0.0188 |

---

## 🚀 How to Run

```bash
git clone https://github.com/anayduggal22/preprocessing-pipelines
cd preprocessing-pipelines
python -m venv venv
venv\Scripts\activate
pip install pandas numpy scikit-learn jupyter joblib
jupyter notebook Pipeline.ipynb
```

---

## 📦 Dependencies

```
pandas
numpy
scikit-learn
jupyter
joblib
```

---

## 👨‍💻 Author

**Anay Duggal**

---

⭐ If you found this project helpful, consider giving it a star!

