# Hotel-Reservation-Cancellation-Prediction
Predicted Reservation Cancellation - binary classification problem

Data Size: 
* 100,000 observation
* 40,325 canceled vs 68460 not canceled
* cancellation rate 37%
* 27 features:
  * hotel, lead_time, stays_in_weekend_nights, stays_in_weeks_nights, adults, children, babies, distribution channel, is_repeated_guests, Previous_booking_not_canceled, reserved_room_type, assigned_room_type, booking_changes, agent, company, etc
* label: cancel vs not canceled 


Modelling:
* baseline: logistic regression
* Random Forest classifier
* Gradient Boosting Classifier
* Adaboost

Process:
1. data cleaning
    1. Dropped outliers (e.g. adr > $1000 or adr < $0)
    2. Removed questionale data: reservaton with only children /babies but with no adults/ requestion parking space over five with only two adults
3. preprocessing
    1. label encoding
5. feature selection
6. training: 4-fold 75%training, 25% testing
7. validation: AUC and precision - 0.934 on training, 0.85 on testing

Analysis:
1. how each feature affect results - using boxplots
2. the longer the lead_time, a reservation is more likely to be canceled (lead time is defined as the time betweem the date the customer makes the reservation to the reserved date)
3. people with more special requests are less likely to cancel 

Conclusion:
We recommend hotels to cut off the lead time and offer more specialized services.
