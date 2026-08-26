Used Car Data Preprocessing

A complete machine learning data preprocessing workflow for the Used Car Resale Dataset.

This project demonstrates how raw data can be transformed into a clean and machine-learning-ready dataset using Python and Scikit-learn.

---

📌 Project Overview

Data preprocessing is one of the most important stages in a machine learning workflow. Raw datasets may contain outliers, categorical variables, inconsistent feature scales, and other issues that can affect the performance of machine learning models.

This project performs a complete preprocessing workflow on a Used Car Resale Dataset, including:

- Dataset inspection
- Missing value analysis
- Duplicate record checking
- Feature and target separation
- Train-test splitting
- IQR-based outlier detection
- Outlier handling using IQR capping
- Nominal categorical encoding
- Ordinal categorical encoding
- Feature scaling
- Data leakage prevention
- Final dataset verification

The final processed dataset is suitable for use in machine learning models for predicting used car resale prices.

---

🎯 Objectives

The objectives of this project are to:

1. Load and inspect the Used Car Resale Dataset.
2. Identify input features and the target variable.
3. Check for missing values and duplicate records.
4. Identify numerical outliers using the IQR method.
5. Handle outliers using IQR-based capping.
6. Encode categorical variables using appropriate encoding techniques.
7. Apply feature scaling to numerical features.
8. Split the dataset into training and testing sets.
9. Prevent data leakage during preprocessing.
10. Verify and save the final processed dataset.

---

📂 Project Structure

used-car-data-preprocessing/
│
├── notebooks/
│   └── Day12_Used_Car_Data_Preprocessing.ipynb
│
├── data/
│   ├── Used_Car_Preprocessed_Dataset.csv
│   ├── Used_Car_Preprocessed_Train.csv
│   └── Used_Car_Preprocessed_Test.csv
│
├── reports/
│   └── Used_Car_Training_Outlier_Report.csv
│
├── .gitignore
├── README.md
└── requirements.txt

---

📊 Dataset Information

The dataset contains 320 records and 15 columns related to used cars.

Main Features

Feature| Description
Car_ID| Unique identifier for each car
Brand| Car manufacturer
Year| Manufacturing year
Mileage_Km| Distance travelled by the car
Engine_CC| Engine capacity
Power_BHP| Engine power
Fuel_Type| Type of fuel
Transmission| Manual or automatic transmission
City| Location of the car
Seller_Type| Type of seller
Condition| Overall condition of the car
Previous_Owners| Number of previous owners
Accidents_Reported| Accident history
Service_Score| Vehicle service condition score
Resale_Price_Lakh| Target variable

---

🔄 Preprocessing Workflow

Raw Dataset
     │
     ▼
Dataset Inspection
     │
     ▼
Missing Value & Duplicate Check
     │
     ▼
Remove Identifier Column
     │
     ▼
Separate Features and Target
     │
     ▼
Train/Test Split (80/20)
     │
     ▼
Fit Preprocessing on Training Data Only
     │
     ├── IQR Outlier Capping
     ├── Numerical Feature Scaling
     ├── Ordinal Encoding
     └── One-Hot Encoding
     │
     ▼
Transform Training & Testing Data
     │
     ▼
Verify Processed Dataset
     │
     ▼
Save Final Processed Data

---

Outlier Handling

Numerical outliers are identified using the Interquartile Range (IQR) method.

Formula

IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR

Upper Bound = Q3 + 1.5 × IQR

Instead of removing complete rows, extreme numerical values are capped at the calculated IQR boundaries.

This approach helps preserve the available data while reducing the influence of extreme observations.

---

🔤 Categorical Encoding

Nominal Encoding

The following categorical variables do not have a natural order and are encoded using One-Hot Encoding:

- Brand
- Fuel_Type
- Transmission
- City
- Seller_Type

Ordinal Encoding

The "Condition" variable has a meaningful order:

Poor < Fair < Good < Excellent

Therefore, it is encoded using Ordinal Encoding.

---

📏 Feature Scaling

Numerical features are standardized using:

StandardScaler()

Standardization transforms numerical variables to have approximately:

- Mean = 0
- Standard Deviation = 1

The following numerical features are scaled:

- Year
- Mileage_Km
- Engine_CC
- Power_BHP
- Previous_Owners
- Accidents_Reported
- Service_Score

---

Data Leakage Prevention

A key requirement of this project is preventing data leakage.

The dataset is first divided into:

- 80% Training Data
- 20% Testing Data

The preprocessing pipeline is then:

1. Fitted only on the training data.
2. Applied to the training data.
3. Applied to the testing data without fitting again.

X_train_processed = preprocessor.fit_transform(X_train)

X_test_processed = preprocessor.transform(X_test)

This ensures that the testing dataset does not influence:

- IQR outlier boundaries
- Scaling parameters
- Category encoding mappings

---

🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Jupyter Notebook
- Google Colab

---

📁 Output Files

The preprocessing workflow generates:

Complete Dataset

Used_Car_Preprocessed_Dataset.csv

Training Dataset

Used_Car_Preprocessed_Train.csv

Testing Dataset

Used_Car_Preprocessed_Test.csv

Outlier Report

Used_Car_Training_Outlier_Report.csv

---

🚀 How to Run

1. Clone the Repository

git clone https://github.com/Heman 659-Crypto/used-car-data-preprocessing.git

2. Open the Notebook

Open:

notebooks/Day12_Used_Car_Data_Preprocessing.ipynb

You can run the notebook using:

- Google Colab
- Jupyter Notebook
- JupyterLab

3. Install Dependencies

pip install -r requirements.txt

4. Run the Notebook

Run all cells from top to bottom.

Upload the Used Car Dataset when prompted.

The notebook will generate the processed CSV files.

---

Results

The original dataset contains:

- 320 rows
- 15 columns

After preprocessing:

- Identifier column is removed.
- Categorical variables are encoded.
- Numerical features are scaled.
- Outliers are handled using IQR capping.
- The dataset is split into training and testing sets.
- Preprocessing is performed without data leakage.
- The final processed dataset is machine-learning ready.

---

📝 Key Learning Outcomes

Through this project, the following concepts were applied:

- Data inspection
- Feature selection
- Outlier detection
- IQR method
- Feature engineering concepts
- One-Hot Encoding
- Ordinal Encoding
- Feature scaling
- Train-test splitting
- Scikit-learn pipelines
- ColumnTransformer
- Data leakage prevention

---

 Author

Heman Dhupper

B.Tech Computer Science Engineering

---

📄 License

This project is created for educational and academic purposes.