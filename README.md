# Hotel Booking Demand

This data set contains booking information for a city hotel and a resort hotel, and includes information such as when the booking was made, length of stay, the number of adults, children, and/or babies, and the number of available parking spaces, among other things.
All personally identifying information has been removed from the data.

We will perform exploratory data analysis with python to get insight from the data.  

This article on medium explains the entire the process  
[Exploratory Data Analysis of the Hotel Booking Demand with Python](https://medium.com/@aaqibqs/exploratory-data-analysis-of-the-hotel-booking-demand-with-python-200925230106)


## Table of Content
- [Motivation](#Motivation)
- [Tools and Libraries Used](#Tools-and-Libraries-Used)
- [Files](#Files)
- [Result](#Result)
- [Dataset Description](#Dataset-Description)
- [Acknowledgements](#Acknowledgements)

## Motivation

### We have tried to answer the following Questions
1. How Many Booking Were Cancelled?
2. What is the booking ratio between Resort Hotel and City Hotel?
3. What is the percentage of booking for each year?
4. Which is the most busy month for hotel?
5. From which country most guest come?
6. How Long People Stay in the hotel?
7. Which was the most booked accommodation type (Single, Couple, Family)?

### After that we made the predictive model to predict whether the booking will be cancelled or not

**We will:**
- Perform the Feature Engineering to make new featuers
- Perform the Data Selection to select only relevant features
- Tranform the Data (Categorial to Numerical)
- Split the data (Train Test Split)
- Model the data (Fit the Data)
- And finally Evaluate our model

## Tools and Libraries Used
We have used Python 3 to its following packages:
- Pandas
- Matplotlib
- Seaborn
- Sklearn

## Files
This repository contains two files other than readme file

**Azzubair Assessment 12032022.ipynb:** Jupyter Notebook file contains all the python code, documentation and visualization  
**hotel_bookings.csv:** Our dataset file

## Dataset Description
After going through with the [original dataset documentation](https://www.sciencedirect.com/science/article/pii/S2352340918315191) , I tabulated the information into the following table: <br><br> 
**<p align="center">Table 1: Variables description </p>**
| Attribute | Description | Notes | Data Type |
| --- | --- | --- | --- |
| **hotel** | Hotel Type | Resort Hotel <br> City Hotel | Categorical |
| **is_canceled** | Value indicating if the booking was canceled | (1) is cancelled <br> (0) is not cancelled | Categorical |
| **lead_time** | Number of days that elapsed between the entering date of the booking into the PMS and the arrival date | - | Integer |
| **arrival_date_year** | Year of arrival date | - | Integer |
| **arrival_date_month** | Month of arrival date with 12 categories | “January” to “December” | Categorical |
| **arrival_date_week_number** | Week number of the arrival date | - | Integer |
| **arrival_date_day_of_month** | Day of the month of the arrival date | - | Integer |
| **stays_in_weekend_nights** | Number of weekend nights (Saturday or Sunday) the guest stayed or booked to stay at the hotel | - | Integer |
| **stays_in_week_nights** | Number of week nights (Monday to Friday) the guest stayed or booked to stay at the hotel | - | Integer |
| **adults** | Number of adults | - | Integer |
| **children** | Number of children | - | Integer |
| **babies** | Number of babies | - | Integer |
| **meal** | Type of meal booked. Categories are presented in standard hospitality meal packages | Undefined/SC – no meal package <br> BB – Bed & Breakfast  <br> HB – Half board (breakfast and one other meal – usually dinner) <br> FB – Full board (breakfast, lunch and dinner) | Categorical |
| **country** | Country of origin. Categories are represented in the ISO 3155–3:2013 format | - | Categorical |
| **market_segment** | Market segment designation | “TA” =  “Travel Agents” <br> “TO” = “Tour Operators” | Categorical |
| **distribution_channel** | Booking distribution channel | “TA” = “Travel Agents” <br> “TO” means “Tour Operators” | Categorical |
| **is_repeated_guest** | Value indicating if the booking name was from a repeated guest | (1) is repeated <br> (0) is not repeated | Categorical |
| **previous_cancellations** | Number of previous bookings that were cancelled by the customer prior to the current booking | - | Integer |
| **previous_bookings_not_canceled** | Number of previous bookings not cancelled by the customer prior to the current booking | - | Integer |
| **reserved_room_type** | Code of room type reserved | Code is presented instead of designation for anonymity reasons | Categorical |
| **assigned_room_type** | Code for the type of room assigned to the booking | Sometimes the assigned room type differs from the reserved room type due to hotel operation reasons (e.g. overbooking) or by customer request. Code is presented instead of designation for anonymity reasons | Categorical |
| **booking_changes** | Number of changes/amendments made to the booking from the moment the booking was entered on the PMS until the moment of check-in or cancellation | - | Integer |
| **deposit_type** | Indication on if the customer made a deposit to guarantee the booking. This variable can assume three categories | No Deposit – no deposit was made <br> Non Refund – a deposit was made in the value of the total stay cost <br> Refundable – a deposit was made with a value under the total cost of stay <br> | Categorical |
| **agent** | ID of the travel agency that made the booking | - | Categorical |
| **company** | ID of the company/entity that made the booking or responsible for paying the booking | ID is presented instead of designation for anonymity reasons | Categorical |
| **days_in_waiting_list** | Number of days the booking was in the waiting list before it was confirmed to the customer | - | Integer |
| **customer_type** | Type of booking, assuming one of four categories | Contract - when the booking has an allotment or other type of contract associated to it <br> Group – when the booking is associated to a group <br> Transient – when the booking is not part of a group or contract, and is not associated to other transient booking <br> Transient-party – when the booking is transient, but is associated to at least other transient booking <br> | Categorical |
| **adr** | Average Daily Rate | - | Numeric |
| **required_car_parking_spaces** | Number of car parking spaces required by the customer | - | Integer |
| **total_of_special_requests** | Number of special requests made by the customer (e.g. twin bed or high floor) | - | Integer |
| **reservation_status** | Reservation last status, assuming one of three categories | Canceled – booking was canceled by the customer <br> Check-Out – customer has checked in but already departed <br> No-Show – customer did not check-in and did inform the hotel of the reason why <br> | Categorical |
| **reservation_status_date** | Date at which the last status was set | This variable can be used in conjunction with the ReservationStatus to understand when was the booking canceled or when did the customer checked-out of the hotel | Date |


## Result
We learned that:
From the dataset distribution, I found out that for each attribute:
1) **hotel** = City hotel is booked more than Resort hotel 
2) **is_canceled** = Most booking are not cancelled, however cancelled booking are quite a lot too
3) **lead_time** = Most booking are done near or on the date of arrival and most of them are transient customer
4) **arrival_date_year** = customer arrived for the booking increased from 2015 until 2016 and slightly decreased on 2017
5) **arrival_date_month** = customer arrived for the booking are the highest during Summer season, and lowest during Winter season
6) **arrival_date_week_number** = People arrived for the booking are the highest on week 33 and lowest on week 52
7) **arrival_date_day_of_month** = Most customer arrived for the booking in the middle of the month
8) **stays_in_weekend_nights** = Most customer do not stay on weekend nights, but the are some people who would stay for 1-2 days. 
9) **stays_in_week_nights** = People tend to stay mostly for 2 days during weekdays for City Hotel, while for Resort Hotel, people mostly stay for 1 until 3 days.
10) **adults** = Most people booking for 2 adults (probably newlyweds, or retirees), or 1 adult (probably single or a traveler)
11) **children** = Most customer did not bring any child for the hotel booking
12) **babies** = Most customer did not bring any baby for the hotel booking
13) **meal** = Most customer booked for BB (Bed & Breakfast) followed by  HB (Half board) and SC (no meal package)
14) **country** = For City Hotel most people who booked are from Portugal, France, and Germany. Meanwhile for Resort Hotel, Most people who booked are from Portugal, United Kingdom, and Spain.
15) **market_segment** = Most customer booked using Online Tour Agent, Offline Tour Agent, and Tour Operators. Nowadays, people rarely use complementary market segment for hotel booking
16) **distribution_channel** = Most customer booked using Tour Agents, and Tour Operators, followed by Direct bookings and Corporate booking
17) **is_repeated_guest** = Most of the bookings are by non-repeated guests. Less than 5% of them are repeated guests.
18) **previous_cancellations** = Most customer did not cancel their previous booking prior to the current booking. Less than 3% of them cancelled their bookings prior to the current booking.
19) **previous_bookings_not_canceled** = Most customer did not cancel their previous booking prior to the current booking. Less than 3% of them cancelled their bookings prior to the current booking.
20) **reserved_room_type** = Customers mostly in favour for room type A, followed by D and others for both hotels
21) **assigned_room_type** = In the booking, most customers are assigned for room type A, followed by D and others for both hotels
22) **booking_changes** = Most booking did not make any booking changes. Only 20% of them does
23) **deposit_type** = Most people booking for no deposit, while some booking for non-refundable deposit. It is rare for customer to book for refundable deposit.
24) **agent** = Most customers used Agent ID no 9 for City Hotel booking and Agent ID No 240 for Resort Hotel booking
25) **company** = Most customers used Company ID no 40 for City Hotel booking and Company ID No 223 for Resort Hotel booking
26) **days_in_waiting_list** = Most customers who booked are not in waiting list. Less than 5% of them are from waiting list
27) **customer_type** = Most customers are transient who are usually walk-in guests, last minute or bookers or simply people that require a very short term stay in the hotel
28) **required_car_parking_spaces** = Most customers did not require parking spaces. Less than 2% requires parking spaces.
29) **total_special_requests** = Most customers did not have special request. However those who have special request quite a lot too
30) **reservation_status** = City hotel has more checkout reservation status than Resort hotel. However, City Hotel also has the most cancellation reservation status than Resort hotel. 

## Acknowledgements
The data is originally from the article Hotel Booking Demand Datasets, written by Nuno Antonio, Ana Almeida, and Luis Nunes for Data in Brief, Volume 22, February 2019.

The data was downloaded and cleaned by Thomas Mock and Antoine Bichat for #TidyTuesday during the week of February 11th, 2020.
