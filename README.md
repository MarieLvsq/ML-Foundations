# ML Foundations — Week 1 (The ML Skeleton)

## Deliverables (Week 1)
- ✅ Environment: macOS + Homebrew Python 3.11, project `.venv`
- ✅ Data: Titanic loaded + cleaned
- ✅ Split: train/test (80/20, stratified)
- ✅ Models: Logistic Regression, Decision Tree (max_depth=5), Random Forest (n_estimators=300)
- ✅ Metrics: Accuracy, Precision, Recall, F1 + confusion matrices
- ✅ Threshold: Logistic Regression @ **0.40** (Acc 0.810, Prec 0.740, Rec 0.783, F1 0.761)

## How to Run
```bash
# 1) Activate environment
cd ~/Documents/ml-foundations
source .venv/bin/activate

# 2) Launch Jupyter
jupyter lab
# open: Week1_ML_Basics.ipynb

Data Notes
	•	Source: seaborn.load_dataset("titanic")
	•	Cleaning:
	•	age → group median by (sex, pclass)
	•	embarked → mode
	•	fare → median
	•	Saved: data/titanic_clean.csv

Model Notes
	•	One-hot encoding via pd.get_dummies(drop_first=True) for Week 1 (simple baseline).
	•	Results prioritised by F1; threshold tuned for LogReg on validation-style pass; final metrics reported on test split.

Decision Log (Week 1)
	•	Winner: Logistic Regression (threshold = 0.40)
	•	CM @0.40: TN=91, FP=19, FN=15, TP=54
	•	Metrics @0.40: Acc 0.810, Prec 0.740, Rec 0.783, F1 0.761
	•	Rationale: Better recall/F1 with acceptable precision trade-off.

Next Week (Week 2 — Plan)
	•	Pipeline + GridSearch (LogReg): tune C, class_weight, scoring=f1, cv=5
	•	Compare with tuned Random Forest (max_depth, min_samples_*, max_features)
	•	Lock threshold using validation, confirm on test
	•	Add ROC/PR curves