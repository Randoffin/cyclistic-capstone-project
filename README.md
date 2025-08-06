Cyclistic Bike-Share Capstone Project

Introduction
This capstone case study explores how Cyclistic bike-share users (annual members vs. casual riders) differ in their ride behavior and how data insights can help convert casual riders into members using digital marketing strategies.
The Cyclistic bike-share analysis case study is for a
fictional company, Cyclistic. In order to answer the
business questions, I will follow the steps of the data analysis process: Ask, Prepare, Process,
Analyze, Share, and Act. 

Scenario/Background
As a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share
company in Chicago. The director of marketing believes the company’s future success
depends on maximizing the number of annual memberships. Therefore, my team wants to
understand how casual riders and annual members use Cyclistic bikes differently. From these
insights, my team will design a new marketing strategy to convert casual riders into annual
members. But first, Cyclistic executives must approve my recommendations, so they must be
backed up with compelling data insights and professional data visualizations.

Approach

1. Ask
Three questions will guide the future marketing program:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

2. Prepare
Data Source:
Two Excel datasets were used:

Divvy_Trips_2019.xlsx [https://docs.google.com/spreadsheets/d/1uCTsHlZLm4L7-ueaSLwDg0ut3BP_V4mKDo2IMpaXrk4/template/preview?resourcekey=0-dQAUjAu2UUCsLEQQt20PDA#gid=1797029090]

Divvy_Trips_2020.xlsx [https://docs.google.com/spreadsheets/d/179QVLO_yu5BJEKFVZShsKag74ZaUYIF6FevLYzs3hRc/template/preview#gid=640449855]

The data has been made available by Motivate International Inc. under this license [https://www.divvybikes.com/data-license-agreement].

3. Process
Tools Used

R/RStudio: For data cleaning, transformation, analysis

ggplot2 & dplyr: For data wrangling and visualization prep

Tableau Public: For creating visual dashboards

Data cleaning, exploration, & combining:
The two datasets were cleaned, merged, and transformed in RStudio into a single dataset all_trips. Key transformations included:
Creation of new fields: ride_length, ride_year, ride_month, day_of_week, hour_of_day
Conversion of ride duration to numeric minutes
Standardizing rider types as "member" and "casual"
Filtering out rides with negative durations or missing data

4. Analyze
Visualizations Built in Tableau Public
1.	Average Ride Length by Day of Week
Members take shorter, more consistent rides across weekdays.
Casual riders tend to take longer rides on weekends.
<img width="1024" height="600" alt="image" src="https://github.com/user-attachments/assets/650de02b-cc64-48e4-927b-38d45b878f05" />

3.	Number of Rides by Day of Week
Members ride most during weekdays.
Casual riders ride more on weekends.
<img width="1024" height="600" alt="image" src="https://github.com/user-attachments/assets/ec1e7208-ca68-4678-b92b-c32a16bd1ffe" />

3. Monthly Trends (Jan–Mar due to available data)
Casual rider usage spikes during weekends even within the short observed period.
Membership usage remains relatively steady.
<img width="1024" height="600" alt="image" src="https://github.com/user-attachments/assets/2ae45595-79a3-4e93-afb4-8023422807ea" />

5. Share
Key Business Questions Answered
1. How do annual members and casual riders differ?
Members ride more frequently and on weekdays.
Casual riders prefer weekends and take longer trips.
Members likely use bikes for commuting; casual riders for leisure.

3. Why might casual riders become members?
Frequent or long-ride casual users would benefit from cost savings.
Riders who repeat usage may prefer flexibility and convenience of membership.
Environmental awareness or improved bike network may influence the shift.

5. How can digital media help convert casuals to members?
Use digital marketing to target high-frequency casuals.
Personalized emails showing monthly savings as a member.
Offer trial memberships or referral discounts via the mobile app.
Promote benefits using social media ads tailored to weekend riders.
Dashboard Link: [https://public.tableau.com/app/profile/uchenna.abaah/vizzes]

7. Act
Recommendations
Analyze casual rider patterns to identify strong membership candidates.
Deploy app-based incentives: ride X times → get a discount code.
Use ride data to automate targeted campaigns (e.g., after 3 rides/month).

Files Delivered

Cleaned Dataset: Cyclistic_cleaned_data.csv

R Script: cyclistic_analysis.R

Tableau Dashboard: [https://public.tableau.com/app/profile/uchenna.abaah/vizzes]

   
