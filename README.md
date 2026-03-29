# Analysing Smart City Bike Sharing Data using Power BI

## 📖 Table of Contents
* [📖 Project Overview](#-project-overview)
* [📊 Data Source](#-data-source)
* [🛠️ Tools & Technologies](#-tools--technologies)
* [🧹 Data Cleaning & Preparation](#-data-cleaning--preparation)
* [🔍 Exploratory Data Analysis (EDA)](#-exploratory-data-analysis-eda)
* [💡 Key Insights and Recommendations](#-key-insights-and-recommendations)
* [🏁 Conclusion](#-conclusion)

## 📊 Project Overview

This project involves cleaning, transforming, and analysing raw data and creating an interactive Power BI dashboard to derive meaningful business insights.

## Project Objective

The main objectives of this project are:

• Determine which cities have the highest System Imbalance Scores, indicating poor bike distribution efficiency.

•	Pinpoint geographic clusters where stations are consistently "Critical: Empty" or "Critical: Full," preventing users from renting or returning bikes.

•	 Identify "outlier" stations where the number of stands significantly exceeds the number of available bikes, leading to wasted infrastructure.

•	Use data to prioritize which cities require manual bike redistribution to move the network from a "Critical" state back to a "Balanced" state.


## 🗂️ Data Source
• Source: Web scrapping

• Size: 382 KB

• Key Variables: Station number, Station, Station Address, Latitude, Longitude, Banking, Bonus, Status, City, Bike Stands, Available Bike Stands, Available Bikes, Last Update date, Last update Time, Station Status and Station Size.

## 🛠️ Tools & Technologies

- **Visualization:**
- 
  **Power BI**
  - Data modelling
  - DAX calculations
  - visualization and
  - Interactive dashboard creation.
- **Documentation:** MS-Word.

## 🧹 Data Cleaning & Preparation

**Tasks Performed:**

•	**Data Cleaning & Transformation:** Handled missing values, standardized formats, and created calculated fields.

•	**Filtering & Sorting:** Organized data to focus on relevant records.

•	Converted the data into Fact and Dimension Table.

•	Separated the Name column with number to unique texts.

•	Replaced the null values in address column with the names in Name column.

• Separated Latitude and Longitude column using Delimiter.

•	Separated Date and Time using Delimiter.

## Calculated Columns:

•	Created Station Status column to check whether a bike station is currently available for public use or restricted due to maintenance or system issues.

  **Dax Formula** Station_Status = switch(true(),
  Feuil1[Available Bikes]=0,"Critical: Empty", Feuil1[Available Bike Stands]=0, "Critical:Full", Feuil1[Available Bikes]           <=2,"Low Stock","Healthy")

•	Created Station size column to group stations based on their total physical capacity (Total Bike Stands).

  **Dax Formula** Station_Size = if(Feuil1[Bike Stands] >30, "Large", if(Feuil1[Bike Stands] >15, "Medium", "Small"))

## 🔍 Exploratory Data Analysis (EDA)

•	The key insight from the Geographic Distribution of Station Status map is that system imbalance is highly localized, with significant "Critical: Empty" (red) and "Critical: Full" (orange) clusters across Europe.

•	This reveals that cities like Seville and regions in France face severe service gaps, requiring targeted bike redistribution to move the network back to a "Healthy" green state.

•	The Station Status by Count of Stations chart reveals that nearly 30% of the network is currently in a "Critical" state, with 24.68% (705 stations) being completely empty and unable to serve users.

•	While over half the network remains "Healthy," the significant volume of empty and low-stock stations suggests a major need for bike redistribution to maintain service availability.

• The System Imbalance Score by City chart reveals a massive performance gap between contracts, with Jcdecauxbike (65) and Lund (53) being the most inefficient. 

•	In contrast, cities like Rouen, Vilnius, and Marseille maintain nearly perfect balance with scores between 0 and 2, setting the benchmark for operational excellence in the network.

•	The Station Status Breakdown by Station Size chart reveals that Small stations are the most vulnerable to inventory issues, with nearly 40% reaching a "Critical: Empty" state.

•	In contrast, Large stations maintain the highest efficiency, with over 75% of stations remaining in a "Healthy" operational status.


<img width="1189" height="668" alt="image" src="https://github.com/user-attachments/assets/1ad22302-79c4-4a06-bd28-582cd679eb85" />





<img width="1193" height="667" alt="image" src="https://github.com/user-attachments/assets/19571d18-595a-4d69-926e-f677d09757c9" />


## 💡 Key Insights and Recommendations

•	Approximately 30% of the global network is in a "Critical" state, with 24.68% of stations being completely empty.

•	There is a massive performance gap between cities; Marseille and Rouen maintain near-perfect balance (Score 0–2), while Jcdecauxbike and Lund suffer from extreme inefficiency (Score 53–65).

•	Small stations are the most fragile, with a 40% Critical: Empty rate, whereas Large stations are the most stable, with 75% remaining "Healthy".

•	The scatter plot identifies significant "Overbuilt" outliers—stations with over 130 stands but fewer than 60 bikes available.

•	Prioritize rebalancing efforts in cities with an Imbalance Score above 40 to move bikes from "Full" outliers to "Empty" clusters.

•	For Small stations with high empty rates, consider physical expansion or implementing "Bonus" incentives to encourage users to return bikes to those specific locations.


## Conclusion

• The integration of Power BI proved effective for end-to-end data analysis, from raw data to visual reporting.


