Cyclistic Bike-Share Capstone Project Report

Project Objective

This capstone project explores how Cyclistic bike-share users (annual members vs. casual riders) differ in their ride behavior and how data insights can help convert casual riders into members using digital marketing strategies.

Data Source

Two Excel datasets were used:

Divvy_Trips_2019.xlsx

Divvy_Trips_2020.xlsx

These were cleaned, merged, and transformed in RStudio into a single dataset all_trips. Key transformations included:
Creation of new fields: ride_length, ride_year, ride_month, day_of_week, hour_of_day
Conversion of ride duration to numeric minutes
Standardizing rider types as "member" and "casual"
Filtering out rides with negative durations or missing data

Tools Used

R/RStudio: For data cleaning, transformation, analysis

ggplot2 & dplyr: For data wrangling and visualization prep

Tableau Public: For creating visual dashboards

Visualizations Built in Tableau Public
1.	Average Ride Length by Day of Week
Members take shorter, more consistent rides across weekdays.
Casual riders tend to take longer rides on weekends.
2.	Number of Rides by Day of Week
Members ride most during weekdays.
Casual riders ride more on weekends.
Monthly Trends (Jan–Mar due to available data)
Casual rider usage spikes during weekends even within the short observed period.
Membership usage remains relatively steady.
Dashboard Link: https://public.tableau.com/app/profile/uchenna.abaah/vizzes

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

Recommendations

Analyze casual rider patterns to identify strong membership candidates.
Deploy app-based incentives: ride X times → get a discount code.
Use ride data to automate targeted campaigns (e.g., after 3 rides/month).

Files Delivered

Cleaned Dataset: Cyclistic_cleaned_data.csv
R Script: cyclistic_analysis_script.R
Tableau Dashboard: https://public.tableau.com/app/profile/uchenna.abaah/vizzes

   
