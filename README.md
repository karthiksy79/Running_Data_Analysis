
---
# 🏃‍♂️ **Running Data Analysis** 📊

Welcome to my **Running Data Analysis** project! It includes various visualizations that track performance metrics over time, helping to identify trends, monitor progress, and optimize training. The dashboard provides insights into key aspects of running such as distance, time, pace, heart rate, and elevation, with comparisons across different years.

[**Running Data Analysis Dashboard**](https://public.tableau.com/views/KSRuns/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)


---
## **Project Overview🛠**

This project focuses on providing a detailed analysis of running data with the goal of tracking progress and performance improvements over time. The key features of this project include:

 **1.** 🏃‍♀️ Run Count: Total number of runs completed.

 **2.** 📅 Yearly Runs: A breakdown of runs by year to assess consistency.

 **3.** ⏱️ Average Speed & Heart Rate: Analyze pace and heart rate across runs to monitor fitness.

 **4.** ⛰️ Elevation Gain Comparison: Compare elevation gain between different years to track the difficulty of your runs.

 **5.** 🗓️ Time and Distance Comparison: View total time and distance run for a given year to monitor endurance and volume.

The raw data was cleaned and prepared using MySQL to ensure accuracy before importing it into Tableau for further visualization and analysis.

---
## **Data Cleaning & Preparation with MySQL 🛠️**

Before visualizing the data in Tableau, I performed several essential data cleaning and preparation steps using **MySQL**. Here's a summary of the steps taken:

### 1. **Removing Null Values** ❌

* **Problem**: The raw dataset contained missing values for critical columns like distance, time, and heart rate.
* **Solution**: I removed rows where key fields like distance or time were null to maintain data integrity and ensure reliable analysis.

```sql
DELETE FROM running_data
WHERE distance IS NULL OR time IS NULL;
```

### 2. **Standardizing Units** ⚙️

* **Problem**: The dataset contained mixed units (e.g., kilometers and miles, hours and minutes).
* **Solution**: I standardized the units across all entries. Distance was converted to **kilometers** and time was converted to **minutes**, ensuring all data points are comparable.

```sql
UPDATE running_data
SET distance = distance * 1.60934,  -- Convert miles to kilometers
    time = time * 60;  -- Convert hours to minutes
```

### 3. **Filtering Relevant Activities** 🎯

* **Problem**: The dataset included multiple types of activities (e.g., cycling, walking) that were not relevant to the running analysis.
* **Solution**: I filtered out all activities except "Running" to focus only on the relevant data.

```sql
DELETE FROM running_data
WHERE activity_type NOT IN ('Running');
```

Once the data was cleaned and standardized, I exported it into a CSV file and imported it into Tableau for analysis.

---

## **Key Features**

### 1. **Run Count & Yearly Runs**

* Track the total number of runs and see a breakdown by year. This visualization helps measure consistency and long-term progress in a running routine.

### 2. **Average Speed & Heart Rate**

* Visualize average pace and heart rate over time to evaluate improvements in both cardiovascular fitness and running efficiency.

### 3. **Elevation Gain Comparison**

* Compare the total elevation gain year-over-year to assess the difficulty of running routes. This is particularly useful for tracking changes in terrain and elevation.

### 4. **Time and Distance for Each Year**

* View the total time and distance run for each year to track endurance and running volume over time.

### 5. **Monthly Trends**

* Monitor running frequency over months and weeks, helping to identify seasonal patterns or fluctuations in training habits.

---

## **Visualization**  

<img width="1701" height="1018" alt="34" src="https://github.com/user-attachments/assets/f9cd3e16-0298-4df4-a415-10e4a907cb11" />


---


## **Technologies Used**

* **MySQL**: For data cleaning, including removing null values, standardizing units, and filtering relevant activities.
* **Tableau**: For creating interactive visualizations and dashboards.
* **Excel**: The cleaned dataset is exported into CSV format, which is then imported into Tableau for analysis.

## **License**

This visualization is published on Tableau Public and is available for public viewing and interaction. The content of this visualization is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).

