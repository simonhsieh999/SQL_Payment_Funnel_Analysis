# Payment Funnel Analysis

This project is from Jess Ramos's [Big SQL Energy course](https://bigdataenergycourses.com/p/bigsqlenergy).

## Executive Summary

Customers have been signing up for a subscription. However, not all customers have completed the entire payment process and paid for the subscription, leading to a loss in revenue. This analysis uses SQL to analyze each step of the entire payment funnel process to identify the causes of the unpaid subscriptions, and to figure out solutions to improve successful payments of the subscriptions.

## Business Problem

The finance team has noticed many unpaid subscriptions, and wants to work on resolving the issues since they have been negatively impacting the revenue. This is done by analyzing the subscription payment funnel stages in order to identify the stages with the most frequent errors, and to increase the conversion rate (the percentage of subscriptions that are successfully converted into a paid subscription). Each of the stages is shown in the following visual (by Jess Ramos) with a maxstatus from 1-5 assigned in each stage, with the goal having a complete payment (maxstatus = 5).

![image](https://github.com/user-attachments/assets/e68e5da9-1cfc-48fc-a676-b4ab13a95b15)


## Methodology

The subscriptions, payment_status_log, and payment_status_definitions tables from the database using Hex were used for the analysis. Using SQL, the tables were extracted, cleaned, and transformed. The following steps were performed:
- Created a CTE assigning a max_status of each subscription_id.
- Categorizing payment statuses using the CASE function.
- Counted the number of payment funnel stages in each year to showcase the distribution, and create a line chart of the distribution.
- Calculated the conversion rate, workflow completion rate, and error rate.
- Created visuals using Hex.
- For the coding process, click [here](https://github.com/simonhsieh999/SQL_Payment_Funnel_Analysis/blob/main/Coding%20Process) to view it.

## Skills

- SQL (Joins, aggregate functions, CTEs, cleaning & transformations, windows functions)
- Data Cleaning
- Data Wrangling
- Data Visualization

## Results

- The majority of the subscriptions have not started the payment process. Here is a line chart illustrating the number of subscriptions for each payment funnel stage each year:
 ![image](https://github.com/user-attachments/assets/4dc82023-e13f-4279-b0e9-bab66d05d2f4)


- The conversion rate (the percentage of subscriptions that are successfully converted into a paid subscription) is 20.3%
- Workflow completion rate (The percentage of subscriptions of those who started the payment that end up completing the payment) is 34.3%
- The percentage of subscriptions that hit an error is 16.9%. Here is a column chart reflecting the number of subscriptions that do not have an error (light blue) and that do have an error (dark blue):
  ![image](https://github.com/user-attachments/assets/9c1a95fe-80f9-4eb7-89c0-9110f6e92b25)

	
## Business Recommendations

Since the majority of the subscriptions have not started the payment process, this needs to be addressed, otherwise this is going to negatively impact the revenue. Also, when a subscription has been made but not paid, the person may end up forgetting about it the next few days, leading them to remain considered an unpaid subscription. This can be addressed in these ways:
- Communicating to them the importance of making the payment earlier to immediately gain the benefits of the product. Having a sense of urgency.
- Having incentives for subscribers who pay earlier such as a discount, coupon, or some sort of reward if they pay by a certain day.
- Reminding the subscriber through text or call about them not starting their payment yet
- Having a deadline (like 1 week) where they have to make the payment within one week, otherwise they will no longer be a subscriber.
		
Also, payment errors can occur, which can be a cause for the unpaid subscriptions. This can be addressed in these ways: 
- Consider having the subscriber's credit card information saved into their account (while having it secured) so that the incorrect information won't be entered, reducing the number of human errors.
- Communicating to the payment processing vendor about the issues that occur with the payment process that reach the vendor's stage, and have them work on resolving those issues.

## Next Steps

- Investigate the reasons why the users aren't starting the payment process after signing up for a subscription. Are they related to the user or our process?
- Investigate the errors to identify which errors are common (user errors or vendor errors), and to identify the causes of those errors to prevent future issues.
