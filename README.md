# Project 6 Exploratory Data Analysis

_Overview_:
Project 6 is an opportunity to create your own custom exploratory data analysis (EDA) project using GitHub, Git, Jupyter, pandas, Seaborn and other popular data analytics tools.

_Objective_:
Perform and publish a custom EDA project to demnostrate skills with Jupyter, pandas, Seaborn and popular tools for data analytics. The notebook should tell a data story and visually present findings in a clear and engaging manner. 

_Data Set_: Titanic passenger data set will be used for this project. This dataset provides information about passengers on the Titanic, including whether they survived or not, their class (1st, 2nd, or 3rd), sex, age, the number of siblings/spouses aboard (sibsp), the number of parents/children aboard (parch), the ticket number, fare, cabin number, and the port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)

Here is an example of the data:
|survived |	pclass|	sex	|age    |	sibsp	|parch	|fare	|embarked	|class	|who	|adult_male	|deck	     |embark_town	|
|---------|-------|-----|-------|-----------|-------|-------|-----------|-------|-------|-----------|------------|--------------|
|0	      |   3	  | male| 22.0	| 1         | 0	    | 7.25	| S	        | Third	| man   | True		| Southampton| no	        | 


*Data columns included as well as entries:
*Int64Index: 891 entries, 0 to 890

| Column   | Count | Non-null | Dtype   |
|----------|-------|----------|---------|
| survived | 891   | 891      | int64   |
| pclass   | 891   | 891      | int64   |
| name     | 891   | 891      | object  |
| sex      | 891   | 891      | object  |
| age      | 714   | 714      | float64 |
| sibsp    | 891   | 891      | int64   |
| parch    | 891   | 891      | int64   |
| ticket   | 891   | 891      | object  |
| fare     | 891   | 891      | float64 |
| cabin    | 204   | 204      | object  |
| embarked | 889   | 889      | object  |

*dtypes: float64(2),|int64(4), object(5)


https://github.com/mwaskom/seaborn-data/blob/master/titanic.csv

# Environment Setup 

## Start a new project repository in GitHub and then clone down to local machine. I leveraged VS Code clone functionality

## Create Virtual Environment

```shell

py -m venv .venv
.venv\Scripts\Activate
```

## Create .gitignore file
```shell
ni .gitignore
```

## Add requirements folder

```shell

ni requirements.txt
py -m pip install -r requirements.txt
```

## Add gitignore

```shell

ni gitignore
```

# Install and Run the Project

## Add dependencies

```shell

py -m pip install jupyterlab
py -m pip install numpy
py -m pip install pandas
py -m pip install pyarrow
py -m pip install matplotlib 
py -m pip install seaborn
py -m pip install scipy
```

## Freeze dependencies

```shell

py -m pip freeze > requirements.txt
```

## Git add and commit 

```shell
git add .
git commit -m "add .gitignore, cmds to readme"
git push origin main
```

# Start Project

## Step 1. Add juypter file
1. Create the Notebook: In the VS Code Explorer, create a new file i.e., yourname_eda.ipynb. Ensure it has a .ipynb extension.
2. Verify your new notebook is open for editing. If needed, view the project files in VS Code Explorer and double-click the notebook file to open it for editing.
3. Add a Markdown cell at the top of your notebook with the introduction (include the title, author, date and the purpose of the project).

```shell
ni blehman_eda.ipynb
```

### Step 2. Import Dependencies (At the Top, After the Introduction)

```python
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
```

#### Step 3. Data Acquisition

Load the data into a pandas DataFrame.
Use the pd read functions such as pd.read_csv() or pd.read_excel() as appropriate.
To read from the Seaborn dataset, we'll use sns.load_dataset() function and pass in the 'titanic' to populate our DataFrame.

Jupyter Notebook / Python cell example:

```python
# Load the dataset into a pandas DataFrame 
df = sns.load_dataset('titanic')

# Inspect first rows of the DataFrame
print(df.head())
```

#### Step 4. Initial Data Inspection

Display the first 10 rows of the DataFrame, check the shape, and display the data types of each column using df.head(10), df.shape, and df.dtypes.

Jupyter Notebook / Python cell example:

```python

print(df.head(10))
print(df.shape)
print(df.dtypes)
```
#### Step 5. Initial Descriptive Statistics

Use the DataFrame describe() method to display summary statistics for each column.

Jupyter Notebook / Python cell example:

```python
print(df.describe())
```

#### Step 6. Initial Data Distribution for Numerical Columns

Choose a numerical column and use df['column_name'].hist() to plot a histogram for that specific column.
To show all the histograms for all numerical columns, use df.hist().

Jupyter Notebook / Python cell example:

```python
# Inspect histogram by numerical column
df['sepal_length'].hist()

# Inspect histograms for all numerical columns
df.hist()

# Show all plots
plt.show()
```
Afterwards, use a Markdown cell to document your observations.

#### Step 7. Initial Data Distribution for Categorical Columns

Choose a categorical column and use df['column_name'].value_counts() to display the count of each category.
Use a loop to show the value counts for **all** categorical columns.

Jupyter Notebook / Python cell example:

```python
# Inspect value counts by categorical column
df['species'].value_counts()

# Inspect value counts for all categorical columns
for col in df.select_dtypes(include=['object', 'category']).columns:
    # Display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()

# Show all plots
plt.show()