# MeridianHealth
Meridian Health's 30-Day Readmission Analysis

We were given patient data from Meridian Health, a for-profit hospital network, and asked to figure out why so many patients keep coming back within 30 days — and what to do about it. Every readmission hurts: it raises the hospital's readmission rate, triggers Medicare penalties up to 3%, and blocks beds for new patients.

The Data:

10,000 patient records covering everything from diagnosis and insurance type to whether a follow-up call was made after discharge. About 45% of patients were readmitted within 30 days — higher than it should be.

What We Found:

- Comorbidity count is the single strongest predictor of readmission. After that, it's Medicare insurance status and how many ER visits a patient had in the past year. Rural patients had the highest readmission rates across the board. Interestingly, race alone wasn't a major driver — but region and insurance access were.
- The interventions that actually helped: scheduling a follow-up appointment, completing medication reconciliation, and making a post-discharge call. Patients who got none of these came back at much higher rates.
The most overlooked group was medium-risk patients with no follow-up scheduled. Not the sickest people in the building — just the ones who slipped through the cracks after discharge.

What We Built:

- We ran EDA across every major variable, built a logistic regression model to predict 30-day readmission, and used K-Means clustering to segment patients into 5 risk tiers. We also engineered a comorbidity × social determinants interaction feature to capture compounding risk. The model hit 1,003 true negatives and 531 true positives.

What We Recommend:

Target Cluster 2 — medium risk, no follow-up, disproportionately rural. These patients are being missed because they don't look critical on paper. Send portal reminders, connect them with a PCP or specialist, and don't wait for them to show up in the ER again.

Tech Stack: 

Python Pandas Scikit-learn Seaborn Matplotlib Google Colab Gemini AI
