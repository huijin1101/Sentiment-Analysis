# Sentiment-Analysis

## Overview
This project demonstrates a comprehensive sentiment analysis pipeline leveraging **Spark on Databricks (Community Edition)** to process and analyze tweets. By utilizing distributed computing capabilities and machine learning techniques, the project delivers efficient sentiment predictions and visualization.

### Dataset
- **Source**: Public S3 bucket containing tweets on the topic of Elon Musk collected in November 2022.
- **Objective**: Build an end-to-end ML pipeline to classify tweet sentiments.

---

## Methodology
### 1. Data Preparation and Cleaning
- **Data Loading**: Imported tweet data from the S3 bucket into a Spark DataFrame in Databricks.
- **Sentiment Labeling**: Added a `sentiment_label` column using TextBlob.
- **Data Cleaning**:
  - Selected relevant columns (`tweet`, `created_at`, `sentiment_label`).
  - Removed missing values and duplicates.
  - Standardized text by:
    - Removing punctuation, special characters (e.g., RT, @mentions, hashtags), URLs, numbers, and excess white spaces.
    - Applying lemmatization and converting text to lowercase.
### 2. Feature Engineering
- **Data Splitting**: 
  - 80% training and 20% testing.
- **New Features**:
  - Extracted `weekday` and `hourtime` from `created_at`.
  - Computed `words_count` from `tweet`.
### 3. Exploratory Data Analysis (EDA)
- Explored relationships between features and sentiment labels:
  - Distribution of `sentiment_label` by `weekday`.
  - Effect of `words_count` on `sentiment_label`.
  - Sentiment variation across `hourtime`.
### 4. ML Pipeline Development
- **Feature Transformation**:
  - Applied `Tokenizer`, `StopWordsRemover`, `CountVectorizer`, `IDF`, and `VectorAssembler`.
- **Model Training**:
  - Experimented with Logistic Regression and Random Forest models.
- **Pipeline Workflow**:
  - Fitted the pipeline model on training data.
  - Validated the pipeline on the testing dataset.
  - Selected the best model based on performance.
### 5. Export and Visualization
- **Export Predictions**: Saved results to the S3 bucket.
- **Dashboard Preparation**: Created a queryable table in AWS Athena.
- **Visualization**: Designed interactive dashboards in AWS QuickSight to showcase sentiment insights.

## Key Highlights
1.  **Distributed Data Processing**: Utilized Spark on Databricks to seamlessly process and analyze large datasets directly from S3, ensuring scalability and efficiency.
2. **Comprehensive Data Preprocessing**: Implemented advanced text standardization techniques, ensuring high-quality inputs for machine learning models.
3. **Feature Engineering and EDA**:
   - Introduced new features (`weekday`, `hourtime`, `words_count`) to enhance model accuracy.
   - Conducted thorough data exploration to uncover meaningful mutual relationships.
4. **Scalable ML Pipeline**:
   - Developed a robust ML pipeline integrating feature transformations and predictive models.
   - Achieved 80% accuracy with Logistic Regression.
5. **End-to-End Workflow**:
   - Automated the sentiment prediction workflow from data ingestion to visualization.
   - Integrated predictions with AWS services (S3, Athena and QuickSight) for real-time insights via interactive dashboards.

## Results
- Best model: Logistic Regression achieving **80% accuracy**.
- Interactive dashboard enabled efficient exploration of sentiment trends across time and other variables.

## Conclusion
This project highlights the power of distributed computing with Spark for large-scale sentiment analysis. By combining Databricks' capabilities with AWS services, we delivered a scalable, end-to-end pipeline from data ingestion to visualization. The approach can be extended to various NLP tasks, making it a valuable template for real-world applications.


