# Sentiment-Analysis

## Overview
This project demonstrates a comprehensive sentiment analysis pipeline leveraging **Spark on Databricks (Community Edition)** to process and analyze tweets. By utilizing distributed computing capabilities and machine learning techniques, the project delivers efficient sentiment predictions and visualization.

### Dataset
- **Source**: Public S3 bucket containing tweets on the topic of Elon Musk collected in November 2022.
- **Objective**: Build an end-to-end ML pipeline to classify tweet sentiments.

---

## Methodology
### 1. Data Preparation and Cleaning
![Data Preparation and Cleaning](images/SA_metho1.png)
### 2. Feature Engineering and Exploratory Data Analysis (EDA)
![Feature Engineering and EDA](images/SA_metho2.png)
### 3. ML Pipeline Development
![ML Pipeline Development](images/SA_metho3.png)
### 4. Export and Visualization
![Export and Visualization](images/SA_metho4.png)

## Key Highlights
1.  **Distributed Data Processing**:
    - Utilized Spark on Databricks to seamlessly process and analyze large datasets directly from S3, ensuring scalability and efficiency.
2. **Comprehensive Data Preprocessing**:
   - Implemented advanced text standardization techniques, ensuring high-quality inputs for machine learning models.
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
- Interactive dashboard enabled efficient exploration of sentiment trends across time and other variables:
  ![Dashboard](SA_visu.png)
  - 0, 1, 2 represent Negative, Neutral, Positive respectively.
  - The first row of images shows the distribution of sentiments in the dataset, highlighting the proportions of each sentiment category.
  - The first image in the second row illustrates the relationship between tweet word count and sentiment. It reveals that neutral tweets tend to have fewer words compared to negative and positive sentiments.
  - The second image in the second row depicts the proportion of predicted sentiments within each actual sentiment category, providing insights into the prediction accuracy for each sentiment class.. 
## Conclusion
This project highlights the power of distributed computing with Spark for large-scale sentiment analysis. By combining Databricks' capabilities with AWS services, we delivered a scalable, end-to-end pipeline from data ingestion to visualization. The approach can be extended to various NLP tasks, making it a valuable template for real-world applications.


