# 📊 AI & Data Strategy Projects

This page summarizes **4 data science & business analytics projects** that I led or deeply participated in, covering predictive modeling, natural language processing, user behavior analysis, and channel performance evaluation. Each project includes both a **detailed report (PDF)** and **code execution results (HTML)** to demonstrate business insights and technical implementation.

---

## 1. Airbnb Superhost Influencing Factors Analysis

**Objective**: Identify key factors that help Airbnb hosts in Hong Kong become "Superhosts" and provide actionable recommendations.

**Methods & Technologies**:
- Logistic Regression to identify significant variables (amenities count, acceptance rate, response time, etc.)
- Random Forest & XGBoost to validate feature importance
- Fine-grained logistic regression on 35 amenities to find top 3 most impactful amenities (shampoo, iron, TV)
- Cross‑validation (5‑fold) and cost‑sensitive classification to optimize cut‑off

**Key Results**:
- “Number of available amenities” is the strongest positive predictor
- 4 actionable suggestions: reduce response time, increase acceptance rate, improve neighborhood description, prioritize high‑value amenities
- Model achieved **~74% AUC** on test set, with a misclassification rate of ~20%
<!-- 
📄 [Project Report (PDF)](./MyBusinessAnalysticsProject/Airbnb%20Actionable%20Factor%20Modeling-%20Turning%20Hosts%20To%20Superhosts/Airbnb%20Project%20Report.pdf)  
💻 [Code & Execution Results (HTML)](./MyBusinessAnalysticsProject/Airbnb%20Actionable%20Factor%20Modeling-%20Turning%20Hosts%20To%20Superhosts/[Data%20Analysis]%20Data%20Analysis%20and%20Modeling%20by%20Python.pdf)  -->

---

## 2. Credit Suisse Crisis News Headline Sentiment Labeling

**Objective**: Automatically label news headlines about the "Credit Suisse crisis" with sentiment polarity (positive/negative/neutral) for subsequent public opinion analysis.

**Methods & Technologies**:
- Rule‑based sentiment polarity calculation using **TextBlob**
- Explored generative labeling using **Hugging Face Transformers** (GPT‑Neo) – code reserved
- Data preprocessing: Excel reading, batch processing of titles
- Output: new Excel file with sentiment scores

**Key Results**:
- Completed sentiment labeling for 4,000+ news headlines
- Built a reusable sentiment analysis pipeline (Python + pandas + TextBlob)
- Provided structured sentiment‑labeled data for event‑driven analysis

<!-- 📄 [Report & Code (HTML – includes full code + outputs)](./MyBusinessAnalysticsProject/Credit%20Suisse%20Crisis%20Sentiment%20Analysis%20of%20International%20News%202023/Credit%20Suisse%20Crisis%20Sentiment%20Analysis/)  
💻 (Same file – already contains code, execution results, and explanations) -->

---

## 3. Coupon Acceptance Prediction (DNN Model)

**Objective**: Build a Deep Neural Network (DNN) model to predict whether a user will accept a coupon, based on scenario factors, personal attributes, and activity frequency, in order to optimize marketing ROI.

**Methods & Technologies**:
- Data cleaning: removed feature `car` (too many NAs), handled 794 missing entries across 5 features
- Feature engineering: 8 ordinal features converted to numeric, 15 nominal features one‑hot encoded, removed constant columns and perfectly collinear features
- Feature selection: XGBoost ranking + incremental feature testing (optimal: 29 features)
- Model architecture: DNN (5 hidden layers: 135‑85‑94‑32‑1, ReLU + Sigmoid), with Dropout and L1 regularization
- Hyperparameter tuning: neurons, batch size, epochs

**Key Results**:
- Test accuracy **73.8%**, validating the effectiveness of feature selection and model architecture
- Business value: help businesses target high‑intent users, reducing wasteful coupon distribution

<!-- 📄 [Project Report (PDF)](./[Project%20Report]%20Cupon%20Prediction%20Report.pdf)  
💻 [Code & Execution Results (HTML)](./coupon_prediction.html) *(to be added – export your .ipynb to HTML)* -->

---

## 4. HKUST YouTube Channel Competitive Analysis & Content Strategy

**Objective**: Analyze the performance of the five major Hong Kong universities’ YouTube channels and provide recommendations for HKUST to increase views and engagement.

**Methods & Technologies**:
- **Power BI Dashboard**: visualizes competitive rankings (average duration, likes, views, number of videos)
- Correlation analysis: relationship between views and likes, segmented by video length
- Content analysis: word cloud to identify popular topics (long videos: academic; short videos: promotional)
- Factor analysis: impact of posting time (term/month/weekday), title language, and number of tags on views

**Key Results**:
- Identified HKUST’s middle‑of‑the‑pack position and gaps (short average duration, low engagement)
- Found that “likes and views are strongly correlated for longer videos”, but short videos still drive high view counts
- Specific recommendations: increase academic long‑form videos, optimize posting timing, enrich tags, etc.

<!-- 📄 [Project Report (PDF)](./[PowerBI%20Dashboard]%20HK%20University%20Channel%20in%20YouTube.pdf)  
💻 (This project uses Power BI; no standalone code file. The report includes all visualizations and analysis.) -->

---

## 🛠️ Common Tech Stack

- **Languages**: Python (pandas, scikit‑learn, XGBoost, TextBlob, transformers)
- **Deep Learning**: TensorFlow / Keras (DNN, Dropout, L1 regularization)
- **Visualization**: Power BI, Matplotlib, Word Cloud
- **Data Processing**: Excel, Jupyter Notebook

---

## 📁 Notes

- “Code & Execution Results (HTML)” files are exported from Jupyter Notebook and can be viewed directly in a browser, showing full code, outputs, and charts.
- For projects where HTML is not yet available, placeholders are provided. I will supplement them soon.
- All files are located in the same directory to ensure link validity.