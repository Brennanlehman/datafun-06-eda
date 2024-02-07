# Project 6 Exploratory Data Analysis

_Overview_:
Project 6 is an opportunity to create your own custom exploratory data analysis (EDA) project using GitHub, Git, Jupyter, pandas, Seaborn and other popular data analytics tools.

_Objective_:
Perform and publish a custom EDA project to demnostrate skills with Jupyter, pandas, Seaborn and popular tools for data analytics. The notebook should tell a data story and visually present findings in a clear and engaging manner. 

_Data Set_: Titanic passenger data set will be used for this project

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