# Food-Safety Risk Triage, Chicago

*Team project · University of Adelaide · Oct–Nov 2026*

**Question:** With limited inspectors, which food businesses should be visited first?

**What we did** (lead analyst, team of 4)
- **I** led the cleaning and merging of 316K public inspection records with health and census data
- **I** built and compared machine-learning models that rank businesses by risk, tested on a year the models had never seen
- **We** turned the risk scores into a 2027 inspection plan and a Tableau dashboard for decision-makers

**Methods**
- **Data engineering:** cleaned 316,703 records with a logged rule for every removal, then merged inspection, health and census data by ZIP code and year
- **Inference:** OLS with socioeconomic controls and year effects; VIF checks, drop-one-control robustness and a within-area (fixed-effects) model
- **Machine learning:** 6 classifiers (logistic regression, decision tree, random forest, Naive Bayes, SVM, neural network) on a **time-based split** (train 2018–23, validate 2024, test 2025) to avoid leakage
- **Evaluation for a rare outcome:** recall and lift in the riskiest 20% instead of accuracy (82.5% accuracy just by predicting "no"), plus calibration of predicted totals
- **Interpretation:** odds ratios from logistic regression to explain the risk drivers

**Result:** The riskiest 20% of visits caught **32.4%** of serious violations (**1.62× lift**), and a risk-first schedule finds about **50% more** problems in the first month with the same inspectors.

**Tools:** Python (pandas, scikit-learn, statsmodels) · Tableau

📊 **[View the interactive dashboard on Tableau Public](https://public.tableau.com/app/profile/duy.nguyen8153/viz/tableau_bigdata/Dashboard)**

---
📂 **Full notes, code and results are available on request.** Message me on [LinkedIn](https://www.linkedin.com/in/duynguyen1908/) and I can share access to the private project repo.
