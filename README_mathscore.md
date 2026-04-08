# Student Math Score Prediction

Prediksi nilai matematika siswa menggunakan pipeline regresi berbasis faktor demografis dan latar belakang pendidikan.

## Hasil Model

| Metric | Score |
|--------|-------|
| R² (test) | **0.8804** |
| MAE | **4.2148** |
| RMSE | **5.3940** |

Model mampu menjelaskan **88% variasi** nilai matematika hanya dari data demografi dan nilai mata pelajaran lain.

## Dataset

- 1.000 siswa, 8 kolom
- Source: [Students Performance in Exams](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams) (Kaggle)
- Fitur: gender, race/ethnicity, parental level of education, lunch, test preparation course, reading score, writing score
- Target: math score

## Workflow

```
1. Load Dataset
2. Exploratory Data Analysis (EDA)
   - Distribusi nilai matematika
   - Pengaruh jenis lunch terhadap nilai
   - Korelasi antar skor
3. Preprocessing
   - OneHotEncoder untuk 5 categorical features
   - ColumnTransformer + Pipeline
4. Model Training — Linear Regression
5. Evaluasi — R², MAE, RMSE
6. Visualisasi — Actual vs Predicted, Residual Distribution
```

## Kenapa Linear Regression?

Reading score dan writing score punya korelasi tinggi dengan math score, dan hubungannya cenderung linear — ini kondisi ideal untuk Linear Regression. Model sederhana ini ternyata sudah cukup kuat dengan R² 0.88, tidak perlu model yang lebih kompleks.

## Tools & Library

```
Python 3.10 (Google Colab)
pandas, numpy
scikit-learn (LinearRegression, Pipeline, ColumnTransformer, OneHotEncoder)
matplotlib
```

## Cara Menjalankan

1. Buka `student_math_score_prediction.ipynb` di [Google Colab](https://colab.research.google.com)
2. Upload `studentperformance.csv` ke panel folder kiri Colab
3. Run all cells: **Runtime → Run all**

## Struktur Repo

```
student-math-score-prediction/
├── student_math_score_prediction.ipynb  ← main notebook
├── studentperformance.csv               ← dataset
├── README.md                            ← dokumentasi ini
└── requirements.txt
```
