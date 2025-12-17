# Capstone-Project-1-Infosys-Internship

## Project Overview
This project performs an Exploratory Data Analysis (EDA) on census income data to identify the key factors that influence an individual's earning potential. By cleaning the data, engineering new features, and analyzing correlations, this project aims to predict whether an individual earns more than $50,000 annually.

The analysis is implemented in a Jupyter Notebook using Python.

## Dataset
The project uses the **Adult Census Income** dataset (often referred to as the "Census Income" dataset).
* **Input File:** `adult_data.csv`
* **Target Variable:** `earning` (>50K or <=50K)
* **Key Features:** Age, Workclass, Education, Marital Status, Occupation, Race, Sex, Hours per week, Native Country.

## Tech Stack
* **Python 3.x**
* **Pandas:** For data manipulation and cleaning.
* **NumPy:** For numerical operations and handling missing values.
* **Seaborn & Matplotlib:** For data visualization (Boxplots, Heatmaps).

## Key Analysis Steps

### 1. Data Cleaning
The raw data contained missing values and inconsistencies which were handled as follows:
* **Missing Value Handling:** Replaced placeholder characters (e.g., `' ?'`, `' NA'`) with `NaN` and dropped rows containing missing data to ensure analysis quality.
* **Column Removal:** Dropped `capital-gain` and `capital-loss` to focus on demographic and employment factors.

### 2. Feature Engineering
New features were derived to extract deeper insights:
* **`Experience`:** Estimated using the formula:  
    $$\text{Experience} = \text{Age} - \text{Education Num} - 5$$
    *(Assumption: Education starts at age 5)*.
* **`Work-life Balance`:** A custom metric calculated as:
    $$\text{Work-life Balance} = \frac{\text{Hours per Week}}{\text{Age}}$$
* **`earning_potential`:** Converted the categorical `earning` column into a binary numeric column (1 for `>50K`, 0 for `<=50K`) for correlation analysis.

### 3. Outlier Detection
* Applied the **Interquartile Range (IQR)** method to remove outliers from numerical columns (`age`, `education-num`, `hours-per-week`), ensuring extreme values do not skew the analysis.

### 4. Correlation Analysis
* Calculated correlation coefficients to determine which factors most strongly correlate with higher earnings.
* **Key Insight:** `education-num` (years of education) and `age` showed significant positive correlations with earning potential.

## How to Run

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/Earning-Potential-Analysis.git](https://github.com/YOUR_USERNAME/Earning-Potential-Analysis.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas numpy seaborn matplotlib
    ```
3.  **Place the dataset:**
    Ensure `adult_data.csv` is in the same directory as the notebook.
4.  **Run the Notebook:**
    Open `Earning Potential Analysis(EDA).ipynb` in Jupyter Notebook or VS Code and execute the cells.

## Results
* **Visualizations:** Boxplots comparing work hours across earning classes.
<img width="622" height="470" alt="image" src="https://github.com/user-attachments/assets/f7969daa-f94c-4a3a-90b3-5c64bc062646" />

* **Correlation Matrix:** Identifies that Education Level and Experience are strong indicators of high income, while the custom 'Work-life Balance' metric shows a negative correlation with higher age/experience brackets.
<img width="827" height="741" alt="image" src="https://github.com/user-attachments/assets/2bcb9993-8f5b-4c75-8e26-2f8c6dd9d909" />
* **Demographic Factors:** A clear upward trend showing that as education-num (years of education) increases, the probability of high earning (earning_potential) increases significantly.
  <img width="618" height="490" alt="image" src="https://github.com/user-attachments/assets/7adb102e-9927-4f52-802c-c37c08bc60c3" />
* A bar chart comparing earning potential between genders.
  <img width="625" height="482" alt="image" src="https://github.com/user-attachments/assets/a5a20db1-9a88-47f2-911e-3ffc57c06625" />
* Bar charts ranking different job roles and employment types by their likelihood of earning >50K.
<img width="1110" height="593" alt="image" src="https://github.com/user-attachments/assets/43057fba-8981-4430-82f4-f3389b2de5f2" />
<img width="512" height="370" alt="image" src="https://github.com/user-attachments/assets/a8d0eefd-1b27-4f61-96e6-db8701e5db10" />
* **Work-Life Balance:** Shows how your calculated "Work-life Balance" metric changes as people get older.
  <img width="926" height="577" alt="image" src="https://github.com/user-attachments/assets/ab8a0dda-1d98-49f4-926b-989d2ef4f175" />






## License
This project is open-source and available for educational purposes.
