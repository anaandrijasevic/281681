In today's digital age, the rise of SMS-based communication has led to a significant increase in fraudulent messages.The "SafeComm Digital Security Solutions" project aims to address this issue by developing an advanced machine-learning system, capable of  accurately identifying and flagging fraudulent SMS messages. Our goal is to enhance digital communication security and protect users from potential scams and malicious activities.  for that we use a dataset containing SMS messages that are labeled as either   fraudulent or legitimate (Binary indicator if the SMS is fraudulent (1 for Yes, 0 for No)).


The first step of our journey is to , tackle  an initial exploration phase called Explanatory Data Analysis (EDA). We want to  understand what we are dealing with (and checking if our dataset contains missing values )  . The main focus are  on two things: figuring out how many messages are fraudulent and looking at how long these messages are.

First, by counting how many messages are pinned as fraudulent compared to those that aren't , we get a clear picture of what our data lookes like. This step allowes us to  see how many of each type we have .As it can bee noticed our dataset contains 86.6% of non fraudolent messages and just 13.4% of fraudolent ones. this Representation shows a considerabel inbalance (the imbalance between the distribution of fraudulent and non-fraudulent messages.)and gives us an idea on how to later train our models to do their respective functions. 

Secondly, we look at the length of the SMS messages. This might seem unusual at first, but, we think that maybe fraudulent messages have a certain length — perhaps they're longer with more convincing details, or maybe they're short and straight to the point.For that we explore the sms text lenght , create a new colom that gives us the lenght of the sms to finally be able to visualise it in the form of a histplot 
By examining this, we potentially discovered a pattern that would help us in identifying the fraudulent messages later with our machine learning models.Indeed we can perceive a lenght difference between fraudolent and non fraudolent message as the fraudolent ones are generally shorter 

will also checked for missing values and concluded that we have non (The dataset has no missing values in any of the columns (Fraudulent, SMS Text, ID, Date and Time).) 

After tackling the too main focus points we want to see if the words frequency could play a role by hepling  us  and giving  us an idea on how to later train our models to do their respective functions. 

After plotting the frequencies of the most common words in fraudulent SMS messages on a bar graph, we have reached the conclusion that this parameter is not suitable for helping us identify fraudulent SMS messages. It could, in fact, be biased because many of the most frequently used words in fraudulent SMS messages are common words that are also used in everyday life and, in our specific case, in legitimate SMS messages.

We explore the temporal aspects of SMS traffic to uncover any discernible patterns that could potentially indicate fraudulent activity. To accomplish this, we transform timestamps into distinct date-time characteristics and then proceed to examine how SMS messages are distributed across different months and specific days of the month.

Our visual analysis of the data reveals that the frequency of SMS messages varies from one month to another. However, it's worth noting that fraudulent messages are consistently present, although they occur less frequently in comparison. When we conduct a day-to-day analysis, we do not observe significant fluctuations in the occurrence of fraud, which suggests that there is no immediate correlation with particular days. however we decided to keep this colomn demander a chat pourquoi on la garder 


<i> the 'ID' column in a dataset typically serves as a unique identifier for each record and does not hold any intrinsic predictive power for the model.It usually contains unique values for each instance and does not have a relationship or pattern that would help in predicting the target variable, and it could lead to overfitting.
 
 df = df.drop('ID', axis=1)
 Drop the 'ID' column from the training features
X_train = X_train.drop('ID', axis=1)

 Drop the 'ID' column from the test features
X_test = X_test.drop('ID', axis=1) 

This  codes represent one of the ways of droping the ID colom while working with training and test sets 
for my case i decided not to drop it 
Its retention could facilitates a seamless audit trail to backtrack and investigate any anomalies or misclassifications post-model training.


