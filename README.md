# cyclistic-capstone-project
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
