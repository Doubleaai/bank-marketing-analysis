## Bank Marketing Analysis
Bank Marketing Analysis is a comprehensive data analysis and prediction tool aimed at understanding customer behaviour and improving the success rate of term deposit marketing campaigns. The project uses Python for data preparation, statistical analysis, visualisation, and machine learning.

Dataset Content
The dataset, bank.csv, contains customer demographic, financial, and contact information alongside the outcome of whether they subscribed to a term deposit (deposit).

Rows: ~45,000 records

Columns: 17 features including age, job, marital, education, contact, and duration.

Data source: UCI Machine Learning Repository – Bank Marketing Dataset.

Business Requirements
The business goal is to:

Identify customer segments most likely to subscribe to a term deposit.

Provide insights into the most effective marketing channels.

Build a predictive model to support targeted marketing strategies.

Hypothesis and How to Validate
H1: Job type and term deposit subscription are dependent.
H2: Age group and term deposit subscription are dependent.
H3: Contact method and term deposit subscription are dependent.
H4: Housing loan status and term deposit subscription are dependent.

Validation:
I used Chi-square tests of independence on the feature-engineered dataset, supported by visualisations, to determine whether these variables are statistically associated with subscription rates.

Project Plan
ETL – Loaded, cleaned, and preprocessed raw bank.csv.

Feature Engineering – Created new columns such as age_band, has_any_loan, and was_previously_contacted. Saved both feature-engineered and ML-ready datasets.

EDA – Explored data patterns and relationships using visualisations.

Hypothesis Testing – Validated observed EDA relationships statistically.

ML Model – (Planned) Train and evaluate Logistic Regression for prediction.

Dashboard – (Planned) Build an interactive dashboard for insights.

The Rationale to Map the Business Requirements to the Data Visualisations
Business Requirement 1: Target customer segments → Mapped to bar plots showing subscription rates by job and age_band.

Business Requirement 2: Best marketing channels → Mapped to bar plots comparing contact method effectiveness.

Business Requirement 3: Predictive modelling → Will use feature importance plots after model training.

Analysis Summary
I began with an Exploratory Data Analysis (EDA) to uncover patterns in customer demographics, financial status, and marketing contact methods. This revealed clear trends: retired and student customers subscribed at much higher rates than most other job types, middle-aged and older customers were more likely to subscribe than younger ones, and cellular contact far outperformed telephone outreach.

These initial findings guided my Hypothesis Testing phase, where I statistically validated the relationships using Chi-square tests of independence. I confirmed significant associations (p < 0.05) for all four tested factors:

H1: Job type — Retired and student customers showed the highest subscription rates.

H2: Age group — Middle-aged and older customers subscribed more than younger ones.

H3: Contact method — Cellular contact was more effective than telephone.

H4: Housing loan status — Customers without a housing loan had a higher subscription proportion.

From these insights, I recommend targeting high-performing job and age segments, prioritising cellular contact methods, and exploring investment opportunities with customers who do not have housing loans. These findings will feed directly into my predictive modelling stage to create a Logistic Regression model aimed at improving campaign targeting.

References:
OpenAI. (2025). ChatGPT. https://chat.openai.com
GitHub. (2025). GitHub Copilot. https://github.com/features/copilot

Analysis Techniques Used
Exploratory Data Analysis (EDA) – Pandas, Matplotlib, Seaborn.

Statistical Testing – Chi-square tests with SciPy.

Planned ML Model – Logistic Regression using Scikit-learn.

Limitations:
Some features are campaign-specific and may not generalise to future marketing efforts. Certain variables (e.g., duration) may require exclusion for prediction as they are only known after contact.

Machine Learning
I initially implemented a Logistic Regression model during my feature engineering stage to create a baseline for predicting whether a customer would subscribe to a term deposit. While this provided interpretable results, I wanted to explore more advanced algorithms to see if predictive performance could be improved.

For this, I trained and evaluated two additional supervised learning models:

1. Random Forest Classifier
The Random Forest model was chosen for its ability to handle mixed data types, capture non-linear relationships, and provide feature importance scores. It performed reliably, producing balanced precision and recall values, and highlighted that previous contact history, month of contact, and specific job categories were among the most influential predictors.

2. XGBoost Classifier
I also implemented XGBoost, a gradient boosting algorithm known for strong performance on structured/tabular data. After cleaning my column names for compatibility, XGBoost achieved slightly higher recall on the positive class compared to Random Forest, making it particularly useful for identifying potential subscribers. Like Random Forest, it confirmed the importance of features such as previous outcome, call intensity, and age bands.

Evaluation and Insights
Both models were evaluated using accuracy, precision, recall, F1-score, and confusion matrices.

Random Forest offered balanced predictions with clear interpretability of top features.

XGBoost provided slightly better recall, which is valuable in marketing scenarios where identifying potential subscribers is more important than avoiding false positives.

Feature importance analysis from both models will directly inform my dashboard recommendations, helping stakeholders focus on the most influential customer attributes.

Ethical Considerations
No personally identifiable information (PII) is present.

Bias awareness: Job, age, and education-based targeting could unintentionally cause discrimination. Any recommendations will be reviewed for fairness.

Dashboard Design (Planned)
Pages:

Overview: Subscription rate trends and customer segmentation.

Demographics: Visualisation by job, age_band, and marital status.

Contact Method: Effectiveness of cellular vs telephone.

Prediction Tool: Input fields for model prediction.

How Were Data Insights Communicated
I designed plots and statistical summaries to be understandable for both technical and non-technical stakeholders, pairing visual results with plain language interpretations.

Unfixed Bugs
No current unfixed bugs. All scripts run successfully in Jupyter Notebook.

Development Roadmap
Finalise Logistic Regression model and evaluate accuracy.

Build Streamlit dashboard for interactive exploration.

Deploy project online.

Deployment
Deployment will be on GitHub for notebooks and datasets. The dashboard will be deployed via Heroku once complete.

Main Data Analysis Libraries
Pandas – Data cleaning and manipulation.

Matplotlib / Seaborn – Visualisations.

SciPy – Statistical testing (Chi-square).

Scikit-learn – Planned machine learning model.

Credits
Content:

Dataset from UCI Machine Learning Repository.

Statistical methods inspired by Scipy documentation.

Visualisation styling guided by Seaborn examples.

Media:

No external media used. 

Acknowledgements:


Special thanks to ChatGPT (OpenAI, 2025) and GitHub Copilot (GitHub, 2025) for assisting in ideation, design thinking, and code optimisation.