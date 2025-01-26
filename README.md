## Project: Customer Segmentation using RFM Analysis for a UK-based Online Retail Store
---

![RFM Segmentation Image](./Temp_Photos/RFM_Image.png)

---

### Introduction

This project uses **RFM (Recency, Frequency, and Monetary)** segmentation to analyze customer behavior and provide insights for targeted marketing campaigns. By classifying customers based on their purchasing patterns, strategies can be tailored to improve customer retention, drive growth, and maximize the lifetime value of each customer.

The analysis focuses on transactions from customers in the **United Kingdom** for a UK-based online retail store, with transaction data spanning from **01/12/2010** to **09/12/2011**. The segmentation is based on **positive offer price transactions** for **Recency** and **Frequency**, and **all transactions, including returns**, are used to calculate **Monetary Value**.

---

### Dataset Overview

The dataset used in this analysis contains transactional data from an online retailer in the UK. Each record represents a unique transaction between the company and its customers.


#### Key Variables:

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


### Data Preprocessing

To prepare the data for RFM analysis, several preprocessing steps were carried out:

1. **Handling Missing Values**: Missing or erroneous values (like canceled transactions) were conditionally filtered out.
2. **Date Parsing**: InvoiceDate was converted to datetime format for recency calculations.
3. **Feature Engineering**: RFM metrics were calculated from the transactional data:
   - **Recency**: The time since the customer's last transaction (based on positive offer price transactions).
   - **Frequency**: The number of transactions made by the customer (based on positive offer price transactions).
   - **Monetary**: The total spending per customer (including returns).


### RFM Analysis

RFM segmentation categorizes customers based on three key metrics:

- **Recency (R)**: Measures how recently a customer made a purchase.
- **Frequency (F)**: Measures how often a customer makes purchases.
- **Monetary (M)**: Measures how much a customer spends (including returns).

The segments are created using thresholds derived from percentiles for each of the three metrics.

### Segmentation and Profiling  

Based on the RFM analysis, customers are segmented into the following categories:  

- **Super Loyal Churned**: Customers who were highly engaged and valuable but have stopped purchasing.  
- **Super Loyal**: High-value customers who frequently purchase and are highly engaged.  
- **Potentially Inactive**: Customers who were frequent buyers in the past but haven't made recent purchases.  
- **Potential**: Recently engaged customers with high purchase frequency but moderate spending.  
- **New Acquisition**: Recently acquired customers with limited transactions.  
- **Inactive**: Customers who show minimal engagement or have stopped purchasing altogether.  
- **Loyal**: Customers who make frequent purchases but have lower spending compared to other groups.  

### Mapping Conditions to Customer Segments  

The following logic maps RFM (Recency, Frequency, Monetary) thresholds to specific customer segments:  

#### RFM Threshold Categories  
- **H**: High  
- **M**: Medium  
- **L**: Low  

#### Mapping Logic  

1. **Super Loyal Churned**  
   - **Conditions**: Low Recency, High/Medium/Low Frequency, High Monetary  
     (L-H-H, L-M-H, L-L-H)  
   - Customers who spent significantly but recently stopped engaging.  

2. **Super Loyal**  
   - **Conditions**: High/Medium Recency, High Frequency, High Monetary  
     (H-H-H, H-M-H, M-H-H, M-M-H)  
   - Highly engaged, consistent, and valuable customers.  

3. **Potentially Inactive**  
   - **Conditions**: Low Recency, Low/Medium Frequency, Medium Monetary  
     (L-H-M, L-L-M, L-M-M)  
   - Customers at risk of becoming inactive; require re-engagement.  

4. **Potential**  
   - **Conditions**: Medium Recency, Low Frequency, High/Medium/Low Monetary  
     (M-L-H, M-L-L, M-L-M)  
   - Recently engaged but with lower frequency; potential to increase value.  

