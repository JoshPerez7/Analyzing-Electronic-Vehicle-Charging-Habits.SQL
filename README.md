# EV Charging Analysis

As electronic vehicles (EVs) become more popular, there is an increasing need for access to charging stations, also known as ports. To that end, many modern apartment buildings have begun retrofitting their parking garages to include shared charging stations. A charging station is shared if it is accessible by anyone in the building.

But with increasing demand comes competition for these ports — nothing is more frustrating than coming home to find no charging stations available! In this project, you will use a dataset to help apartment building managers better understand their tenants’ EV charging habits.

## Data

The data has been loaded into a PostgreSQL database with a table named `charging_sessions` with the following columns:

| Column            | Definition                                          | Data type |
|-------------------|-----------------------------------------------------|-----------|
| garage_id         | Identifier for the garage/building                  | VARCHAR   |
| user_id           | Identifier for the individual user                  | VARCHAR   |
| user_type         | Indicating whether the station is Shared or Private | VARCHAR   |
| start_plugin      | The date and time the session started               | DATETIME  |
| start_plugin_hour | The hour (in military time) that the session started| NUMERIC   |
| end_plugout       | The date and time the session ended                 | DATETIME  |
| end_plugout_hour  | The hour (in military time) that the session ended  | NUMERIC   |
| duration_hours    | The length of the session, in hours                 | NUMERIC   |
| el_kwh            | Amount of electricity used (in Kilowatt hours)      | NUMERIC   |
| month_plugin      | The month that the session started                  | VARCHAR   |
| weekdays_plugin   | The day of the week that the session started        | VARCHAR   |

## Objective

The objective of this project is to analyze data from shared EV charging stations in apartment building parking garages to provide valuable insights for building managers. The analysis aims to achieve the following goals:

1. **Determine Unique Users:** Identify the number of unique individuals using each garage’s shared charging stations.
2. **Identify Popular Charging Times:** Determine the top 10 most popular charging start times by weekday and start hour.
3. **Identify Long Duration Users:** Identify users whose average charging duration exceeds 10 hours at shared charging stations.

By achieving these goals, the project aims to help apartment building managers better understand their tenants' EV charging habits, improve resource allocation, and enhance the overall management of shared charging stations.

## Conclusion

In this project, we conducted an analysis of EV charging sessions data from shared charging stations in apartment building parking garages. The analysis focused on three main objectives:

1. **Determine Unique Users**: We extracted data from the `charging_sessions` table and filtered it to include only rows where `user_type` is 'Shared'. By grouping the data by `garage_id` and counting the number of unique `user_id` values, we identified that the garage with the highest number of unique users was `Bl2` with 18 unique users. This information can help building managers understand the usage patterns and demand for shared charging stations in different garages.

2. **Identify Popular Charging Times**: We retrieved records from the `charging_sessions` table and filtered them to include only rows where `user_type` is 'Shared'. By grouping the data by `weekdays_plugin` and `start_plugin_hour`, and counting the number of unique `user_id` values, we determined the top 10 most popular charging start times. The most popular charging start time was Sunday at 17:00 with 30 charging sessions. This insight allows building managers to recognize peak usage times and manage congestion effectively.

3. **Identify Long Duration Users**: We extracted data from the `charging_sessions` table and filtered it to include only rows where `user_type` is 'Shared'. By grouping the data by `user_id` and calculating the average `duration_hours`, we identified users whose average charging duration exceeds 10 hours. The user with the longest average charging duration was `Share-9` with an average of 16.85 hours. This information can help building managers address potential issues related to prolonged usage of shared charging stations and ensure fair access for all residents.

Overall, this project provided valuable insights into the charging habits of EV users in apartment buildings. These insights can help building managers make informed decisions to improve the availability and management of shared charging stations, enhancing the overall experience for EV owners and promoting the adoption of electric vehicles.

## Sources

- Data: [CC BY 4.0, via Kaggle](https://www.kaggle.com/)
- Image: [Julian Herzog, CC BY 4.0, via Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Electric_car_charging.jpg)


