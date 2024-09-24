# Lung Cancer Treatment Decision Support System Using Keytruda (Pembrolizumab)

### 1. **Overview and Background**
Lung cancer is one of the most aggressive and fatal cancers globally, with non-small cell lung cancer (NSCLC) being the most common type. Over the years, treatment strategies have evolved significantly. **Keytruda (Pembrolizumab)** is an immunotherapy drug designed to target the PD-1/PD-L1 pathway, a mechanism that cancer cells exploit to evade detection by the immune system. By blocking this pathway, Keytruda enables the immune system to recognize and attack cancer cells more effectively.

Keytruda has shown great promise in treating various cancers, especially in cases where high levels of PD-L1 expression are present. However, it is not always clear which patients will benefit the most from this treatment, as it is based on a combination of biomarkers and clinical factors.

---

### 2. **Objective of the Project**
The goal of this project is to assist doctors in making more informed decisions on whether Keytruda is a suitable treatment option for a given lung cancer patient. By using machine learning, we aim to build a predictive model that will analyze patient data and assess their likelihood of responding positively to Keytruda treatment.

This decision support system will not only help doctors make quicker decisions based on data-driven insights, but it will also provide patients with a personalized treatment plan, improving outcomes and reducing unnecessary treatments.

---

### 3. **Project Methodology and Proposed Solution**
This project will follow a structured methodology to develop a robust machine learning model and deploy it for real-world use:

#### **Step 1: Dataset Overview**
The dataset contains detailed information about 3,000 lung cancer patients, including their age, gender, cancer stage, tumor size, genetic mutations, smoking history, and their response to previous treatments.

**Shape of Dataset:**
- Rows: 3000
- Columns: 10

**Columns:**
- `Patient_ID`: Unique identifier for each patient.
- `Age`: Age of the patient.
- `Gender`: Male/Female.
- `Cancer_Stage`: Stage of lung cancer (Stage II, Stage III, Stage IV).
- `PD-L1_Level`: Percentage of PD-L1 expression in the tumor cells.
- `EGFR_Mutation_Count`: Number of mutations in the EGFR gene.
- `Tumor_Size`: Size of the tumor in centimeters.
- `Treatment_Type`: Type of treatment received (Chemotherapy or Immunotherapy).
- `Smoking_Status`: Smoking history of the patient (Never, Former, Current).
- `Response`: Patient's response to treatment (Responder/Non-Responder).

#### **Step 2: Loading Data**
We will start by loading the dataset into a database system such as MySQL or from a `.csv` file. This will help in managing larger datasets and efficiently querying patient records.

- **Technology Stack**: MySQL for database management.
- **Python Libraries**: `pandas`, `sqlalchemy` for data manipulation and database connection.

#### **Step 3: Data Cleaning and Preprocessing**
Once the data is loaded, we will perform several data cleaning steps:
- Handling missing values, especially in categorical and numerical fields such as `Smoking_Status`, `Gender`, and `Tumor_Size`.
- Removing or treating outliers in numerical columns such as `Age` and `Tumor_Size`.
- Feature encoding for categorical variables like `Treatment_Type` and `Smoking_Status`.

#### **Step 4: Exploratory Data Analysis (EDA)**
In this step, we will gain insights into the dataset by visualizing:
- Distribution of key variables like PD-L1 levels, tumor sizes, and cancer stages.
- Correlations between variables such as PD-L1 expression and response to treatment.
- Potential relationships between patient attributes and their likelihood of responding to Keytruda.

#### **Step 5: Feature Engineering**
We'll create new meaningful features by combining existing columns or performing transformations. Examples include:
- Binary encoding for `Response` (0 for Non-Responder, 1 for Responder).
- Binning `Age` and `Tumor_Size` into categories (e.g., small/medium/large tumor).

#### **Step 6: Model Building**
We will experiment with several machine learning models to predict treatment response, including:
- Logistic Regression
- Random Forest Classifier
- XGBoost Classifier

Each model will be trained on the patient data, and hyperparameters will be tuned to optimize performance. We will use cross-validation techniques to evaluate model accuracy, precision, recall, and F1 score.

#### **Step 7: Model Evaluation**
After training and tuning, the model's performance will be evaluated using standard metrics:
- **Accuracy**: The percentage of correct predictions.
- **Precision and Recall**: How well the model balances between correctly identifying responders and non-responders.
- **AUC-ROC**: This curve will help us understand the model's ability to distinguish between responders and non-responders.

#### **Step 8: Flask-based Web Application**
Finally, we will deploy this predictive model as a web application using Flask, allowing doctors to enter patient details and receive a prediction on whether Keytruda will be an effective treatment.

- **Front-End**: Simple form-based interface for doctors to enter patient data.
- **Back-End**: Flask-based API that connects to the trained machine learning model to provide predictions.
- **Deployment**: The app can be deployed locally or using cloud services like AWS or Heroku for real-time access.

#### **Project Workflow Summary:**
1. **Data Loading**: Load data from MySQL or CSV.
2. **Data Cleaning**: Handle missing values, outliers, and perform feature encoding.
3. **EDA**: Analyze data patterns and correlations.
4. **Feature Engineering**: Create new features for better model accuracy.
5. **Model Training**: Train and evaluate machine learning models.
6. **Deploy as Web App**: Create Flask-based application to provide real-time treatment suggestions.

---

### 4. **Benefits of the Project**
- **For Doctors**: This system allows healthcare professionals to quickly assess the effectiveness of Keytruda for their patients, enabling data-backed decisions and reducing the trial-and-error aspect of cancer treatment.
- **For Patients**: Patients benefit from a personalized treatment plan, ensuring they receive the most effective treatment based on their specific health profile, thereby improving outcomes and reducing unnecessary side effects.

---

### 5. **Conclusion**
This project combines the power of data science with the growing field of precision medicine to assist in the treatment of lung cancer. By building a predictive model based on patient data, we aim to enhance clinical decision-making and improve patient care in cancer treatment.
