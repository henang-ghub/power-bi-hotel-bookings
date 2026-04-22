# power-bi-hotel-bookings
A centralised dashboard for a hotel chain providing actionable insights into booking trends, revenue generation, guest demographics, and operational efficiency

## Overview
This project presents an end-to-end data analytics solution for analysing hotel booking and guest data. Built using Power BI, the dashboard provides actionable insights into booking trends, revenue generation, customer demographics, and operational performance.

**Goal:** To support data-driven decision-making for improving hotel operations, marketing strategies, and customer experience.

## Business Problem
A luxury hotel chain needed a centralized reporting solution to:
*	Monitor revenue and booking performance 
*	Identify peak booking periods 
*	Understand customer behaviour and demographics 
*	Optimize marketing channels and partnerships 

**Dataset Description**

The dataset consists of two related tables:

**1. Guests Table**

*	Guest ID (Primary Key) 
*	Name 
* Age 
*	Demographic details 

**2. Bookings Table**
*	Booking ID (Primary Key) 
*	Guest ID (Foreign Key) 
*	Booking Date 
*	Check-in & Check-out Dates 
*	Room Type (Standard, Deluxe, Suite) 
*	Booking Status (Completed, Cancelled, Pending) 
*	Revenue 
*	Booking Source (Website, Travel Agent, Walk-in) 

**Relationship:** One-to-Many (One guest → Many bookings)

## Tools & Technologies
*	Power BI – Data visualization & dashboarding 
*	DAX (Data Analysis Expressions) – Calculated measures 
*	Excel / CSV / Power Query – Data preparation 
*	Data Modeling – Star schema design 




## Key Features

**Booking Insights**

*	Created a DAX measure to calculate the total revenue generated, offering a clear view of business profitability.
*	Developed a DAX measure to display the total number of "completed" bookings, providing a snapshot of overall performance.
*	Calculated the average duration (in days) for completed bookings to better understand guest stay patterns.

 **Booking Trends**
 	
*	Monthly booking trends:  Visualised monthly trends in the number of bookings (regardless of booking status) to identify busy periods and peak seasons, supporting resource allocation and operational planning.
  
**Room Type Analysis**
 	
*	Booking distribution by room type : Visualised the proportion (% and number) of bookings by room type (e.g., standard, deluxe, suite) regardless of booking status to identify guest preferences and prioritise high-demand offerings. 

**Booking Source Analysis**
 	
*	 Analysed the distribution of bookings across various sources (e.g., website, travel agents, walk-ins) to understand customer acquisition channels and inform targeted marketing efforts.

**Profitability Analysis**

*	 Identified the most profitable booking source for each room type to prioritise high-value channels and optimise partnerships.

**Demographic Analysis**

*	Visualised the proportion (% and number) of revenue by age category to identify the customer segments contributing most to revenue

**Detailed Booking Table**
 	
•	Created a full booking-level visibility table including: 

* Guest name 
*	Dates 
*	Room type 
*	Status 
*	Revenue
  
**Interactive Filters**

*	Enable filtering by booking date, booking source, and booking status to support tailored insights and decision-making.

## Key DAX Measures 

**Total Revenue Generated**

```

Total Revenue Generated (£) = SUM(Bookings[Sum of Revenue Generated])

```


**Total Completed Bookings**

```

Total Completed Bookings =
CALCULATE(
  COUNT('Bookings'[Booking Status]),
  'Bookings'[Booking Status] = "completed"
)

```

**Average Stay Duration Completed (Days)**

```

Average Stay Duration Completed (Days) =
CALCULATE(
  AVERAGEX(
    'Bookings', DATEDIFF('Bookings'[Check-in Date], 'Bookings'[Check-out Date], DAY)
  ),
  'Bookings'[Booking Status] = "Completed"
)

```

 ## Dashboard Insights and Recommendations
*	Provided a snapshot of key performance indicators for insightful decision making at a glance
*	Identified peak booking months, to help improving staff allocation and smooth out any bottleneck
*	Revealed most profitable booking channels, enabling targeted marketing eg better collaboration with Travel agents
*	Highlighted customer segments driving revenue. Focus marketing efforts on high revenue segments e.g up selling and tailoring content to appeal  to the 18-35 and 0ver 60 age groups
*	Improved visibility into room demand patterns
*	Insights enable Implementation of forward planning to allocate operational and marketing resources. 


## Future Improvements
*	Add forecasting models for booking trends 
*	Implement customer lifetime value (CLV) 
*	Connect to a SQL database 

⭐ If you found this project useful, feel free to star the repo!  Thank you!

 
