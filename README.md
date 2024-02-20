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




 
 # Report Snapshot (Power BI DESKTOP)

 
![Dashboard](https://github.com/alokrrbal/road-accident-analysis/assets/116140888/3e759d72-0db2-4673-bc09-1b18da0b6a87)

 # Report Recording
https://github.com/alokrrbal/road-accident-analysis/assets/116140888/cb4e9e8b-aea7-4175-96f8-1eeb741ce516

## Insights from Analysis:

1. **Casualties by Area:**
   - 38.05% of casualties occur in rural areas, while 61.95% occur in urban areas.

2. **Casualties by Light Condition:**
   - 73.84% of casualties occur in daylight, whereas 26.16% occur in dark conditions.

3. **Casualties by Road Type:**
   - Single carriageway roads account for 108,000 casualties, followed by dual carriageways with 21,000 casualties, roundabouts with 10,000 casualties, one-way streets with 3,000 casualties, and slip roads with 2,000 casualties.

4. **Casualties by Vehicle Type:**
   - Agricultural vehicles contribute to 399 casualties, bikes to 15,610 casualties, buses to 6,573 casualties, cars to 155,804 casualties, vans to 15,905 casualties, and other vehicle types to 1,446 casualties.

### Primary Key Numbers:
1. Total casualties in the current year amount to 195,700 with a year-over-year (YoY) growth of -11.9%.
2. The total number of accidents in the current year stands at 144,400, with a YoY change of -11.7%.
3. Fatal accidents in the current year total 1,500, with a YoY change of -35.6%.
4. Serious accidents in the current year amount to 18,800, with a YoY change of -16.6%.
5. Slight accidents in the current year total 124,100, with a YoY growth of -10.8%.

These insights provide valuable information regarding the distribution of casualties across different areas, light conditions, road types, and vehicle categories, along with key performance indicators highlighting the current status and trends in road accidents.


### Suggestions Based on Insights:

1. **Targeted Road Safety Campaigns:**
   - Develop targeted road safety campaigns focusing on rural areas to address the relatively high proportion of casualties occurring in these regions. These campaigns could include initiatives to improve road infrastructure, increase awareness about safe driving practices, and enhance emergency response capabilities in rural areas.

2. **Visibility Enhancement Measures:**
   - Implement measures to improve visibility on roads during nighttime, such as upgrading street lighting and promoting the use of reflective materials on vehicles and clothing. This could help reduce the number of accidents occurring in dark conditions.

3. **Infrastructure Upgrades:**
   - Prioritize infrastructure upgrades and safety improvements on single carriageway roads, which account for a significant number of casualties. This may involve widening roads, installing safety barriers, and implementing traffic calming measures to reduce the risk of accidents.

4. **Vehicle Safety Measures:**
   - Focus on promoting vehicle safety features and encouraging the adoption of safer vehicle types, particularly among high-risk categories such as motorcycles and agricultural vehicles. This could include awareness campaigns highlighting the importance of vehicle maintenance, seatbelt usage, and the benefits of advanced safety technologies.

5. **Continued Monitoring and Evaluation:**
   - Establish a framework for ongoing monitoring and evaluation of road safety initiatives to assess their effectiveness and identify areas for improvement. Regular data analysis and reporting can help track progress towards reducing casualties and inform future interventions.

6. **Community Engagement:**
   - Engage with local communities, stakeholders, and advocacy groups to raise awareness about road safety issues and foster a culture of responsible driving. Community-led initiatives and grassroots efforts can complement government-led interventions and contribute to long-term behavior change.

7. **Multi-Agency Collaboration:**
   - Strengthen collaboration among government agencies, law enforcement, emergency services, and transportation authorities to ensure a coordinated approach to road safety. Regular communication and joint efforts can lead to more effective enforcement, faster emergency response times, and better coordination of road infrastructure projects.
