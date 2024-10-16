# Titanicfinalproject
titanic_analysis for Excel
The purpose of analysis is to find the total number of survivors and non surivivors The average age of survivors and non survivors Creating visulaiztion the distribution of survivors Summary Cleaned the data by using filters to represent empty cells by yellow color Calculated average age of survivors and non survivors Calculated number of survivors by PClass Created bar charts and pie charts to view the distribution of survivors

Assume you have imported the dataset into a SQL database. Write SQL queries to answer the following questions: 1 )What is the total number of passengers? SELECT * FROM new_schema.titanic; SELECT COUNT(*) AS total_passengers FROM titanic

2)What percentage of passengers survived? SELECT* FROM new_schema.titanic; SELECT (SUM(Survived) * 100.0 / COUNT(*)) FROM titanic

3)How many passengers were in each class (Pclass)?

SELECT * FROM new_schema.titanic; SELECT Pclass, COUNT(*) AS COUNT FROM titanic GROUP BY Pclass

What was the average fare for survivors and non-survivors? survived, AVG(fare) AS average_fare FROM titanic GROUP BY survived;
SELECT survived, AVG(fare) AS average_fare FROM titanic GROUP BY survived;

Python

Basic Python Analysis Using Python, perform the following tasks: Load the dataset using pandas. Clean the data (similar to what you did in Excel).? Analyze the same metrics you did in SQL: Total number of passengers.? Percentage of survivors.? Average fare by survival status.? Output your findings to the console.

import pandas as pd

Load the dataset
df = pd.read_csv('titanic.csv')

Display the first few rows of the dataset
print("Initial Data:") print(df.head())

Data Cleaning
Check for missing values
print("Missing values in each column:") print(df.isnull().sum())

Drop rows with missing values in 'Age' and 'Embarked' columns
df_cleaned = df.dropna(subset=['Age', 'Embarked','Cabin'])

Check again Missing values are cleaned print(df.isnull().sum())

Total number of passengers
total_passengers = df.shape[0] print(total_passemgers)

Percentage of survivors
survival_percentage = df['Survived'].mean() * 100

Average fare by survival status
average_fare = df.groupby('Survived')['Fare'].mean()

Output findings
print(f'Total Passengers: {total_passengers}') print(f'Survival Percentage: {survival_percentage:.2f}%') print('Average Fare:\n', average_fare)
