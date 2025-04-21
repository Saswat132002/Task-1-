# Task-1-

```markdown
# 🧹 Data Cleaning and Preprocessing - Sales Dataset

This project focuses on cleaning and preparing a raw sales dataset for further analysis. It involves handling missing values, removing duplicates, correcting inconsistent formats, and converting data types using **Python (Pandas)**.

---

## 📂 Dataset
- **Source**: [Kaggle Sales Data Sample](https://www.kaggle.com/)
- **File**: `sales_data_sample.csv`
- **Rows**: 2,823
- **Columns**: 25 (before cleaning)

---

## 🎯 Objective

Clean and prepare the dataset by:
- Handling missing values
- Removing duplicate records
- Standardizing inconsistent text formats
- Converting columns to appropriate data types
- Making the data analysis-ready

---

## 🛠️ Tools Used

- Python
- Pandas
- Jupyter Notebook / VS Code (optional)
- CSV / Excel files

---

## ✅ Cleaning Steps Performed

1. Renamed all column headers to lowercase and replaced spaces with underscores
2. Removed columns with mostly missing values (`addressline2`)
3. Dropped rows with missing values in essential columns (`customername`, `orderdate`, `country`, `postalcode`)
4. Filled missing values in `state` and `territory` with `"Unknown"`
5. Removed duplicate rows
6. Converted `orderdate` to `datetime` format
7. Converted `postalcode` to string format
8. Standardized values in `country` and `status` columns

---

## 📦 Output

- Cleaned CSV file: `cleaned_sales_data.csv`
- Ready for further analysis or visualization

---

## 📊 Sample Code

```python
import pandas as pd

# Load and clean the dataset
df = pd.read_csv('sales_data_sample.csv', encoding='latin1')
df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')
df.drop(columns=['addressline2'], inplace=True)
df.dropna(subset=['customername', 'orderdate', 'country', 'postalcode'], inplace=True)
df['state'].fillna('Unknown', inplace=True)
df['territory'].fillna('Unknown', inplace=True)
df.drop_duplicates(inplace=True)
df['orderdate'] = pd.to_datetime(df['orderdate'], errors='coerce')
df['country'] = df['country'].str.title()
df['status'] = df['status'].str.capitalize()
df['postalcode'] = df['postalcode'].astype(str)

# Save the cleaned file
df.to_csv('cleaned_sales_data.csv', index=False)
```

---

## 📈 Next Steps

- Exploratory Data Analysis (EDA)
- Data Visualization
- Insights and Reporting

---

## 🙌 Acknowledgement

This project is a part of my learning journey at **Masai School**, where I’m training to become a Data Analyst by working on real-world datasets and case studies.

---

## 📬 Connect with Me

- LinkedIn: [SASWAT](https://www.linkedin.com/in/saswat13/)
- GitHub: [SASWAT](https://github.com/Saswat132002
)

```