5. **New Acquisition**  
   - **Conditions**: High Recency, Low Frequency, High/Medium/Low Monetary  
     (H-L-H, H-L-L, H-L-M)  
   - Recently acquired customers; focus on onboarding.  

6. **Loyal**  
   - **Conditions**: High/Medium Recency, Medium Frequency, High/Medium/Low Monetary  
     (H-H-L, H-H-M, H-M-L, H-M-M, M-H-L, M-H-M, M-M-L, M-M-M)  
   - Consistently engaged but with room for growth.  

7. **Inactive**  
   - **Conditions**: Low Recency, Low/Medium Frequency, Low Monetary  
     (L-H-L, L-L-L, L-M-L)  
   - Customers with minimal engagement; require reactivation efforts.  

### Customer Insights and Recommendations  

The RFM analysis reveals the following distribution of customer segments and corresponding strategies:  

- **Super Loyal Churned (28.15%)**:  
   These customers spent significantly in the past but have recently stopped engaging.  
   **Recommendation**: Focus on win-back strategies, such as tailored discounts or exclusive offers, to re-engage them.  

- **Super Loyal (31.58%)**:  
   These are highly valuable, engaged, and frequent buyers.  
   **Recommendation**: Maintain loyalty through VIP perks, early access to promotions, and loyalty rewards.  

- **Potentially Inactive (22.46%)**:  
   Customers at risk of becoming inactive after previously being frequent buyers.  
   **Recommendation**: Prevent churn with re-engagement campaigns offering discounts or personalized promotions based on their preferences.  

- **Potential (4.94%)**:  
   Recently active customers who make frequent purchases but have moderate spending.  
   **Recommendation**: Offer cross-selling or upselling opportunities tailored to their purchase history.  

- **New Acquisition (0.64%)**:  
   Recently acquired customers with minimal transactions.  
   **Recommendation**: Focus on onboarding campaigns with incentives to build brand loyalty and encourage repeat purchases.  

- **Inactive (8.07%)**:  
   Customers with little to no engagement or purchasing activity.  
   **Recommendation**: Run reactivation campaigns using deep discounts or special promotions to win them back.  

- **Loyal (4.15%)**:  
   Regular buyers who frequently purchase but spend less than other groups.  
   **Recommendation**: Encourage higher spending through loyalty programs, personalized offers, and incentives.  

This segmentation highlights actionable strategies to enhance customer engagement, retention, and value.


### Conclusion

RFM segmentation helps identify distinct customer groups based on their purchasing behaviors, enabling more targeted marketing campaigns. By understanding customer engagement and tailoring strategies for retention, growth, and re-engagement, businesses can maximize the value of each customer. Future steps may include predictive modeling and more refined segmentation for further optimization of marketing efforts.

---

### Project Files and Structure

- **[Customer Segmentation Using RFM Analysis for Online Retail.ipynb](https://github.com/ChaitanyaC22/Customer-Segmentation-Using-RFM-Analysis-for-Online-Retail/blob/main/Customer%20Segmentation%20Using%20RFM%20Analysis%20for%20Online%20Retail.ipynb)**: Contains the complete code for performing the RFM analysis.
- **Dataset folder**: Contains the Online Retail dataset used for analysis.
- **Output_Files folder**: Stores all output files generated from the analysis.
- **RFM Analysis folder**: Contains the final RFM segmentation analysis results and reports.

For more details on the analysis, please refer to the final RFM analysis report:
**[RFM Analysis Detailed Report](./RFM%20Analysis/RFM_Segmentation_Analysis_UKRetailOnline.xlsx?raw=true)**

---

### Acknowledgements

A special thanks to [Siddharth Birajdar](https://in.linkedin.com/in/siddharth-birajdar), whose work inspired much of this analysis.

This dataset is made available by the **UCI Machine Learning Repository** and was created by **Daqing Chen**, School of Engineering, London South Bank University. You can access the dataset [here](https://archive.ics.uci.edu/dataset/352/online+retail).


<br>
Thank you for taking the time to visit this repository. 🙏

---
