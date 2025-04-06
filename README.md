# Cyclistic Bike-Share Analysis: Case Study

## Table of Contents
1. [Introduction](#introduction)
2. [Business Task](#business-task)
3. [Data Sources](#data-sources)
4. [Data Cleaning and Manipulation](#data-cleaning-and-manipulation)
5. [Analysis and Key Findings](#analysis-and-key-findings)
   - [Rider Distribution](#rider-distribution)
   - [Trip Duration](#trip-duration)
   - [Monthly Trends](#monthly-trends)
   - [Hourly Trends](#hourly-trends)
   - [Bike Type Preferences](#bike-type-preferences)
   - [Station Usage](#station-usage)
   - [Trip Start Locations](#trip-start-locations)
6. [Recommendations](#recommendations)
7. [Visualizations Summary](#visualizations-summary)
8. [Next Steps](#next-steps)

---

## Introduction
Cyclistic is a bike-share program based in Chicago, featuring over 5,800 bicycles and 600 docking stations. The program includes traditional bikes, electric bikes, and accessibility-friendly options such as hand tricycles and cargo bikes.

The program offers three pricing plans:
- Single-ride passes (casual riders)
- Full-day passes (casual riders)
- Annual memberships (Cyclistic members)

Annual members have been identified as significantly more profitable than casual riders. To increase profitability, Cyclistic aims to convert casual riders into annual members.

---

## Business Task
The primary goal is to identify behavioral differences between casual riders and annual members using Cyclistic's bike-share data. These insights will inform marketing strategies to increase the number of annual members.

### Analysis Questions
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

---

## Data Sources
The analysis uses Cyclistic’s publicly available historical bike trip data for the year 2023. The datasets were sourced from [Divvy Trip Data](https://divvy-tripdata.s3.amazonaws.com/index.html) under a public license agreement. The data does not contain personally identifiable information.

Key columns in the dataset:
- `ride_id`: Unique trip identifier
- `rideable_type`: Type of bike (classic, electric, docked)
- `started_at` and `ended_at`: Trip start and end timestamps
- `start_station_name` and `end_station_name`: Names of start and end stations
- `start_lat`, `start_lng`, `end_lat`, `end_lng`: GPS coordinates for stations
- `member_casual`: Rider type (casual or annual member)

---

## Data Cleaning and Manipulation
Data cleaning was performed using **SQL** and **R** to ensure accuracy and consistency.

### Steps Taken:
1. **Combined 12 monthly datasets** into a single dataset for streamlined analysis.
2. Removed duplicates and filtered out invalid entries (e.g., negative trip durations).
3. Addressed null values:
   - Rows with null `start_station_name` were removed for station-based visualizations, as their inclusion could lead to inaccurate insights.
   - The null rate for `start_station_name` was much higher for members (549,587 rows) compared to casual riders (326,129 rows), which may impact certain visualizations, particularly those involving station usage or trip start locations.
4. Current datasets lack unique IDs for individual riders, which limits the ability to analyze returning customers or track long-term usage trends. A suggestion for improvement is to assign **custom unique IDs** to each rider in future datasets. This would allow for better customer segmentation and analysis of customer retention.

---

## Analysis and Key Findings
### Rider Distribution
- Casual riders accounted for 64% of all trips, compared to 36% by annual members.
- Casual riders offer a significant opportunity for conversion to memberships.

![Member Vs Casual Rider Count](analysis_results/Member%20Vs%20Casual%20Rider%20Count.png)

---

### Trip Duration
- Casual riders took longer trips (27.74 minutes on average), reflecting leisure or recreational use.
- Members averaged 12.03 minutes per trip, consistent with commuting patterns.

![Average Riding Time by Rider Type](analysis_results/Average%20Riding%20Time%20by%20Rider%20Type.png)

---

### Monthly Trends
- Both groups showed peak ridership from March to August, with a steep decline during winter months.
- Casual riders showed a sharper decline in activity during winter, emphasizing seasonal dependence.

![Monthly Rider Counts by Membership Type](analysis_results/Monthly%20Rider%20Counts%20by%20Membership%20Type.png)

---

### Hourly Trends
- Members had peaks during commuting hours (8 AM and 5 PM), indicating regular workday use.
- Casual riders were most active midday and on weekends, suggesting leisure-driven use.

![Hourly Rider Counts by Membership Type](analysis_results/Hourly%20Rider%20Counts%20by%20Membership%20Type.png)

---

### Bike Type Preferences
- Electric bikes were the most popular choice for both groups, followed by classic bikes.
- **Docked bikes had the longest average trip duration but were the least used.** This suggests that users who did choose docked bikes likely needed them for extended trips where other bike types were unavailable.

![Rideable Type Usage by Membership and Rider Count](analysis_results/Rideable%20type%20Usage%20by%20Membership%20and%20Rider%20Count.png)

![Average Riding Time by Rideable Type](analysis_results/Average%20Riding%20Time%20by%20Rideable%20Type.png)

---

### Station Usage
- Casual riders used more unique stations (1,549) compared to members (1,455), reflecting dispersed travel patterns.
- Higher null rates for `start_station_name` among members may slightly skew station-related insights.

![Station Count by Rider Type](analysis_results/Station%20Count%20by%20Rider%20Type.png)

---

### Trip Start Locations
- Casual riders frequently began trips at recreational hotspots such as parks, beaches, and museums.
- Members started trips near residential and business districts, aligning with commuting behaviors.

![Trip Start Locations Members Vs. Casual Riders](analysis_results/Trip%20Start%20Locations%20Members%20Vs.%20Casual%20Riders.png)

---

## Recommendations
1. **Target Peak Seasons**  
2. **Introduce Seasonal Memberships**  
3. **Promote Electric Bikes**  
4. **Leverage Recreational Stations**  
5. **Investigate Docked Bike Appeal**  
6. **Implement Unique IDs for Riders**  

---

## Visualizations Summary
1. Member Vs Casual Rider Count  
2. Average Riding Time by Rider Type  
3. Monthly Rider Counts by Membership Type  
4. Hourly Rider Counts by Membership Type  
5. Station Count by Rider Type  
6. Rideable Type Usage by Membership and Rider Count  
7. Average Riding Time by Rideable Type  
8. Trip Start Locations Members Vs. Casual Riders   

---

## Next Steps
1. **Conduct Surveys**  
2. **Run A/B Testing**  
3. **Enhance Marketing at Hotspot Locations**  
4. **Analyze Membership Retention**  
5. **Enhance Data Collection Practices**  

---

## About This Project
This case study is part of the **Google Data Analytics Professional Certificate**. The goal was to apply the data analysis process to a real-world scenario, showcasing skills in data cleaning, analysis, visualization, and strategic recommendation.

For more details, view the [original datasets](https://divvy-tripdata.s3.amazonaws.com/index.html) or explore the project repository.

