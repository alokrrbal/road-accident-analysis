# Road Accident Analysis 

<!-- ### Dashboard Link : https://app.powerbi.com/groups/me/reports/384d017e-e935-44dc-9e7d-1626c1a36de1/ReportSection -->

### Problem Statement:

The Ministry of Transport, in collaboration with various stakeholders including the Road Transport Department, Police Force, Emergency Services Department, Road Safety Corps, Transport Operators, Traffic Management Agencies, Public, and Media, seeks to gain comprehensive insights into road accidents for the years 2021 and 2022. The objective is to create a Road Accident Dashboard that provides essential metrics and trends to enhance decision-making and promote road safety initiatives.

### Key Requirements:

- **Primary KPIs:** Develop metrics for total casualties and total accidents for the current year and year-over-year growth to gauge the overall road safety situation.
  
- **Accident Severity Analysis:** Highlight total casualties categorized by accident severity for the current year and compare with the previous year to identify trends and areas of improvement.
  
- **Vehicle Type Analysis:** Analyze total casualties concerning vehicle types to understand the impact of different vehicle categories on road accidents.
  
- **Monthly Trend Comparison:** Visualize the monthly trend of casualties for the current year and the previous year to identify seasonal variations and inform targeted interventions.
  
- **Road Type Analysis:** Break down casualties by road types to identify high-risk areas and prioritize safety measures accordingly.
  
- **Location and Time Analysis:** Provide insights into casualties based on area/location and day/night occurrences to pinpoint hotspots and inform resource allocation.
  
- **Geographical Overview:** Present total casualties and accidents by location to facilitate targeted interventions and resource allocation across regions.

### Stakeholders:

1. **Ministry of Transport:** Utilizes insights from the dashboard to formulate road safety policies and initiatives.
  
2. **Road Transport Department:** Uses the dashboard to enhance road infrastructure planning and maintenance strategies.
  
3. **Police Force and Emergency Services Department:** Leverages data from the dashboard for effective emergency response planning and accident investigation.
  
4. **Road Safety Corps:** Implements targeted road safety campaigns and interventions based on the dashboard insights.
  
5. **Transport Operators:** Incorporates dashboard insights into driver training programs and fleet management practices to reduce accident risks.
  
6. **Traffic Management Agencies:** Utilizes dashboard data for traffic management strategies and infrastructure improvements.
  
7. **Public:** Accesses the dashboard to stay informed about road safety issues and make informed decisions while traveling.
  
8. **Media:** Utilizes dashboard insights to raise awareness about road safety issues and promote community engagement in road safety initiatives.


### Steps for Road Accident Analysis in Power BI:

1. **Load Data and Create Calendar Table:**
   - Load the road accident data into Power BI Desktop from an Excel file.
   - Create a new table called "Calendar" using Power Query Editor.
   - Extract three columns from the "Accident Date" column: Date, Year, and Month.
   - Use the following formulas to create the columns:
     - Date: `Calendar = CALENDAR(MIN(Data[Accident Date]),MAX(Data[Accident Date]))`
     - Year: `Year = YEAR('Calendar'[Date])`
     - Month: `MONTH = FORMAT('Calendar'[Date],"mmm")`
   - Connect the Calendar table with the main data table using the "Accident Date" column.

2. **Primary KPI - Total Casualties:**
   - Create a new measure named "CY Casualties" to calculate the total casualties for the current year.
     - Formula: `CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]),'Calendar'[Date])`
   - Calculate the total casualties for the previous year using a measure named "PY Casualties".
     - Formula: `PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]),SAMEPERIODLASTYEAR('Calendar'[Date]))`
   - Calculate the year-over-year growth in casualties using a measure named "YoY Casualties".
     - Formula: `YoY Casualties = ([CY Casualties] - [PY Casualties])/[PY Casualties]`

3. **Primary KPI - Total Accidents:**
   - Create a new measure named "CY Accident Count" to calculate the total number of accidents for the current year.
     - Formula: `CY Accident Count = TOTALYTD(COUNT(Data[Accident_Index]),'Calendar'[Date])`
   - Calculate the total number of accidents for the previous year using a measure named "PY Accident".
     - Formula: `PY Accident = CALCULATE(COUNT(Data[Accident_Index]),SAMEPERIODLASTYEAR('Calendar'[Date]))`
   - Calculate the year-over-year growth in accidents using a measure named "YoY Accidents".
     - Formula: `YoY Accidents = ([CY Accident Count] - [PY Accident] ) / [PY Accident]`


# Snapshot of Dashboard (Power BI Service)

![dashboard_snapo](https://user-images.githubusercontent.com/102996550/174096257-11f1aae5-203d-44fc-bfca-25d37faf3237.jpg)

 
 # Report Snapshot (Power BI DESKTOP)

 
![Dashboard_upload](https://user-images.githubusercontent.com/102996550/174074051-4f08287a-0568-4fdf-8ac9-6762e0d8fa94.jpg)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total Number of Customers = 129880

   Number of satisfied Customers (Male) = 28159 (21.68 %)

   Number of satisfied Customers (Female) = 28269 (21.76 %)

   Number of neutral/unsatisfied customers (Male) = 35822 (27.58 %)

   Number of neutral/unsatisfied customers (Female) = 37630 (28.97 %)


           thus, higher number of customers are neutral/unsatisfied.
           
### [2] Average Ratings

    a) Baggage Handling - 3.63/5
    b) Check-in Service - 3.31/5
    c) Cleanliness - 3.29/5
    d) Ease of online booking - 2.88/5
    e) Food & Drink - 3.21/5
    f) In-flight Entertainment - 3.36/5
    g) In-flight service - 3.64/5
    h) In-flight Wifi service - 2.81/5
    i) Leg room service - 3.37/5
    j) On-board service - 3.38/5
    k) Online boarding - 3.33/5
    l) Seat comfort - 3.44/5
    m) Departure & arrival convenience - 3.22/5
  
  while calculating average rating, null values have been ignored as they were not relevant for some customers. 
  
  These ratings will change if different visual filters will be applied.  
  
  ### [3] Average Delay 
  
      a) Average delay in arrival(minutes) - 15.09
      b) Average delay in departure(minutes) - 14.71
Average delay will change if different visual filters will be applied.

 ### [4] Some other insights
 
 ### Class
 
 1.1) 47.87 % customers travelled by Business class.
 
 1.2) 44.89 % customers travelled by Economy class.
 
 1.3) 7.25 % customers travelled by Economy plus class.
 
         thus, maximum customers travelled by Business class.
 
 ### Age Group
 
 2.1)  21.69 % customers belong to '0-25' age group.
 
 2.2)  52.44 % customers belong to '25-50' age group.
 
 2.3)  25.57 % customers belong to '50-75' age group.
 
 2.4)  0.31 % customers belong to '75-100' age group.
 
         thus, maximum customers belong to '25-50' age group.
         
### Customer Type

3.1) 18.31 % customers have customer type 'First time'.

3.2) 81.69 % customers have customer type 'returning'.
       
       thus, more customers have customer type 'returning'.

### Type of travel

4.1) 69.06 % customers have travel type 'Business'.

4.2) 30.94 % customers have travel type 'Personal'.

        thus, more customers have travel type 'Business'.
