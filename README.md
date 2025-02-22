# Customer Churn Prediction using AWS  

## Overview  
Customer churn prediction is critical for improving customer retention and business profitability. This project leverages **machine learning models** to analyze customer behavior and predict churn risk. We utilize **AWS services** for data processing, model training, prediction, and visualization.  

## Problem Statement  
Customer attrition leads to significant revenue loss for businesses. Identifying at-risk customers enables proactive retention strategies. The goal is to:  
- Use historical customer data to train **ML models**.  
- Experiment with multiple models to identify churn triggers.  
- Predict at-risk customers and notify stakeholders.  
- Visualize customer journeys and churn patterns using dashboards.  

## Dataset  
- **Source:** [Churn_Modelling.csv](https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling)  
- **Size:** 10,000 customer records  
- **Features:**  
  - Credit Score, Geography, Gender, Age, IsActiveMember, Exited, etc.  
  - Geographic regions: France, Spain, Germany  

## Tools & Technologies  
### **AWS Services Used**  
- **AWS IAM** – User and role creation for access control.  
- **AWS S3** – Data storage and management.  
- **AWS SageMaker** – Data cleaning, preprocessing, model training, and deployment.  
- **AWS QuickSight** – Data visualization and dashboarding.  
- **AWS SNS** – Event-driven notifications.  
- **AWS Lambda** – Automating custom email notifications.  
- **AWS SES** – Configuring recipients and delivering emails.  

### **Other Tools**  
- **Jupyter Notebook** – For model development and experimentation.  

## Project Architecture  
1. **Data Storage:**  
   - **AWS S3:** A dedicated bucket (`churn-modelling-bucket`) was created to store raw and processed data.  
2. **Exploratory Data Analysis (EDA):**  
   - **AWS QuickSight** was used to analyze trends and distributions.  
   - **Key Insights:**  
     - Churn rates vary by geography and gender.  
     - Higher churn observed among customers with fewer products.  
     - Weak correlation between credit score and churn.  
3. **Data Preprocessing:**  
   - **Feature Engineering:** Converted categorical variables into numerical representations.  
   - **Data Cleaning:** Handled missing values and normalized data.  
4. **Model Training & Evaluation:**  
   - **Algorithms Tested:**  
     - Logistic Regression  
     - Support Vector Machine (SVM)  
     - Decision Tree  
     - Random Forest  
     - K-Nearest Neighbors (KNN)  
   - **Best Model:** Random Forest (F1 Score: **0.82**)  
   - **Challenges Addressed:**  
     - Imbalanced dataset: Applied stratified sampling to balance class distribution.  
5. **Automated Notifications:**  
   - **AWS SNS:** Monitors S3 updates and triggers notifications.  
   - **AWS Lambda & SES:** Sends emails with churn reports and model predictions.  
6. **Data Visualization:**  
   - **AWS QuickSight Dashboards** displaying customer churn insights.  

## Challenges & Resolutions  
| **Challenge** | **Resolution** |  
|--------------|--------------|  
| IAM policy restrictions for SageMaker & QuickSight access | Created **custom inline policies** for specific roles. |  
| AWS QuickSight login issues | Initial access required via **root user setup**. |  
| Highly imbalanced dataset | Used **stratified sampling** to ensure fair model evaluation. |  

## Future Scope  
- **Integrate real-time predictions** using AWS Lambda or Step Functions.  
- Extend model to **other business domains and datasets**.  
- Experiment with **deep learning models** for improved accuracy.   

## References  
- [Kaggle Dataset](https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling)  
- AWS Documentation: [IAM](https://aws.amazon.com/iam/), [S3](https://aws.amazon.com/s3/), [SageMaker](https://aws.amazon.com/sagemaker/), [QuickSight](https://aws.amazon.com/quicksight/), [Lambda](https://aws.amazon.com/lambda/), [SNS](https://aws.amazon.com/sns/), [SES](https://aws.amazon.com/ses/)  

---

🚀 **For more details, explore the [EDA Report](Exploratory_Data_Analysis.pdf) and [Interactive Dashboard](Interactive_Dashboard.pdf).**  
