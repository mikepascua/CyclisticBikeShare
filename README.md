## INTRODUCTION

Hello, I'm Mike, and I'm embarking on my first Data Analytics case study as part of my Google Data Analytics Professional Certification.  

In this case study, I serve as a junior data analyst on the marketing analytics team at Cyclistic - a bike-share company based in Chicago.  The marketing director believes that the company's future success depends on maximizing annual memberships.  To achieve this, our team aims to understand how casual riders and annual members utilize Cyclistic bikes differently.  

From these insights, we'll design a new marketing strategy to convert casual riders into annual members.  However, before implementing our recommendations, Cyclistic executives must approve them, so we need compelling data insights and professional data visualizations to backup our proposals.

![Cyclistic_Project](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/df7405af-5586-4b94-a7b0-91e205897879)

## ABOUT THE COMPANY

In 2016, Cyclistic introduced a successful bike-share program in Chicago, Illinois USA.  They now have a fleet of 5,824 bicycles, and a network of 692 stations across Chicago.  Bikes can be unlocked from one station and returned to any other station in the system anytime.

They have flexible pricing plans to choose from:  **single-ride passes**, **full-day passes**, **annual memberships**

For this analysis, we will refer to the bikers as:

* **Casual riders:**  single-ride and full-day passes
* **Annual members:**  Cyclistic's annual membership

## BUSINESS TASK

**Marketing Team's Goal:**  Design marketing strategies aimed at converting casual riders into annual members

**Business Tasks:**
* 1.)  How do annual members and casual riders use Cyclistic bikes differently?
* 2.)  Why would casual riders buy Cyclistic annual memberships?
* 3.)  How can Cyclistic use digital media to influence casual riders to become members?

**My Task:**  The team needs to better understand how annual members and casual riders use Cyclistic bikes differently.

## DATA SOURCES

The data was made available by **Motivate International Incorporated**, under this license <https://divvybikes.com/data-license-agreement>.

It consists of twelve months of trip data from **April 2023** to **March 2024.**  I could say that my data ROCCC!  It's reliable, accurate, and has unbiased info.  It's original, comprehensive, current, and cited.

![Source_Data](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/f3dae905-750f-4c30-bd10-fe2214a33de6)

## DATA CLEANING AND MANIPULATION

* Checked if all 12 months data have the same column names
* Checked the data type for each column name
* Formatted the cells by changing the column width, making the column names bold and centered
* Turned on filtering, and checked if there are blank or empty cells under the **ride_id** column
* ride_id field length is inconsistent.  Majority have 16 characters.  Cleaned the data by adding/removing trailing zeroes.
* Checked and removed duplicates under ride-id field.
* Some of the data have null values, particularly under the start_station_name, start_station_id, end_station_name, end_station_id, start_lat, start_lng,end_lat, and end_lng field names.  I removed these columns and did not include in my analysis.
* Sorted the data by the started_at column in ascending order.

**Added three additional columns or fields:**

* 1.)  **ride_length** (to determine the duration per ride, computed by deducting started_at from ended_at, and changed the format to hh:mm:ss)
* 2.)  **day_of_week** (to determine the number of users per day of the week, used the weekday function in Excel to compute this)
* 3.)  **ride_length_mins** (converted ride_length into minutes using the round function in Excel)

![Excel_SS_01](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/cd693fa7-6d0a-4d3a-bfcc-6c889f6d213c)

## ANALYSIS
​
For my analysis, I created an **aggregated data** file, used **pivot tables** and several **functions** in Excel, then I compared the results using **SQL** in BigQuery.
​
#### Data Aggregation

![Excel_SS_02](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/7a6fbf55-61aa-4567-8628-2a2c09a4f1ee)

![Excel_SS_03](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/044f5fee-04f4-435d-8310-c00635b8bfbe)

![Excel_SS_04](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/46668c3b-2fef-4718-9ed7-7aabd0e05544)

#### SQL Query

![SQL_SS_01](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/2a060e45-36a3-4ad8-a3b5-8f6e13bb124d)

### Total Bike Rides for the Year (April 2023 - March 2024)

![Powerpoint_SS_01](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/e4203f61-62b5-4c5b-a817-0cfc96c97537)

### Annual Bike Rides (per user)

The majority of bike rides were taken by annual members, at 3.68 million or 64%.

![Powerpoint_SS_02](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/1227396d-328f-4c19-8078-4cbd7df2aeaa)

### Monthly Bike Rides (per user)

* During spring through the end of summer, both annual members and casual riders had the most number of bike rides (March to August).
* As fall and winter arrived, the frequency of bike rides for both users decreased (September to February)

![Powerpoint_SS_03](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/5307b4d9-f3e0-4565-8d96-3b30c2fcbae7)

### Bike Rides (per day of week)

* It's evident that casual riders exhibit a weekend preference.
* On the other hand, annual members predominantly utilize bikes during weekdays, while the trend decreases on weekends.

![Powerpoint_SS_04](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/df046536-6829-4e43-8ef4-fa73650e4762)

### Rideable Bike Preference

* A greater number of annual members opt for classic bikes over electric bikes.  Interestingly, none of them used any docked bikes.
* Among casual riders, electric bikes are the preferred choice most of the time.
* There was no utilization of docked bikes for both users starting September 2023.

![Powerpoint_SS_05](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/2df4ddb9-537a-43ea-9255-f6cdef097622)

### Average Ride Length (in minutes)

Casual riders, on average, have longer bike usage, compared to annual members.

![Powerpoint_SS_06](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/b0d5d73e-cc07-4e06-bd35-02a11f5761e0)

### Monthly Average Ride Length (in minutes)

* During spring and summer, casual riders tend to ride their bikes for longer duration.  However, as fall and winter arrive, their riding time decreases.
* In contrast, annual members consistently use bikes for an average duration of  10 to 13 minutes all throughout the year.

![Powerpoint_SS_07](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/ea8e1b7f-39d8-4a6f-add4-3de727d72856)

### Average Ride Length (per day of week)

* Both casual riders and annual members tend to ride their bikes for longer duration on weekends.
* Most probably, casual riders use their bikes for leisure, perhaps visiting tourist spots on weekends.
* While annual members use it consistently for 11 to 12 minutes on weekdays, probably for work, and a mix of leisure and practical errands during weekends.

![Powerpoint_SS_08](https://github.com/mikepascua/CyclisticBikeShare/assets/170308027/dd34c1d0-707c-4b68-9369-bd9c245ab378)

## KEY FINDINGS

* Majority of bike rides were done by annual members at 64%.
* Both annual members and casual riders had the most number of bike rides during spring through the end of summer.  As fall and winter arrived, it decreased.
* Most casual riders used the bikes on weekends.  While annual members mostly used it on weekdays.
* Casual riders preferred electric bikes, while annual members still opted for classic bikes.
* On average, casual riders had longer bike usage, compared to annual members.
* Casual riders tend to ride their bikes for longer duration during spring and summer.  While annual members had consistently used the bikes for 10 - 13 minutes on average, all throughout the year.
* Both casual riders and annual members spent longer duration on bike rides during weekends (Saturday and Sunday).

## RECOMMENDATIONS

* Design a **Bikers Loyalty Program** for annual members to reward them for their ongoing engagement with Cyclistic.  They can earn points by using the bikes longer, which they can redeem for discounts or extra ride minutes or hours in their next ride.
* Design year-round **bike ride promotions** for annual members, with a special focus on weekend rides.
* Revisit **pricing plans** for annual members, and add extra minutes/hours in corresponding plan packages.















