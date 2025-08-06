Cyclistic Bike-Share Capstone Project

Introduction/Overview

This capstone case study explores how Cyclistic bike-share users (annual members vs. casual riders) differ in their ride behavior and how data insights can help convert casual riders into members using digital marketing strategies.
The Cyclistic bike-share analysis case study is for a
fictional company, Cyclistic. In order to answer the
business questions, I followed the steps of the data analysis process: Ask, Prepare, Process,
Analyze, Share, and Act. 

Business Tasks

Goal:

Help Cyclistic's marketing team convert more casual riders into annual members by analyzing how different types of riders use the service.

Scenario/Background

As a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share
company in Chicago. The director of marketing believes the company’s future success
depends on maximizing the number of annual memberships. Therefore, my team wants to
understand how casual riders and annual members use Cyclistic bikes differently. From these
insights, my team will design a new marketing strategy to convert casual riders into annual
members. But first, Cyclistic executives must approve my recommendations, so they must be
backed up with compelling data insights and professional data visualizations.

Approach

i. Ask
   
Three questions will guide the future marketing program:

1. How do annual members and casual riders use Cyclistic bikes differently?

2. Why would casual riders buy Cyclistic annual memberships?
   
3. How can Cyclistic use digital media to influence casual riders to become members?

ii. Prepare

Data Source:

Two Excel datasets were used:

Divvy_Trips_2019.xlsx [https://docs.google.com/spreadsheets/d/1uCTsHlZLm4L7-ueaSLwDg0ut3BP_V4mKDo2IMpaXrk4/template/preview?resourcekey=0-dQAUjAu2UUCsLEQQt20PDA#gid=1797029090]

Divvy_Trips_2020.xlsx [https://docs.google.com/spreadsheets/d/179QVLO_yu5BJEKFVZShsKag74ZaUYIF6FevLYzs3hRc/template/preview#gid=640449855]

The data has been made available by Motivate International Inc. under this license [https://www.divvybikes.com/data-license-agreement].

iii. Process

Tools Used:

R/RStudio: For data cleaning, transformation, analysis

ggplot2 & dplyr: For data wrangling and visualization prep

Tableau Public: For creating visual dashboards

GitHub: For version control and project documentation

Data cleaning, exploration, & combining:

The two datasets were cleaned, merged, and transformed in RStudio into a single dataset all_trips. Key transformations included:

Creation of new fields: ride_length, ride_year, ride_month, day_of_week, hour_of_day

Conversion of ride duration to numeric minutes

Standardizing rider types as "member" and "casual"

Filtering out rides with negative durations or missing data

iv. Analyze

1.	Average Ride Length by Day of Week
   
Members take shorter, more consistent rides across weekdays.

Casual riders tend to take longer rides on weekends.

<img width="262" height="1038" alt="Average Ride Length by Member Type and Day of Week" src="https://github.com/user-attachments/assets/3189a9b5-0a48-4e1b-954f-d6d8b6c12f03" />

2.	Number of Rides by Day of Week
   
Members ride most during weekdays.

Casual riders ride more on weekends.

<img width="631" height="985" alt="Number of Rides by Day of Week" src="https://github.com/user-attachments/assets/7987fc28-bfa6-4196-b142-ddda2dc677cf" />

3. Monthly Trends (Jan–Mar due to available data)
   
Casual rider usage spikes during weekends even within the short observed period.

Membership usage remains relatively steady.

<img width="390" height="985" alt="Monthly Trend" src="https://github.com/user-attachments/assets/7c8c2ca3-abe1-41c5-a787-1a7ba2498025" />

v. Share

<img width="987" height="949" alt="Dashboard 1" src="https://github.com/user-attachments/assets/bd929289-7583-470a-8dff-10065e57c27f" />

Key Business Questions Answered (Key insights):

1. How do annual members and casual riders differ?
   
Members ride more frequently and on weekdays.

Casual riders prefer weekends and take longer trips.

Members likely use bikes for commuting; casual riders for leisure.

2. Why might casual riders become members?
   
Frequent or long-ride casual users would benefit from cost savings.

Riders who repeat usage may prefer flexibility and convenience of membership.

Environmental awareness or improved bike network may influence the shift.

3. How can digital media help convert casuals to members?
   
Use digital marketing to target high-frequency casuals.

Personalized emails showing monthly savings as a member.

Offer trial memberships or referral discounts via the mobile app.

Promote benefits using social media ads tailored to weekend riders.

Dashboard Link: [https://public.tableau.com/app/profile/uchenna.abaah/vizzes]

vi. Act
   
Conclusion & Recommendations:

To increase member conversions:

Offer weekend members discounts or loyallty points for frequent casual riders.

Promote membership benefits during peak summer periods.

Highlight faster checkout, customer service, and perks to casusl users.

Deploy app-based incentives: ride X times → get a discount code.

Use ride data to automate targeted campaigns (e.g., after 3 rides/month).

Files Delivered

Cleaned Dataset: Cyclistic_cleaned_data.csv

R Script: cyclistic_analysis.R

Tableau Dashboard: [https://public.tableau.com/app/profile/uchenna.abaah/vizzes]

   
