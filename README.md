# Project: RFM Segmentation Analysis - UK Online Retail Dataset

![RFM Segmentation Image](./Temp_Photos/RFM_Image.png)

## Introduction

This project uses **RFM (Recency, Frequency, and Monetary)** segmentation to analyze customer behavior and provide insights for targeted marketing campaigns. By classifying customers based on their purchasing patterns, strategies can be tailored to improve customer retention, drive growth, and maximize the lifetime value of each customer.

The analysis focuses on transactions from customers in the **United Kingdom** for a UK-based online retail store, with transaction data spanning from **01/12/2010** to **09/12/2011**. The segmentation is based on **positive offer price transactions** for **Recency** and **Frequency**, and **all transactions, including returns**, are used to calculate **Monetary Value**.

## Dataset Overview

The dataset used in this analysis contains transactional data from an online retailer in the UK. Each record represents a unique transaction between the company and its customers.

### Key Variables:

| Variable Name  | Description                                          | Units       |
|----------------|------------------------------------------------------|-------------|
| InvoiceNo      | A unique 6-digit number for each transaction. Cancellations are marked with "C". | -           |
| StockCode      | A 5-digit number uniquely identifying each product.  | -           |
| Description    | The name of the product sold.                        | -           |
| Quantity       | The number of units purchased per transaction.       | Units       |
| InvoiceDate    | The exact date and time of the transaction.          | Date & Time |
| UnitPrice      | The price per unit of each product (in GBP).         | GBP         |
| CustomerID     | A unique 5-digit ID assigned to each customer.       | -           |
| Country        | The customer's country of residence.                | -           |

The data includes a variety of customers, including wholesalers, and spans about a year.

## Data Preprocessing

To prepare the data for RFM analysis, several preprocessing steps were carried out:

1. **Handling Missing Values**: Missing or erroneous values (like canceled transactions) were conditionally filtered out.
2. **Date Parsing**: InvoiceDate was converted to datetime format for recency calculations.
3. **Feature Engineering**: RFM metrics were calculated from the transactional data:
   - **Recency**: The time since the customer's last transaction (based on positive offer price transactions).
   - **Frequency**: The number of transactions made by the customer (based on positive offer price transactions).
   - **Monetary**: The total spending per customer (including returns).

## RFM Analysis

RFM segmentation categorizes customers based on three key metrics:

- **Recency (R)**: Measures how recently a customer made a purchase.
- **Frequency (F)**: Measures how often a customer makes purchases.
- **Monetary (M)**: Measures how much a customer spends (including returns).

The segments are created using thresholds derived from percentiles for each of the three metrics.

## Segmentation and Profiling

Based on the RFM analysis, customers are segmented into the following categories, each with its own marketing strategy:

- **Super Loyal Churned**: Customers who were highly engaged but have stopped purchasing.  
  **Recommendation**: Focus on personalized win-back campaigns to re-engage these valuable customers.

- **Super Loyal**: High-value and frequent customers.  
  **Recommendation**: Maintain loyalty through exclusive offers, rewards, and VIP treatment to retain business.

- **Potentially Inactive**: Customers who haven't made recent purchases but were frequent buyers in the past.  
  **Recommendation**: Engage with targeted re-engagement campaigns to prevent churn.

- **Potential**: Recently engaged customers with high frequency but moderate spending.  
  **Recommendation**: Offer complementary or upsell products to increase total spend.

- **New Acquisition**: Recently acquired customers with limited transactions.  
  **Recommendation**: Focus on onboarding campaigns to build long-term relationships and encourage repeat purchases.

- **Inactive**: Customers who have minimal engagement or stopped purchasing.  
  **Recommendation**: Reactivate these customers with special discounts or promotions to draw them back.

- **Loyal**: Customers who make frequent purchases but have lower spend.  
  **Recommendation**: Encourage higher spending through loyalty programs, personalized offers, and incentives.

## Customer Insights and Recommendations

The RFM segments provide clear insights into customer behavior, helping to inform more targeted marketing strategies:

- **Super Loyal Churned (28.15%)**: These customers spent significantly but recently stopped engaging.  
  **Recommendation**: Implement personalized win-back strategies, such as tailored discounts or exclusive offers, to reignite their interest.

- **Super Loyal (31.58%)**: These customers are highly engaged, loyal, and valuable.  
  **Recommendation**: Continue to nurture this segment with loyalty rewards, VIP perks, and early access to promotions.

- **Potentially Inactive (22.46%)**: These customers are at risk of becoming inactive.  
  **Recommendation**: Re-engage through targeted campaigns offering discounts or special promotions tailored to their preferences.

- **Potential (4.94%)**: These are recent, active customers with potential for upselling.  
  **Recommendation**: Introduce cross-selling or upselling offers based on previous purchase history.

- **New Acquisition (0.64%)**: These customers have made only a few purchases since acquisition.  
  **Recommendation**: Focus on onboarding them effectively with incentives to boost early retention and establish brand loyalty.

- **Inactive (8.07%)**: Customers who have little to no engagement.  
  **Recommendation**: Run reactivation campaigns offering deep discounts or special promotions to win them back.

- **Loyal (4.15%)**: These customers are regular but spend less than other groups.  
  **Recommendation**: Encourage these customers to increase their spend through loyalty programs or personalized incentives.

## Project Files and Structure

- **Customer Segmentation Using RFM Analysis for Online Retail.ipynb**: Contains the complete code for performing the RFM analysis.
- **Dataset folder**: Contains the Online Retail dataset used for analysis.
- **Output_Files folder**: Stores all output files generated from the analysis.
- **RFM Analysis folder**: Contains the final RFM segmentation analysis results and reports.

## Conclusion

RFM segmentation helps identify distinct customer groups based on their purchasing behaviors, enabling more targeted marketing campaigns. By understanding customer engagement and tailoring strategies for retention, growth, and re-engagement, businesses can maximize the value of each customer. Future steps may include predictive modeling and more refined segmentation for further optimization of marketing efforts.

## Acknowledgements

A special thanks to [Siddharth Birajdar](https://in.linkedin.com/in/siddharth-birajdar), whose work inspired much of this analysis.

This dataset is made available by the **UCI Machine Learning Repository** and was created by **Daqing Chen**, School of Engineering, London South Bank University. You can access the dataset [here](https://archive.ics.uci.edu/dataset/352/online+retail).

For more details on the analysis, please refer to the final RFM analysis report:

- **[RFM Analysis Detailed Report](./RFM_Analysis/RFM_Segmentation_Analysis_UKRetailOnline.xlsx)**
