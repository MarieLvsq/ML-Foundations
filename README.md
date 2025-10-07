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

## Next Weeks — PhD-Aligned ML Foundations Roadmap (Oct 6 – Nov 2 2025)

### Week 2 (Oct 13 – 19): Metrics and Evaluation
**Goal:** Develop solid evaluation literacy and model-comparison intuition.  
**Tasks:**
- Implement Confusion Matrix, ROC and AUC plots.
- Plot Precision–Recall curve; analyze class imbalance.
- Simulate bias–variance trade-off by varying sample sizes.
- Run GridSearchCV for hyperparameter tuning.
- Finalize evaluation notebook with charts and push.
- Read: Géron Chs 3–4; Brownlee (2021); Saito & Rehmsmeier (2015).
- Deliverables:  
  - `Week2_Model_Evaluation.ipynb`  
  - Research Journal Entry #2 (metric selection + interpretation)

---

### Week 3 (Oct 20 – 26): Feature Engineering and Pipelines
**Goal:** Build reproducible pipelines and feature-selection workflows.  
**Tasks:**
- Encode categorical features (OneHotEncoder, LabelEncoder).  
- Apply scaling (StandardScaler / MinMaxScaler).  
- Integrate into `Pipeline()` and test re-fit.  
- Add `GridSearchCV` inside pipeline and save best params.  
- Run feature selection (`SelectKBest` / RF importance).  
- Deliverables:  
  - `Week3_FeatureEngineering_Pipeline.ipynb`  
  - Feature importance chart + updated README on reproducibility.  
- Reading: Géron Chs 5–6 + Raschka (2022) blog on pipelines.

---

### Week 4 (Oct 27 – Nov 2): Mini-Project and Reflection
**Goal:** Apply all techniques to a real-world dataset and publish results.  
**Tasks:**
- Download Kaggle Bank Customer Churn dataset.  
- Perform EDA (correlations + distributions).  
- Build preprocessing pipeline (scaler + encoder).  
- Train LogReg, Random Forest, XGBoost.  
- Compare ROC/AUC and classification reports.  
- Write final README + visual summary.  
- Deliverables:  
  - `Churn_Prediction_Project.ipynb`  
  - Final README + LinkedIn summary post.

---

📘 **Readings & Reflections:**  
Each week ends with a research-journal note connecting the week’s readings (Géron, Brownlee, Raschka, Saito & Rehmsmeier, etc.) to your long-term PhD orientation — reproducibility, evaluation fairness, and transparent pipelines.