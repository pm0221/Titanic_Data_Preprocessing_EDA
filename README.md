# Titanic Dataset – Exploratory Data Analysis and Data Preprocessing

## Project Overview
This notebook performs exploratory data analysis (EDA) and basic data preprocessing on the Titanic training dataset. It examines missing values in selected columns, summarizes the Age distribution, analyzes passenger embarkation ports, and prepares a cleaned copy of the dataset by handling missing values.

## Objectives
- Load and inspect the Titanic training dataset.
- View sample records and dataset size.
- Identify missing values and calculate missing-value percentages.
- Calculate the mean and median age.
- Visualize the Age distribution using a histogram and density plot.
- Analyze passenger counts by port of embarkation.
- Identify the most common embarkation port and cabin value.
- Handle missing Age and Embarked values.
- Drop the Cabin column and inspect the resulting dataset.

## Dataset
The notebook reads an Excel file named **`train.xlsx`**:

```python
train_df = pd.read_excel('train.xlsx')
```

Place `train.xlsx` in the same folder as the notebook before running it.

The notebook uses these columns:
- `Age` – passenger age.
- `Embarked` – port of embarkation (`C`, `Q`, or `S`).
- `Cabin` – cabin information.

The dataset is expected to be a Titanic training dataset containing these columns.

## Tools and Libraries
- Python
- Jupyter Notebook
- pandas – loading and manipulating tabular data
- NumPy – numerical operations
- Matplotlib – plotting and visualization
- Seaborn – statistical visualizations
- Plotly Express – imported in the notebook

## Workflow

### 1. Import libraries and load the dataset
The notebook imports the required Python libraries and loads `train.xlsx` into a pandas DataFrame named `train_df`.

### 2. Inspect the dataset
- Display the first few records.
- Check the number of samples (rows).
- Count missing values in each column.

### 3. Analyze missing values and Age
- Calculate the percentage of missing values in `Age`.
- Calculate the mean and median age, excluding missing values.
- Plot the Age histogram and density curve.

### 4. Analyze Embarked and Cabin
- Calculate the percentage of missing values in `Embarked` and `Cabin`.
- Count passengers for each embarkation port:
  - `C` – Cherbourg
  - `Q` – Queenstown
  - `S` – Southampton
- Display the embarkation counts with a Seaborn count plot.
- Identify the most frequent `Embarked` value and the most frequent `Cabin` value.

### 5. Preprocess the data
A copy of the original DataFrame is created as `train_data`. The notebook then:
- Fills missing `Age` values with the median age.
- Fills missing `Embarked` values with the most frequent embarkation port (mode).
- Drops the `Cabin` column.
- Checks remaining missing values and displays the cleaned data.
- Plots the Age distribution after preprocessing.

## How to Run
1. Keep `DA_EXP4.ipynb` and `train.xlsx` in the same folder.
2. Install the required packages:

   ```bash
   pip install pandas numpy matplotlib seaborn plotly openpyxl jupyter
   ```

3. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

4. Open `DA_EXP4.ipynb`.
5. Run the cells from top to bottom.

## Notes
- The notebook expects the input file to be named exactly `train.xlsx`.
- The Excel dataset is not included with this README; provide it separately.
- The notebook creates a cleaned DataFrame in memory (`train_data`). It does not save the cleaned dataset to a new Excel or CSV file.
- The `Cabin` column is dropped rather than imputed because the notebook treats it as a column to remove during preprocessing.
- The notebook imports Plotly Express, although no Plotly Express chart is created in the current notebook.
- Some pandas `inplace=True` operations may show deprecation or chained-assignment warnings in newer pandas versions. The preprocessing can be rewritten with direct column assignment if needed.

## Conclusion
This experiment demonstrates basic EDA and missing-value handling on the Titanic dataset. It uses summary statistics and visualizations to understand the data, then applies median imputation for `Age`, mode imputation for `Embarked`, and removes `Cabin` to create a prepared DataFrame for further analysis.
