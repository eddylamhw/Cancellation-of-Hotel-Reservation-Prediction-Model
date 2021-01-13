# Cancellation-of-Hotel-Reservation-Prediction-Model
 
## 1. Business Question
This project aims to predict whether a customer will cancel a hotel reservation or not, so that the hotels can know when to launch a booking discount, and better allocate resources for room and food preparation. 

## 2. Data Collection
The data is downloaded from 2 websites: "ScienceDirect" and "Kaggle".
ScienceDirect: https://www.sciencedirect.com/science/article/pii/S2352340918315191
Kaggle: https://www.kaggle.com/jessemostipak/hotel-booking-demand

The data includes reservation data from two hotels, a resort hotel and a city hotel, that are due to arrive between the 1st of July of 2015 and the 31st of August 2017. The data contains bookings that effectively arrived and bookings that were canceled. 

## 3. Data Preprocessing
1. Merge the datasets of Resort Hotel and City Hotel.
2. Clean spaces in the data.
3. Drop unnecessary features.
4. Fill in missing values.
5. Encode categorical variables with get_dummies. (e.g. hotel type, meal type, market segment, distribution channel, deposit type, and customer type).
6. Encode with ordinal encoder for ordinal attributes (e.g. agent number, company number, country number).
7. Map the month and room names with corresponding numbers.

## 4. Exploratory Data Analysis
### Country of Origin
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Country_of_Origin_1.png">
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Country_of_Origin_2.png">
Most customers are from Portugal, France and UK.
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Country_of_Origin_3.png">
Customers from Portugal, Brazil and Italy have higher percentages of booking cancellation.

### Month
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Month_1.png">
Cancellation of Booking for City Hotel is higher than Resort Hotel.
Also, there are more cancellations from April to September, and cancellations are the lowest in February and November.

### Agent
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Agent_1.png">
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Agent_2.png">
In average, cancellation rate of customers with agent is about 40%, while it is around 25% for those booking without agent.

### Special Requests
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Special_Request.png">
Customers with fewer special requests tend to have higher percentage of cancellation.

### Customer Type
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Customer.png">
Group customers tend to have lower percentage of cancellation.

### Lead Time
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Lead_Time_1.png">
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Lead_Time_2.png">
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Lead_Time_3.png">
Most customers have lead time within 50 days. In general, cancellation rate is higher if there is longer lead time.

## 5. Models Creation
The followings are the input variables:
1. The number of days that elapsed between the entering date of the booking and the arrival   date (LeadTime)
2. Arrival Date (ArrivalDateYear, ArrivalDateMonth, ArrivalDateWeekNumber, ArrivalDateDayOfMonth)
3. Stays in weekday or weekend nights (StaysInWeekendNights, StaysInWeekNights)
4. Number of customers (Adults, Children, Babies)
5. Country of origin (Country)
6. Whether the customer is a repeated guest (IsRepeatedGuest)
7. Whether the customer has cancelled a booking previously (PreviousCancellations, PreviousBookingsNotCanceled)
8. The room type (ReservedRoomType, AssignedRoomType)
9. Number of booking changes (BookingChanges)
10. Agent Number or no agent (Agent)
11. ID of the company/entity that made the booking or responsible for paying the booking (Company)
12. Number of days the booking was in the waiting list (DaysInWaitingList)
13. Average Daily Rate (ADR)
14. The number of required car parking spaces (RequiredCarParkingSpaces)
15. The number of total special requests (TotalOfSpecialRequests)
16. The hotel type (Hotel_City Hotel, Hotel_Resort Hotel)
17. The meal type (Meal_BB, Meal_FB, Meal_HB, Meal_SC, Meal_Undefined)
18. Market segment of the booking (MarketSegment_Aviation, MarketSegment_Complementary, MarketSegment_Corporate, MarketSegment_Direct, MarketSegment_Groups, MarketSegment_Offline TA/TO, MarketSegment_Online TA, MarketSegment_Undefined)
19. The booking distribution channel (DistributionChannel_Corporate, DistributionChannel_Direct, DistributionChannel_GDS, DistributionChannel_TA/TO, DistributionChannel_Undefined)
20. The deposit type (DepositType_No Deposit, DepositType_Non Refund, DepositType_Refundable)
21. The customer type (CustomerType_Contract, CustomerType_Group, CustomerType_Transient, CustomerType_Transient-Party)

The following is the output variable:
- Value indicating if the booking was canceled (IsCanceled)



## Logistic Regression
