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
- Count of Country by Distribution Channel
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

### Result and Findings

Here, we want to critically answer some major questions with individual visualization.

#### Booking Patterns:
- What is the trend in booking patterns over time, and are there specific seasons or months with increased booking activity?

![SHG 1](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/4c0f2ac6-a9fe-4bc2-b3e3-ef4924ddf9a2)

From the chart above, there is a declining trend in booking patterns over time across different distribution channels. Online Travel Agents have the highest booking count at 74.072K and was 1,481,340.00% higher than Undefined, which had the lowest Count of Booking Date, followed by a significant drop to Offline Travel Agents at 24K. Direct bookings are at 15K, Corporate bookings are even lower at 7K, and there are no bookings under the Undefined category. Across all 5 Distribution channels, the Count of Booking dates ranged from 0 to 74,072.  


- How does lead time vary across different booking channels, and is there a correlation between lead time and customer type?

![SHG 2](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/a92aa6af-70b9-44bc-a1e9-339255d2e0a4)

The chart above shows that lead time varies significantly across different booking channels and customer types. Transient customers who book through corporate channels have the highest lead time at 6.0M, while other customer types (Transient-Party, Contract, Group) have much lower lead times ranging from 1.3M to 1.7M when booked through Direct or Offline Travel Agent channels.


#### Customer Behavior Analysis:

- Which distribution channels contribute the most to bookings, and how does the average daily rate (ADR) differ across these channels?

![SHG 3](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/1b6cb58e-09e1-4250-85a7-f69a29ec460d)

The distribution channel that contributes the most to bookings is Online Trav. with 28.86% of the total bookings. The ADR for this channel is $94.76. The second highest is Offline Trav. with an ADR of $74.32 and it contributes to 22.63% of total bookings.


- Can we identify any patterns in the distribution of guests based on their country of origin, and how does this impact revenue?

![SHG 4](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/a1bc34ff-fec9-499c-9090-a9e9fb813e11)

The country with the highest number of guests is Venezuela with approximately 4K guests, followed by Viet Nam with approximately 2K guests. However, despite having fewer guests (0.6K), Zambia generates 1K in revenue, indicating a higher revenue per guest compared to Venezuela and Viet Nam. 
The sum of Guests and the total Sum of Revenue are positively correlated with each other.  Venezuela accounted for 62.07% of Sum of Guests.  The Sum of Revenue and Sum of Guests diverged the most when the Country was Venezuela when the Sum of Revenue was 3,894 higher than the Sum of Guests.   


#### Cancellation Analysis:

- What factors are most strongly correlated with cancellations, and can we predict potential cancellations based on certain variables?

![SHG 5](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/e1c7fccb-8aad-485e-ab55-aa9f07875990)

The customer types “Transient-Party” and “Group” have the highest cancellation rates of 37.95% and 28.84%, respectively.
Transient accounted for 87.65% of Sum of Revenue Loss.  Cancellation Rate and Sum of Revenue Loss diverged the most when the Customer Type was Transient when the Cancellation Rate was 11,502,363.41 higher than the Sum of Revenue Loss.  


- How does the revenue loss from cancellations compare across different customer segments and distribution channels?

![SHG 6](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/3c306bc4-bb29-457d-ab3a-27ed4ca3c414)

The chart depicts the sum of revenue by customer type. Transient customers contribute the highest revenue at 23M, followed by a significant drop to Transient-Party at 5M. Contract customers contribute 2M, and there is no revenue from Group customers. Transient accounted for 76.68% of Sum of Revenue.  Across all 4 Customer Types, the Sum of Revenue ranged from 123,354 to 22,696,693. 


#### Revenue Optimization:

- What is the overall revenue trend, and are there specific customer segments or countries contributing significantly to revenue?

![SHG 7](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/ed3b1b90-44c0-4ba8-b624-b4c7f5e80975)

The overall revenue trend shows that the Transient customer type generates the highest revenue, followed by Transient-Party, while Contract and Group customer types do not generate any revenue. Albania contributes significantly to the Transient customer type’s revenue while Transient in Country Portugal made up 24.80% of Sum of Revenue. 


- Can we identify optimal pricing strategies based on the Average Daily Rate (ADR) for different customer types and distribution channels?

![SHG 8](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/9730c401-0b0d-44c0-8c86-9f2fdce6a367)

The optimal pricing strategy, based on the ADR, would be to prioritize Group and Transient customer types as they have higher ADRs of 74.2 and 73.5 respectively. Contract and Transient-Party customer types have lower ADRs, so they might not be as profitable.


#### Geographical Analysis:

- How does the distribution of guests vary across different countries, and are there specific countries that should be targeted for marketing efforts?

![SHG 10](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/ff31c119-44a9-49f6-98b3-1651cc602994)

At 74,072, Online Travel Agent had the highest Count of Country and was 1,481,340.00% higher than Undefined, which had the lowest Count of Country at 5. Offline Travel Agent had the second highest Count of Country with 24k even though with an appreciable difference.   Online Travel Agent accounted for 62.04% of Count of Country.  Across all 5 Distribution Channel, Count of Country ranged from 0 to 74,072.

- Is there a correlation between the country of origin and the likelihood of cancellations or extended stays?

![SHG 111](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/c06d52a0-264f-46fc-8268-9147f40e2cc0)

The top 11 Countries like Benin, Cambodia, Fiji, etc, all had a Cancellation Rate of 1.  Across all 126 Countries, the Cancellation Rate ranged from 0.03 to 1.  This simply means that there is a correlation between the country of origin and the likelihood of cancellations, though the chance of cancellation is slim.


#### Operational Efficiency: 

- What is the average length of stay for guests, and how does it differ based on booking channels or customer types?

![SGH 12](https://github.com/Solution92/SPLENDOR-HOTEL-GROUPS-SHG-BOOKING-ANALYSIS/assets/144762124/545d82a0-0d17-4bb4-9c04-0074cf8c50d7)

The average length of stay for guests varies based on both booking channels and customer types. For instance, “Contract” customers tend to have longer stays when booking through “Corporate” or “Direct” channels. “Transient-Party” customers have the longest stays when booking through “Offline Travel Agents”. The shortest stays are observed in the “Group” customer type across all booking channels.











