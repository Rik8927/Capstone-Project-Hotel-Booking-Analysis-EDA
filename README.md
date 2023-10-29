# Capstone-Project-Hotel-Booking-Analysis-EDA
# Hotel-Booking-Analysis
The project contains the real world data record of hotel bookings of a city and a resort hotel containing details like bookings, cancellations, guest details etc. from 2015 to 2017. In this project we are going to analyze Hotel Booking Data in order to find out valuable insights and give suggestions to increase revenue of hotels.

**Programming Language** : Python

**Libraries used** : Pandas, Numpy, Matplotlib, Seaborn

**NoteBook** : Google Colab

**Dataset Source** : Provided by Almabetter themself.

## Objective
We are provided with a hotel bookings dataset.

The main purpose of this study is to perform EDA on the given dataset and draw useful conclusions about the trends in hotel bookings and how factors that control hotel bookings influence each other.

## Dataset 
We are given a hotel bookings dataset. This dataset contains booking information for a city hotel and a resort hotel. It contains the following features.
```
- hotel: Name of hotel ( City or Resort)
- is_canceled: Whether the booking is canceled or not (0 for no canceled and 1 for canceled)
- lead_time: time (in days) between booking transaction and actual arrival.
- arrival_date_year: Year of arrival
- arrival_date_month: month of arrival
- arrival_date_week_number: week number of arrival date.
- arrival_date_day_of_month: Day of month of arrival date
- stays_in_weekend_nights: No. of weekend nights spent in a hotel
- stays_in_week_nights: No. of weeknights spent in a hotel
- adults: No. of adults in single booking record.
- children: No. of children in single booking record.
- babies: No. of babies in single booking record. 
- meal: Type of meal chosen 
- country: Country of origin of customers (as mentioned by them)
- market_segment: What segment via booking was made and for what purpose.
- distribution_channel: Via which medium booking was made.
- is_repeated_guest: Whether the customer has made any booking before(0 for No and 1 for Yes)
- previous_cancellations: No. of previous canceled bookings.
- previous_bookings_not_canceled: No. of previous non-canceled bookings.
- reserved_room_type: Room type reserved by a customer.
- assigned_room_type: Room type assigned to the customer.
- booking_changes: No. of booking changes done by customers
- deposit_type: Type of deposit at the time of making a booking (No deposit/ Refundable/ No refund)
- agent: Id of agent for booking
- company: Id of the company making a booking
- days_in_waiting_list: No. of days on waiting list.
- customer_type: Type of customer(Transient, Group, etc.)
- adr: Average Daily rate.
- required_car_parking_spaces: No. of car parking asked in booking
- total_of_special_requests: total no. of special request.
- reservation_status: Whether a customer has checked out or canceled,or not showed 
- reservation_status_date: Date of making reservation status.
```

- Total number of rows in data: 119390
- Total number of columns: 32

## Data Cleaning and Feature Engineering

### (1) Handling null values
- Null values in columns `company` and `agent` were replaced by 0.
- Null values in column `country` were replaced by 'others'.


### (2) Removing Duplicate rows
All duplicate rows were dropped.

### (3) Converting columns to appropriate data types

- Changed data type of `children`, `company`, `agent` to int type.
### (4) Renaming the columns

- The `adr` column was renamed for better understanding to `average_daily_rate`



### (5) Creating new columns
- Creating new column `Total_stay` by adding `stays_in_weekend_nights`+`stays_in_week_nights`.
- Creating new column `Total_members` by adding `adults`+`children`+`babies`.
###(6)Remove outliers

## Exploratory Data Analysis

Performed EDA and tried answering the following questions:

