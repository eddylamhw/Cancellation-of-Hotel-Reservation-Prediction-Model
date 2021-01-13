# Cancellation-of-Hotel-Reservation-Prediction-Model
 
## 1. Business Question
This project aims to predict whether a customer will cancel a hotel reservation or not, so that the hotels can know when to launch a booking discount, and better allocate resources for room and food preparation. 

## 2. Data Collection
The data is downloaded from 2 websites: "ScienceDirect" and "Kaggle".

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
Cancellation of Booking for City Hotel is higher than Resort Hotel. \
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
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images/Lead_TIme_1.png">
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

### Logistic Regression
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0018.jpg">

### Support Vector Machine (Linear Kernel)
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0019.jpg">

### K-Nearest Neighbors
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0020.jpg">

### Decision Tree
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0021.jpg">

### Random Forest
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0022.jpg">

### AdaBoost Classifier
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0023.jpg">

### XGB Classifier
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0024.jpg">

## 6. Model Evaluation and Comparison
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0026.jpg">
The above figure compares the accuracy scores of all models before and after tuning. There are significant improvements in accuracy scores for SVM and KNN after tuning. Overall, XGBoost Classifier and Random Forest Classifier attain the highest accuracy scores, which are around 89%.

<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0027.jpg">
The above figure shows a ROC analysis on different models. The area under curve for XGB and Random Forest are higher than other models, which indicate that they are the best for classifying the dataset correctly. On the other hand, the blue curve for logistic regression is closest to the centre and performs the worst.

## 7. Feature Importance
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0028.jpg">
The scikit-learn in-built feature importance is used to get the weights of the features in the Random Forest and XGB models. For Random Forest, there are around 10 features that have particularly high weights. On the other hand, for XGB Classifier, there is a feature with disproportionately high weight, which is a no refund deposit type, having a weight of 0.8475. 

### Scikit-learn In-built Feature Importance Comparison
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0029.jpg">
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0030.jpg">
The top 10 most important features for both Random Forest Classifier and XGB Classifier are obtained from the scikit-learn in-built feature importance. The Random Forest Classifier and XGB Classifier are trained again using only the top 10 most important features as input variables. Even without hyper tuning, the Random Forest Classifier has an accuracy of 87% while XGB Classifier has 81%. Although only 10 out of the 50 features are used, the accuracy is still relatively high, showing that using only the features with high weight can allow us to train models more efficiently and without the cost of getting too much information while at the same time retaining a high enough accuracy scores.

### Permutation Importance Comparison
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0031.jpg">
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0032.jpg">
The top 10 most important features for both Random Forest Classifier and XGB Classifier are obtained using permutation importance. The Random Forest Classifier and XGB Classifier are trained again using only the top 10 most important features as input variables. Both Random Forest and XGB Classifiers have an accuracy of around 87%. Although there is a slight drop in accuracy for Random Forest, XGB has an increase in accuracy score compared to using top 10 features generated from scikit-learn in-built feature importance.

### Feature Importance Summary
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0032.jpg">
In summary, it seems that for our dataset, permutation importance is more suitable for XGB Classifier, while scikit-learn in-built feature importance performs better with Random Forest. From the analysis, we can also derive some important features that hotels can consider for predicting cancellation of reservation, including country of origin, lead time, deposit type, previous cancellations, total number of special requests, and required number of parking spaces.

## 8. Future Improvement
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0035.jpg">
<img src="https://github.com/eddylamhw/Cancellation-of-Hotel-Reservation-Prediction-Model/blob/main/images(ppt)/0036.jpg">

# References
Dataset \
https://www.sciencedirect.com/science/article/pii/S2352340918315191
https://www.kaggle.com/jessemostipak/hotel-booking-demand

Kaggle Notebook \
Marcus Wingen: https://www.kaggle.com/marcuswingen/eda-of-bookings-and-ml-to-predict-cancelations




