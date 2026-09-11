# Predicting Student Burnout Risk Using Academic Behavior Logs: A Data Mining Approach 🧠📊

This repository contains the official code implementation and research framework for predicting academic burnout among university students. This project addresses a critical gap in educational data mining by designing a scalable, data-driven prior intervention system to detect psychological exhaustion using objective behavioral footprints rather than subjective surveys.

## 🔬 Research Overview & Affiliation
- **Authors:** Faria Ahmed Richi, Horish Das Priyo, Md Mostafijur Rahaman Bipul
- **Institution:** Department of Computer Science & Engineering, American International University-Bangladesh (AIUB)
- **Dataset:** Open University Learning Analytics Dataset (OULAD) — comprising 7 interlinked relational structures tracking demographics, virtual learning environment (VLE) clicks, and registration patterns.

## 🎯 The Innovation: Proxy-Based Labeling
Since "burnout" is inherently an unlabeled state in raw learning analytics data, this research established a rigorous behavioral deficit syndrome proxy framework to engineer binary targets (`burnout_risk = 1`):
1. **LMS Engagement Drop:** VLE interaction logs dropping below the lowest 25th percentile.
2. **Academic Disengagement:** Consistent pattern of missing or failing foundational assessments.
3. **Institutional Status:** Final course registration outcomes marked explicitly as "Withdrawn" or "Fail".

## 🚀 Advanced Feature Engineering
We extracted high-dimensional behavioral features mapping temporal engagement patterns:
- **Weekly VLE Click Counts:** Measuring active interaction and affordance access patterns over time.
- **Assessment Submission Gaps:** Quantifying the inter-submission intervals and delay margins relative to deadlines.
- **Grade Decline Trends:** Capturing dynamic velocity changes via the linear-fit slope average over sequential grades to isolate progressive performance decay.

## 📊 Experimental Results & Evaluation
To handle class imbalances safely without information leakage, SMOTE oversampling and stratified cross-validation were utilized. The engineered models yielded stellar classification metrics:

| Model | Accuracy | Precision | Recall | F1-score | ROC–AUC |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Logistic Regression** | **96.91%** | 0.99 | 0.94 | 0.97 | 0.99 |
| **Random Forest** | **96.79%** | 0.99 | 0.94 | 0.97 | 0.97 |
| **XGBoost** | **96.65%** | 0.98 | 0.95 | 0.97 | 0.97 |
| **Decision Tree** | **95.13%** | 0.95 | 0.96 | 0.95 | 0.95 |

### Key Takeaway:
While ensemble architectures (Random Forest, XGBoost) proved highly robust, Logistic Regression emerged as an exceptional, highly interpretable baseline with **96.91% test accuracy** and a **0.99 ROC-AUC**, proving the strong predictive capacity of the engineered behavioral features.

## 🗺️ Future Roadmap & Bridging Research Gaps
I am actively looking to expand and evolve this architecture in future research cycles by focusing on the following areas:
- **Cross-Dataset Validation:** Testing the model's generalizability by evaluating it against diverse, multi-institutional learning management system (LMS) data beyond the OULAD ecosystem.
- **Socio-Demographic Integration:** Bridging current data limitations by incorporating lifestyle variables, socio-economic contexts, and mental health metrics to create a holistic, multi-dimensional prediction pipeline.
- **Explainable AI (XAI):** Implementing SHAP (SHapley Additive exPlanations) and LIME to transform black-box tree models into transparent, interpretable diagnostic systems for university counselors.
- **Real-Time Analysis:** Transitioning the current batch architecture into a time-series framework to track the gradual, chronological progression of student burnout as it happens.

---
*This repository serves as an open framework for preemptive academic interventions, helping institutions safeguard student mental well-being before disengagement escalates to dropout.*