```
 Q1) Remove outlier
 Q2)  Which hotel has more no of bookings and What is the  percentage of bookings in each hotel ?
 Q3) Which meal type is the  most preffered meal of customers ?
 Q4) Trough which channel most booking came?
 Q5)How many number of repeated guest are there?
 Q6)Hotel wise booking based on year and what is the trend?
 Q7)Hotel wise booking based on date of the month and what is the trend?
 Q8)Hotel wise booking based on month and what is the trend?
 Q9)Which country given most number of bookings?
 Q10)What type of customer given most number of bookings?
 Q11)How many percentage of customer required parking spaces?
 Q12)What type of guest most come in the hotel?
 Q13)which agent done most number of bookings?
 Q14)Which type of room preffered by most number of guest?
 Q15)How long the guest stay in the hotel and number of stay in weekend and weekdays?
 Q16)Which hotel got most number of full stay?
 Q17)Which type of booking most preffered by the guest?
 Q18)Which type of hotel got most cancellations?
 Q19)Average waiting period of booking?
 Q20)What is the average daily rate month wise?
 Q21)What is the average daily price per person?
 Q22)What is the number of special requests?
 23)Using a heatmap to find out the correlation.
 24) Using pair plot to find out the corelation.

Mainly performed using Matplotlib and Seaborn library and the following graph and plots had been used:
   - Bar Plot.
   - Scatter Plot.
   - Pie Chart.
   - Line Plot.
   - Heatmap.
   - Box Plot
   -Pair plot
             
## Analysis:

Performed analysis and made the following conclusions:
```
 1.)From the scatter plot it is clear that when Full stay increases the average daily rate decreases. So the customer gets a better discount. 
 2.) 61% of bookings are for the City Hotel and 39% of bookings are for the Resort hotel, therefore City Hotel is busier than the Resort hotel.
 3.)BB-Bed and breakfast HB-Half bord(Breakfast and dinner included FB-Full board(in which breakfast,lunch and dinner are included) 78% people like BB type meal
 4.)79.13% of people booked through TA/TO.
 5.)Only 4% of people are repeated guests, rest are new guests.
 6.) Booking of city hotels is higher than the resort hotel in 2016 and the bookings were also maximum.
 7.)We can see less number of arrivals at the last  of the month.
 8.)Most booking was done in the month of May, June, July, and August.
 9.)Most guests are from Portugal and other European countries.
 10.)There are 4 types of customers. And maximum are transient types.
 11.)Only 8% of people require parking spaces.
 12.)Most guests are coming as a pair of two adults.
 13.)Agent no.9 has made the maximum booking.
 14.) Rooms A and D are most preferred by the guest. but better average daily room are H,G,F,C.
 15.) a) The most common stay in the hotel is less than 4 days and for longer days people like to stay in Resort hotels.
      b) City hotels have more number of stays in both weekdays and weekends.
  16.)Full stay is quite the same for both city hotels and resorts.
  17)Booking preferred with no deposit in a resort hotel is much higher than a city hotel.
  18) a) The cancellation rate in city hotels is much higher than in resort hotels.
      b)And cancellation has been done in the highest number in 2017
  19) The average waiting period in city hotel is much higher rather than resort.
  20) The average daily rate in city hotels much higher rather than resort.And it got its peak during may,june,july,august,september.
  21)It is clearly visible price per person in resort hotel much higher.And it gots its peak during may,june,july,august,september.
  22) The number of special request is much higher in city hotel rather than resort.
  23)Full_stay and lead_time have slide correlation.This mean that who stay longer have got less time to plan. 2.Average_daily_rate is        also slightly correlated with Total_members.Which means more number of people means more daily rate.
  24)we find out the pattern and correlation.
```
## Conclusion

```
(1) 61% bookings are for City hotel and 39% bookings are for Resort hotel, therefore City Hotel is busier than Resort hotel. Also the overall average daily rate of City hotel is slightly higher than Resort hotel.
(2) Mostly guests stay for less than 5 days in hotel and for longer stays Resort hotel is preferred.
(3) Most of the guests came from european countries, with most of guests coming from Portugal.
(4) It's clearly seen that the most people preferred room is Type A, . Also, the average daily rate of type A rooms seems to be less. But, those whose average daily rate is higher i.e.(Type C,G,F,H) it's seen that preference is also less, hotel need to improve on this.
(5) Retention rate of both the hotel is very low need to think on that too.
(6) We should also target months between May to Aug. Those are peak month for Hotel revenue generation. 
(7) Within a month, average daily rate gradually increases as month ends, with small sudden rise on weekends.
(8) Couples are the most common guests for hotels, hence hotels can plan services according to couples needs to increase revenue.
(9) For customers, generally the longer stays (more than 15 days) can result in better deals in terms of low average daily rate.
(10) November, December, January and February are the months which has least bookings so in this periods you can get rooms with less average daily rate.
And many more conclusion
```
## Challenges
```
(1) Lot of null values were present in the dataset.
(2) Data type of some Data was in wrong format.
(3) Lot of duplicate data.
(4) Which visualization techniques to use was a challenge?

