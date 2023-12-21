# SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS

Renowned hospitality company SHG aims to improve visitor experiences and streamline corporate processes by utilizing data-driven insights. Your task is to thoroughly examine one of our best resorts' past booking data to identify trends, comprehend consumer behavior, and offer useful suggestions for tactical decision-making.

![SGH image](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/e58641f8-462a-4a78-a982-b66703ae5156)


### Project Overview

Your task involves a thorough analysis of a comprehensive dataset, featuring intricate details of bookings, guest demographics, distribution channels, and financial metrics. By applying your analytical prowess, we aim to extract meaningful insights that will not only inform operational improvements but also contribute to the overall success of SHG in delivering unparalleled hospitality.

### Objectives of the Analysis

- What are the Booking Patterns
- Do Customer Behavior Analysis
- Conduct Comprehensive Cancellation Analysis
- Revenue Optimization/Analysis
- Do Geographical Analysis
- What is the Operational Efficiency
- What is the Impact of Deposit Types
- Analysis of Corporate Bookings
- Time-to-Event Analysis
- Comparison of Online and Offline Travel Agents

### Tools and Technologies

Power BI — Used For Data Cleaning, Transformation, Analysis and Creating Reports.

### Data Source

Find the Dataset [here](https://docs.google.com/spreadsheets/d/1gG5k2a7by4yDz4byNOkR4-xIPhdaYgF7/edit?usp=drive_link&ouid=115729712207610806012&rtpof=true&sd=true)

### Data Cleaning and Preparation

Transformation Process

After loading the table to the Power Query editor, I discovered it has about 119,390 rows and 18 columns with some column headers such as Booking ID, Hotel, Booking Date, Arrival Date, Lead Time, Nights, Guests, etc. 
- I deleted (Removed) the last column from the table because it was empty
- Next, I formatted the “AVG Daily Rate” column that was formatted as TEXT to number by first removing the “$” signs. 
- I did the same with the “Cancelled (1/0)” column, though this has no “$” sign. 
- Lead Time, Night, Guests, Revenue, and Revenue Loss columns were also reformatted using the same process above.
- I created a = "Status Update" column using a custom column to enable my analysis of patterns in check-out dates


![SGH sources](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/b556393e-4096-493c-90fb-386760f452e5)


### Exploratory Data Analysis (EDA)

With the help of statistical graphics and other data visualization methods, I have generated the following key Performance Indicators (KPIs) and insights

- Average Lead Time
- Average Length of Stay
- AVG Daily Rate (ADR)
- Cancellation Rate
- Guests Per Booking
- Net Revenue
- Occupancy Rate
- Rev. from Completed Bookings
- Rev. Loss from Cancelled Bookings
- Rev. PAR
- Total Bookings
- Count of Booking Date by Distribution Channel
- AVG Daily Rate (ADR) by Distribution Channel
- Cancellation Rate and Sum of Revenue Loss by Customer Type
- Sum of Lead Time by Customer Type and Distribution Channel
- Sum of Guests and Sum of Revenue by Country
- Sum of Revenue by Customer Type
- AVG Daily Rate (ADR) by Distribution Channel
- AVG Daily Rate (ADR) by Customer Type
- Cancellation Rate by Country
- Average Length of Stay by Customer Type and Distribution Channel
- Sum of Revenue by Deposit Type
- Sum of Cancelled (0/1) by Deposit Type
- Operational Efficiency: Average Length of Stay by Year, Quarter, Month and Day
- Count of Customer Type by Deposit Type
- AVG Daily Rate (ADR) by Distribution Channel
- Sum of Lead Time and Sum of Revenue by Customer Type
- Sum of Revenue by Distribution Channel
- Sum of Revenue and Sum of Cancelled (0/1) by Lead Time
- Cancellation Rate and Sum of Revenue by Distribution Channel


### Data Analysis

Here are some explanations and analyses of key Performance Indicators (KPIs) with the formula.
~~~
- Average Lead Time
Definition: The average number of days between booking and arrival.
Formula: Average Lead Time = AVERAGE(SHG[Lead Time])

- Average Length of Stay
Definition: The average number of days a guest stays in the hotel.
Average Length of Stay = SUM(SHG[Nights]) / COUNTROWS(SHG)

- AVG Daily Rate (ADR)
Definition: The average income earned per paid occupied room per day.
AVG Daily Rate (ADR) = SUM(SHG[Revenue])/SUM(SHG[Nights])

- Cancellation Rate
Definition: The percentage of bookings that were canceled.
Cancellation Rate = DIVIDE(COUNTROWS(FILTER(SHG,SHG[Cancelled (0/1)] = 1)), COUNTROWS(SHG))

- Guests Per Booking
Definition: The average number of guests per booking.
Guests Per Booking = AVERAGE(SHG[Guests])

- Net Revenue
Definition: The revenue minus revenue loss from cancellations.
Net Revenue = SUM(SHG[Revenue]) + SUM(SHG[Revenue Loss])

- Occupancy Rate
Definition: The percentage of rooms that are occupied
Occupancy Rate = SUM(SHG[Nights])/COUNTROWS(SHG)

- Revenue from Completed Booking
Definition: The total revenue from completed (non-cancelled) bookings.
Rev. from Completed Bookings = SUMX(FILTER(SHG, SHG[Cancelled (0/1)] = 0),SHG[Revenue])

- Revenue Loss from Cancelled Bookings
Definition: The total revenue loss from canceled bookings.
Rev. Loss from Cancelled Bookings = SUMX(FILTER(SHG, SHG[Cancelled (0/1)] = 1),SHG[Revenue Loss])

- Revenue Per Available Room (RevPAR):
Definition: The total revenue divided by the total number of available rooms.
Rev. PAR = SUM(SHG[Revenue])/ COUNTROWS(SHG)

- Total Bookings
Definition: The total number of bookings.
Total Bookings = COUNTROWS(SHG)
~~~


### The Dashboards

#### Dashboard 1

![DB 1](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/8cc970b7-1081-4bb2-b7a6-df22fb69b248)


#### Dashboard 2

![DB 2](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/cb789ddd-2253-4223-bdef-5c89222ef4e4)


#### Dashboard 3

![DB #](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/717836cf-ecec-4e01-9181-dd47d680dae1)


#### Dashboard 4

![DB 4](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/ca4cb567-dbaa-4bfb-bf43-38c0d740e6c5)
