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

#Install & Load Required Libraries
install.packages(c("readxl", "dplyr", "tidyr", "lubridate", "ggplot2", "janitor", “modeest”))
library(readxl)     # To read Excel files
library(dplyr)      # For data manipulation
library(tidyr)      # For data reshaping
library(lubridate)  # For date/time cleaning
library(janitor)    # For cleaning column names
library(modeest) # For Calculating mode
#Import Your Excel Files
# Read 2019 and 2020 data
data_2019 <- read_excel("C:\\Rproj\\data\\Divvy_Trips_2019_Q1.xlsx")
data_2020 <- read_excel("C:\\Rproj\\data\\Divvy_Trips_2020_Q1.xlsx")
#Clean column names
data_2019 <- data_2019 %>% clean_names()
data_2020 <- data_2020 %>% clean_names()
#Standardize column names
#Rename usertype to member_casual in 2019.
#Convert values for consistency (Subscriber → member, Customer → casual).
data_2019 <- data_2019 %>%
  rename(member_casual = usertype) %>%
  mutate(member_casual = case_when(
    member_casual == "Subscriber" ~ "member",
    member_casual == "Customer" ~ "casual",
    TRUE ~ member_casual
  ))
#Align columns between both datasets
#2019 has start_time and end_time
#2020 has started_at and ended_at
#Let's rename 2020 columns to match 2019:
data_2020 <- data_2020 %>%
  rename(
    start_time = started_at,
    end_time = ended_at
  )
#Add derived columns for both datasets
# Function to add derived fields
add_derived_fields <- function(df) {
  df %>%
    mutate(
      start_time = ymd_hms(start_time),
      end_time = ymd_hms(end_time),
      ride_length = as.numeric(difftime(end_time, start_time, units = "mins")),
      ride_year = year(start_time),
      ride_month = month(start_time, label = TRUE, abbr = TRUE),
      day_of_week = wday(start_time, label = TRUE),
      hour_of_day = hour(start_time)
    ) %>%
    filter(ride_length > 0, !is.na(ride_length))
}

# Apply to both datasets
data_2019 <- add_derived_fields(data_2019)
data_2020 <- add_derived_fields(data_2020)
# Safely merge both cleaned datasets
all_trips <- bind_rows(data_2019, data_2020)
# Export cleaned dataset to CSV for Tableau
write.csv(all_trips, "Cyclistic_cleaned_data.csv", row.names = FALSE)


Tableau Dashboard: https://public.tableau.com/app/profile/uchenna.abaah/vizzes

   
