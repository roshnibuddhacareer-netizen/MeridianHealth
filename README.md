# MeridianHealth

🏥 A Remedy for Readmission
A healthcare consulting case where we analyzed 10,000 patient records for Meridian Health to figure out why 45% of patients were coming back within 30 days, and built a data driven recommendation to fix it.

📋 Overview
Meridian Health is a for-profit hospital network struggling with high 30-day readmission rates. As part of a case competition, we stepped into the role of consultants. We dug into their patient data, figured out what was actually driving readmissions, and built a targeted intervention plan the hospital could realistically act on.

🛠️ Tools Used
Python, Pandas, Scikit-learn, Seaborn, Matplotlib, Jupyter Notebook, Gemini AI

💡 The Problem
Readmissions hurt everyone involved. Patients end up back in the hospital, Meridian takes a hit on Medicare reimbursement of up to 3%, and beds get tied up that could go to new patients. Across 10,000 patient records, 45.5% were readmitted within 30 days, which is well above where it should be. The hospital didn't have a clear way to tell which patients were actually at risk before it happened, so we had to build one.

🧩 What Is K-Means Clustering
K-Means is a way of letting the data sort itself into groups instead of us deciding the categories ahead of time. We gave it five variables for every patient (comorbidity count, age, length of stay, ED visits in the past year, and social determinants risk score) and told it to find 5 natural groupings, or clusters, where patients within a group look similar to each other and different from patients in other groups. We didn't tell it what "high risk" or "low risk" means. It just found the patterns, and we labeled the groups afterward based on what showed up. That's what let us find a risk group that wasn't obvious just by looking at the raw data.

📊 What the Numbers Showed
The five clusters we found:
- Cluster 1: our highest risk group, made up 15% of patients and had a 59% readmission rate. They had the heaviest comorbidity load and the most ED visits of any group.
- Cluster 2: 19% of patients, came in at 52% readmitted, with the longest hospital stays of any cluster.
- Cluster 3: 23% of patients, sat at 44% readmitted. This is the one that mattered most to us. Their comorbidity count was actually the lowest of any cluster, and they were the oldest patients on average at 66 years old. Nothing about their chart makes them look severe, but they were still coming back at a high rate.
- Cluster 4: 22% of patients, was our youngest group at an average age of 35, with a 39% readmission rate.
- Cluster 5: 22% of patients, averaged age 65 with a 38% readmission rate, which told us age alone wasn't driving risk once comorbidity burden was low.

A quick note on our logistic regression model:
We also ran a logistic regression to see what factors predict readmission. Where a patient got discharged to came out as the top signal, followed by whether they had a scheduled follow up and completed medication reconciliation, things the hospital can actually control. Comorbidity count and ED visits mattered too, just less. We used this mainly to confirm and rank the risk factors, and leaned on the clustering to shape our actual recommendation.

✅ The Solution
Cluster 3 is the group we recommend targeting. They don't look high risk on paper. Low comorbidity count, nothing flagging them as severe, but they still come back 44% of the time. They're not the sickest patients in the building, just the ones nobody follows up with after they leave. Our recommendation sends them proactive outreach, portal reminders and direct contact from a physician connecting them to a specialist or primary care provider, instead of waiting for them to show up in the ER again.

✨ What We Delivered
📊 Exploratory analysis across every major variable in the dataset
🤖 A logistic regression model ranking the key drivers of 30-day readmission
🧩 K-Means clustering that sorted 10,000 patients into 5 distinct risk groups
📈 Visualizations breaking down readmission rates by diagnosis, discharge type, age, and comorbidity count
🎯 A targeted outreach plan for Cluster 3, the highest impact, most overlooked patient group
🗓️ A phased rollout plan for the hospital to put the recommendation into action

🧠 Key Decisions
We chose logistic regression because the goal was to explain what's actually driving readmissions to hospital stakeholders, not just spit out a black box prediction. We used K-Means clustering instead of manually deciding what "high risk" means, so the data could group patients on its own. Discharge outcome turned out to be the strongest signal in the model, but we made a point of flagging that it's tangled up with how sick patients already were, not a simple process fix on its own.

📚 What This Case Taught Us
The biggest risk group isn't always the obvious one. It's tempting to build a model, flag the sickest patients, and call the analysis done. But the group that actually mattered here was the one that looked fine by every standard measure and still had a 44% readmission rate. We also learned how important it is to be upfront about a model's limits in a client facing recommendation, since the strongest predictor in our model was partly a symptom of patient severity rather than a clean fix.

🚀 Why We Took This On
We wanted a case that went beyond surface level numbers, not just reporting a readmission rate but actually digging into who was falling through the cracks and why. It gave us the chance to work through a real healthcare dataset from start to finish. Cleaning it, exploring it, modeling it, and turning that into a recommendation a hospital could realistically put into action.
