# 911-Calls-Capstone-Project
<img width="1691" height="910" alt="Screenshot 2026-01-13 104516" src="https://github.com/user-attachments/assets/78a839e2-1021-47c6-8110-bab3ea9ae38d" />
## Project Overview

This capstone project involves the analysis of 911 emergency call data from Montgomery County, Pennsylvania. The goal of the project is to explore, visualize, and gain insights from the 911 call dataset using Python and data science techniques. The project covers data cleaning, feature engineering, exploratory data analysis (EDA), and time-series analysis.

## Dataset

The dataset used in this project is sourced from [Kaggle](https://www.kaggle.com/mchirico/montcoalert) and contains 911 call records with the following fields:

| Column      | Description                                                                                 |
| ----------- | ------------------------------------------------------------------------------------------- 
| `lat`       | Latitude of the emergency call (string)                                                     
| `lng`       | Longitude of the emergency call (string)                                                    
| `desc`      | Description of the emergency call (string)                                                  
| `zip`       | Zipcode of the emergency call (string)                                                      
| `title`     | Title of the call, which includes a department code (EMS, Fire, or Traffic) and description 
| `timeStamp` | Date and time of the call (string, YYYY-MM-DD HH:MM:SS)                                     
| `twp`       | Township in which the call occurred (string)                                                
| `addr`      | Address of the call (string)                                                                
| `e`         | Dummy variable (always 1)                                                                   

## Project Objectives

1. Perform basic exploratory data analysis (EDA) on the 911 call data.
2. Identify patterns in 911 calls by zip code, township, and type of emergency.
3. Extract and analyze time-based features (hour, day, month) from timestamps.
4. Visualize the data using plots, countplots, line plots, and heatmaps.
5. Explore patterns of emergency calls over time and by department (Reason).

## Libraries Used

* `numpy` for numerical operations
* `pandas` for data manipulation and analysis
* `matplotlib` and `seaborn` for data visualization

## Analysis Steps

### 1. Data Import and Setup

* Imported the necessary libraries.
* Read the dataset CSV into a Pandas DataFrame called `df`.
* Checked basic information and the first few rows using `df.info()` and `df.head()`.

### 2. Basic Questions

* Identified the **top 5 zip codes** and **top 5 townships** for 911 calls.
* Determined the number of **unique title codes** in the dataset.

### 3. Creating New Features

* Extracted the **Reason** (EMS, Fire, Traffic) from the `title` column using `.apply()` and a lambda function.
* Determined the **most common reason** for a 911 call.
* Visualized the count of calls by Reason using a **Seaborn countplot**.

### 4. Time-based Analysis

* Converted the `timeStamp` column from string to datetime using `pd.to_datetime()`.
* Extracted **Hour**, **Month**, and **Day of Week** from the timestamp.
* Mapped the numeric Day of Week to string names (Mon–Sun).
* Created countplots for:

  * Calls by Day of Week, with hue by Reason.
  * Calls by Month, with hue by Reason.
* Addressed missing months by grouping by month and plotting a line chart of call counts.
* Applied a **linear fit** using Seaborn's `lmplot`.

### 5. Daily Call Analysis

* Created a new column `Date` from `timeStamp`.
* Grouped by Date and plotted the daily counts of 911 calls.
* Generated separate plots for each Reason (EMS, Fire, Traffic) over time.

### 6. Heatmaps and Clustermaps

* Restructured data with **Hours as columns** and **Day of Week as index** using `groupby` and `unstack()`.
* Generated a **HeatMap** and **ClusterMap** for calls by hour and day of the week.
* Repeated the process with **Months as columns** to observe monthly patterns.

### 7. Further Exploration

* Additional insights can be drawn by further slicing the data by Reason, Township, or Zip code.
* Additional visualizations can include geographical plots using latitude and longitude.

## Results and Insights

* **Top Zipcodes:** Identified areas with the highest 911 call frequency.
* **Top Townships:** Highlighted the most active townships for emergency calls.
* **Common Reasons:** EMS calls were the most frequent, followed by Fire and Traffic.
* **Time Patterns:** Calls peaked at certain hours and days of the week, and showed seasonal variations by month.
* **Visual Patterns:** Heatmaps and clustermaps revealed the busiest times for emergency calls visually.

## How to Run the Project

1. Clone the repository.
2. Install required libraries (if not already installed):

   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
3. Open the Jupyter Notebook (`911_calls_analysis.ipynb`) and run all cells.
4. Replace the CSV file path in the notebook with your local dataset location if needed.

## References

* [Kaggle: Montco Alert Dataset](https://www.kaggle.com/mchirico/montcoalert)
* [Pandas Documentation](https://pandas.pydata.org/docs/)
* [Seaborn Documentation](https://seaborn.pydata.org/)


## Author

 Halimat O. Abu
 abuhalimah1999@gmail.com
