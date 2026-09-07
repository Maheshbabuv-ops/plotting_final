# # Exp 6 Analysis and Visualization of COVID-19 Dataset using Python

NAME : MAHESHBABU V

REG NO : 212225230166


## AIM:

To analyse a large real-world COVID-19 dataset using Python and visualize key trends and relationships using multiple types of graphs for meaningful insights.

## DESIGN STEPS:

### Step 1:

Clone the repository from GitHub.

### Step 2:

Create a Python project in the preferred IDE (VS Code/PyCharm/Jupyter Notebook).

### Step 3:

Create the Python program for analysing and visualizing the COVID-19 dataset using **Pandas** and **Matplotlib** libraries.

### Step 4:

Load the **`covid_cases.csv`** dataset using Pandas and explore the dataset by displaying its shape and column names.

### Step 5:

Check and handle missing values in the dataset, if any.

### Step 6:

Perform basic data exploration by finding the total number of records and generating the statistical summary using the `describe()` function.

### Step 7:

Use Matplotlib to create different visualizations:

* **Line Graph:** Trend of confirmed cases over time globally.
* **Bar Chart:** Top 10 countries by total confirmed cases.
* **Pie Chart:** Case distribution of the top 5 affected countries.
* **Scatter Plot:** Relationship between confirmed cases and deaths.
* **Histogram:** Distribution of active cases.

### Step 8:

Add appropriate titles, axis labels, legends, and other necessary labels to the graphs.

### Step 9:

Execute the program and analyze the generated visualizations to identify meaningful trends and relationships in the COVID-19 dataset.

## PROGRAM:
```
from google.colab import files
uploaded = files.upload()
import pandas as pd
import matplotlib.pyplot as plt

# Load dataset
data = pd.read_csv("covid_case.csv")

# Display basic information
print("First 5 rows:")
print(data.head())

print("\nDataset Shape:")
print(data.shape)

print("\nColumn Names:")
print(data.columns)

# Check missing values
print("\nMissing Values:")
print(data.isnull().sum())

# Remove missing values
data = data.dropna()

# Convert Date column to datetime
data['Date'] = pd.to_datetime(data['Date'])

# Total number of records
print("\nTotal Records:", len(data))

# Statistical summary
print("\nStatistical Summary:")
print(data.describe())

# Line Graph: Global confirmed cases over time
global_cases = data.groupby('Date')['Confirmed'].sum()

plt.figure()
plt.plot(global_cases.index, global_cases.values)
plt.title("Global Confirmed COVID-19 Cases Over Time")
plt.xlabel("Date")
plt.ylabel("Confirmed Cases")
plt.show()

# Bar Chart: Top 10 countries by confirmed cases
top10 = data.groupby('Country')['Confirmed'].sum().sort_values(ascending=False).head(10)

plt.figure()
top10.plot(kind='bar')
plt.title("Top 10 Countries by Confirmed Cases")
plt.xlabel("Country")
plt.ylabel("Confirmed Cases")
plt.show()

# Pie Chart: Top 5 affected countries
top5 = data.groupby('Country')['Confirmed'].sum().sort_values(ascending=False).head(5)

plt.figure()
plt.pie(top5, labels=top5.index, autopct='%1.1f%%')
plt.title("Top 5 Countries Case Distribution")
plt.show()

# Scatter Plot: Confirmed vs Deaths
plt.figure()
plt.scatter(data['Confirmed'], data['Deaths'])
plt.title("Confirmed Cases vs Deaths")
plt.xlabel("Confirmed Cases")
plt.ylabel("Deaths")
plt.show()

# Histogram: Distribution of active cases
plt.figure()
plt.hist(data['Active'], bins=20)
plt.title("Distribution of Active Cases")
plt.xlabel("Active Cases")
plt.ylabel("Frequency")
plt.show()
```
## OUTPUT:

<img width="892" height="995" alt="image" src="https://github.com/user-attachments/assets/837b909e-5d9c-4c21-ad1e-2e6a5c0e3df4" />
<img width="800" height="557" alt="image" src="https://github.com/user-attachments/assets/1f1bee2d-3954-40ae-a37e-3084cdc54170" />
<img width="830" height="636" alt="image" src="https://github.com/user-attachments/assets/e382a838-2420-407d-a6fd-4cf69b13b5d3" />
<img width="675" height="510" alt="image" src="https://github.com/user-attachments/assets/2463e342-df10-45fb-889a-a8448fa4f753" />
<img width="881" height="580" alt="image" src="https://github.com/user-attachments/assets/ce7dfdc2-7617-4846-8b06-e5ef4b422575" />
<img width="793" height="557" alt="image" src="https://github.com/user-attachments/assets/7499e98c-cb3f-4d36-9066-581687a3a3da" />







## RESULT:

The COVID-19 dataset was successfully analysed using Python. The dataset was explored using Pandas, and meaningful trends and relationships were visualized using different types of graphs such as line graph, bar chart, pie chart, scatter plot, and histogram using Matplotlib.
