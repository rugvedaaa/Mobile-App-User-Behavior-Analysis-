# 📱 Mobile App User Behavior Analysis  

This project focuses on analyzing **user behavior in a mobile app** and preparing the data for predictive modeling. The main objective is to understand what drives a user to **enroll** in the app after their first open.  

---

## 📂 Project Overview  
- Worked with **50,000 user records** from `appdata.csv`.  
- Conducted **Exploratory Data Analysis (EDA)** to uncover usage patterns.  
- Performed **data cleaning & preprocessing** on time-based and categorical fields.  
- Engineered new features such as **funnels** (Loan, Credit, Saving, etc.) to better capture user behavior.  
- Created a final cleaned dataset `new_appdata.csv` with ~50 features, ready for modeling.  

---

## 🛠 Tools & Libraries  
- **Python**  
  - pandas, numpy  
  - matplotlib, seaborn, plotly  
- **Jupyter Notebook**  

---

## 🔍 Steps Performed  

### 1. Exploratory Data Analysis  
- Checked summary statistics & distributions.  
- Visualized:  
  - **Day of the week** → higher activity on weekends.  
  - **Hour of usage** → peaks late evening/night.  
  - **Age distribution** → majority between 20–40 years.  
  - **Number of screens visited** → most browse ~30 screens.  
- Explored correlations between features and enrollment.  

### 2. Data Pre-processing  
- Converted `hour` into numeric format.  
- Converted `first_open` & `enrolled_date` into datetime objects.  
- Created a new column: `difference = enrolled_date – first_open` (in hours).  
- Reclassified enrollments → if `difference > 48 hours`, set as not enrolled.  
- Dropped redundant columns (`first_open`, `enrolled_date`, `difference`).  

### 3. Feature Engineering  
- Used `popular_screens.csv` to extract important screens.  
- Converted `screen_list` into **binary indicators** (visited or not).  
- Grouped related screens into funnels:  
  - `SavingCount`  
  - `CMCount` (Credit Monitoring)  
  - `CCCount` (Credit Cards)  
  - `LoansCount`  
- Added an `other` feature for remaining screens.  

### 4. Final Dataset  
- Produced a **cleaned dataset with ~50 features**.  
- Exported as `new_appdata.csv` for modeling.  

---

## 📊 Results & Insights  
- **Enrollment happens quickly** → Most users enroll right after first open.  
- **Peak activity** → Evenings & weekends show the most usage.  
- **Age group** → Younger users (20–40) drive the majority of activity.  
- **Behavioral links** → Users exploring financial screens (loan/credit/saving) are more likely to enroll.  
- **Final Output** → A dataset that’s structured for direct input into machine learning models (Logistic Regression, Random Forest, XGBoost, etc.) to predict enrollment.  

---

## 🚀 Next Steps  
- Train ML models on `new_appdata.csv` to predict user enrollment.  
- Build dashboards for visual reporting.  
- Further optimize features for predictive performance.  

---

## 📁 Repository Structure  
├── appdata.csv # Original dataset
├── popular_screens.csv # List of popular app screens
├── Mobile_App_Analysis.ipynb # Jupyter notebook with full workflow
├── new_appdata.csv # Final cleaned dataset with engineered features
└── README.md # Project documentation


---

## ⚙️ How to Run  

1. Clone the repository:  
   ```bash
   git clone https://github.com/your-username/mobile-app-user-analysis.git
   cd mobile-app-user-analysis
