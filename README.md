# **MTA Delivery**

Jason Kim
April 2, 2021


## Abstract

My goal with this project was to utilize public MTA Turnstile data provided by the MTA to make observations in ridership during the months of November to January, across some of the most popular stations across New York City.

In addition, I aimed to discover which days these stations were the least utilized, on average. To achieve these goals, I used Python libraries, including pandas, to clean the data, as well as MatPlotLib and Seaborn to create visualizations.


## Design

The MTA Subway system is an incredibly extensive transportation network that spans the densely populated city of New York.

Swift & Secure would like to utilize this system to establish a holiday delivery service in areas with the highest used stations in New York. However, as they prioritize the speed and safety of their deliveries, they would like to know what days these stations are the least utilized during the months of November to January.

## Data

The MTA Turnstile data was extensive, and often difficult to wrangle.

There were several issues with the data, including the somewhat vague 'RECOVR AUD' classification, and the fact that the MTA collects ridership numbers cumulatively, and doesn't keep a day by day log.

The dataset itself contains the columns 'C/A', 'UNIT', 'SCP', 'STATION', 'LINENAME', 'DIVISION', 'DATE', 'TIME', 'DESC', 'ENTRIES', and 'EXITS', as seen [in this guide](http://web.mta.info/developers/resources/nyct/turnstile/ts_Field_Description.txt).

Because of the nature of my analysis, I chose to ignore several of these fields, and focused more on 'ENTRIES' and 'EXITS', as well as 'STATION', and 'TIME'.

The datasets themselves are accessible on the [MTA Turnstile Data page](http://web.mta.info/developers/turnstile.html).



## Tools & Algorithms
Python Libraries:
* Pandas & Numpy - Data manipulation & cleaning
* MatPlotLib & Seaborn - Data visualizations
* Datetime - For dates

SQLAlchemy & SQLite - Loading and manipulating data

Data Import:
* Download files from MTA database
* Combine files into a dataframe list
* Concatenate into single dataframe
* Use SQLAlchemy to create engine and database/database table

Data Cleaning & Manipulation:
* Utilize Pandas to remove redundant data
* Create dataframe within range December 2019 to January 2020
* Remove any NaN rows and drop RECOVR_AUD
* Obtain noncumulative values from cumulative 'ENTRIES'/'EXITS' columns
* Create Dataframes for:
  - Top 10 Stations by Entry & Exit numbers
  - Daily Entry & Exit numbers for each station for each month between December and January
  - Daily Average Entry & Exit Numbers for each station, for each month
  - Daily Average Entry & Exit Numbers for all top 10 station, for each month

## Communication
# Visualizations:
Top 10 Stations by Entry & Exit (Nov 2020-Jan 2019):

![Top_10_Entry_Dec_Jan](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/Top_10_Entry_Dec_Jan.png)
![Top_10_Exit_Dec_Jan](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/Top_10_Exit_Dec_Jan.png)

Daily Entries for Each Top 10 Station for Each Month:

![Top_10_Entry_Nov](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/November/Top_10_Entry_Nov.png)
![Top_10_Exit_Nov](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/November/Top_10_Exit_Nov.png)
![Top_10_Entry_Dec](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/December/Top_10_Entry_Dec.png)
![Top_10_Exit_Dec](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/December/Top_10_Exit_Dec.png)
![Top_10_Entry_Jan](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/January/Top_10_Entry_Jan.png)
![Top_10_Exit_Jan](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/January/Top_10_Exit_Jan.png)



Day of Week Average Entries & Exits for Each Top 10 Station For Each Month:

![Top_10_DayOfWeek_Entry_Nov](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/November/Top_10_DayOfWeek_Entry_Nov.png)
![Top_10_DayOfWeek_Exit_Nov](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/November/Top_10_DayOfWeek_Exit_Nov.png)
![Top_10_DayOfWeek_Entry_Dec](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/December/Top_10_DayOfWeek_Entry_Dec.png)
![Top_10_DayOfWeek_Exits_Dec](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/December/Top_10_DayOfWeek_Exits_Dec.png)
![Top_10_DayOfWeek_Entry_Jan](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/January/Top_10_DayOfWeek_Entry_Jan.png)
![Top_10_DayOfWeek_Exit_Jan](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/January/Top_10_DayOfWeek_Exit_Jan.png)

Day of Week Average Entries & Exits For All Top 10 Stations Combined for Each Month:

![DayOfWeek_Nov](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/November/DayOfWeek_Nov.png)
![DayOfWeek_Dec](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/December/DayOfWeek_Dec.png)
![DayOfWeek_Jan](https://github.com/Jason-HKim/MTA_EDA_Project/blob/main/Images/January/DayOfWeek_Jan.png)
