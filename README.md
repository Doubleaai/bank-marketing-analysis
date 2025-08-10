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

Analysis Techniques Used
Exploratory Data Analysis (EDA) – Pandas, Matplotlib, Seaborn.

Statistical Testing – Chi-square tests with SciPy.

Planned ML Model – Logistic Regression using Scikit-learn.

Limitations:
Some features are campaign-specific and may not generalise to future marketing efforts. Certain variables (e.g., duration) may require exclusion for prediction as they are only known after contact.

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