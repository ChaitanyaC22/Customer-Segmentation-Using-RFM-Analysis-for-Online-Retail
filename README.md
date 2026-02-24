## Project: Customer Segmentation using RFM Analysis for a UK-based Online Retail Store

---

![RFM Segmentation Image](./Temp_Photos/RFM_Image.png)

---

### Introduction

This project uses **RFM (Recency, Frequency, and Monetary)** segmentation to analyze customer behavior and provide insights for targeted marketing campaigns. By classifying customers based on their purchasing patterns, strategies can be tailored to improve customer retention, drive growth, and maximize the lifetime value of each customer.

The analysis focuses on transactions from customers in the **United Kingdom** for a UK-based online retail store, with transaction data spanning from **01/12/2010** to **09/12/2011**.

The segmentation is based on **positive offer price transactions** for **Recency** and **Frequency**, and **all transactions, including returns**, are used to calculate **Monetary Value**.

---

### Dataset Overview

The dataset used in this analysis contains transactional data from an online retailer in the UK. Each record represents a unique transaction between the company and its customers.

#### Key Variables:

| Variable Name | Description | Units |
|--------------|------------------------------------------------------|-------------|
| InvoiceNo | A unique 6-digit number for each transaction. Cancellations are marked with "C". | - |
| StockCode | A 5-digit number uniquely identifying each product. | - |
| Description | The name of the product sold. | - |
| Quantity | The number of units purchased per transaction. | Units |
| InvoiceDate | The exact date and time of the transaction. | Date & Time |
| UnitPrice | The price per unit of each product (in GBP). | GBP |
| CustomerID | A unique 5-digit ID assigned to each customer. | - |
| Country | The customer's country of residence. | - |

The data includes a variety of customers, including wholesalers, and spans about a year.

---

### Data Preprocessing

To prepare the data for RFM analysis, several preprocessing steps were carried out:

1. **Handling Missing Values**: Missing or erroneous values (like canceled transactions) were conditionally filtered out.  
2. **Date Parsing**: InvoiceDate was converted to datetime format for recency calculations.  
3. **Feature Engineering**: RFM metrics were calculated from the transactional data:  

   - **Recency**: The time since the customer's last transaction (based on positive offer price transactions).  
   - **Frequency**: The number of transactions made by the customer (based on positive offer price transactions).  
   - **Monetary**: The total spending per customer (including returns).  

---

### RFM Analysis

RFM segmentation categorizes customers based on three key metrics:

- **Recency (R)**: Measures how recently a customer made a purchase.  
- **Frequency (F)**: Measures how often a customer makes purchases.  
- **Monetary (M)**: Measures how much a customer spends (including returns).  

The segments are created using thresholds derived from percentiles for each of the three metrics.

---

### Customer Segmentation and Insights

#### Segmentation and Profiling

Based on RFM analysis, customers are segmented as follows:

- **Champions**: Top-tier customers who shop very recently, very frequently, and spend high.
- **Loyal Customers**: Regular customers who shop often and recently, even if their basket value is not always at the highest level.
- **Potential Loyalists**: Customers showing promise with moderate frequency and recency but high spend.
- **New Acquisition**: Recently acquired or re-engaged shoppers who have not yet become routine or high spenders.
- **Need Attention**: Customers whose engagement is slipping and are shopping less frequently or spending less.
- **At Risk**: Previously valuable customers who have not purchased in a long time.
- **Hibernating**: Very infrequent buyers who still generate some value when they shop.
- **About to Sleep**: Customers close to churn with low recent activity and low spending.
- **Lost**: Fully disengaged customers with no recent, frequent, or valuable purchases.

---

#### Mapping Logic

The following logic maps RFM thresholds (Recency, Frequency, Monetary) to customer segments:

- **H**: High  
- **M**: Medium  
- **L**: Low  

##### Segment Mapping

1. **Champions**  
   - **Conditions**: H-H-H, M-H-H, H-M-H  
   - **Definition**: Top-tier customers who shop very recently, very frequently, and spend high.  

2. **Loyal Customers**  
   - **Conditions**: H-H-M, M-H-M, H-M-M, H-H-L, M-H-L  
   - **Definition**: Regular customers who shop often and recently, even if their basket value is not always at the highest level.  

3. **Potential Loyalists**  
   - **Conditions**: M-M-H, M-M-M  
   - **Definition**: Customers showing real promise with moderate frequency and recency but high spend, making them ideal for targeted loyalty programs.  

4. **New Acquisition**  
   - **Conditions**: H-M-L, H-L-M, H-L-L  
   - **Definition**: New or re-engaged shoppers with recent activity but not yet consistent or high spenders.  

5. **Need Attention**  
   - **Conditions**: M-L-H, M-M-L, H-L-H, M-L-M, M-L-L  
   - **Definition**: Customers whose engagement is declining and require proactive retention strategies.  

6. **At Risk**  
   - **Conditions**: L-H-H, L-M-H, L-H-M  
   - **Definition**: Dormant but formerly valuable customers who used to be frequent or high spenders but have not purchased recently.  

7. **Hibernating**  
   - **Conditions**: L-L-H, L-L-M, L-M-M  
   - **Definition**: Infrequent buyers with low recency and frequency but still contributing some monetary value.  

8. **About to Sleep**  
   - **Conditions**: L-M-L, L-H-L  
   - **Definition**: Customers close to churn with low spend and low recent engagement who need immediate win-back offers.  

9. **Lost**  
   - **Conditions**: L-L-L  
   - **Definition**: Fully disengaged customers with no recent, frequent, or valuable purchases.  

---

#### Customer Insights and Recommendations

##### Segment Distribution and Strategies:

- **Champions**  
  - **Insights**: Highly engaged and high-value customers.  
  - **Recommendation**: Reward with exclusive perks, early access to sales, and VIP programs.  

- **Loyal Customers**  
  - **Insights**: Consistent and reliable buyers.  
  - **Recommendation**: Encourage higher basket size through cross-sell and loyalty incentives.  

- **Potential Loyalists**  
  - **Insights**: Promising customers with strong spending behavior.  
  - **Recommendation**: Nurture with personalized campaigns to convert them into Champions.  

- **New Acquisition**  
  - **Insights**: Recently acquired or re-engaged customers.  
  - **Recommendation**: Run onboarding campaigns and targeted offers to increase repeat purchases.  

- **Need Attention**  
  - **Insights**: Engagement is weakening.  
  - **Recommendation**: Use personalized reminders and limited-time incentives to prevent churn.  

- **At Risk**  
  - **Insights**: Previously high-value customers who have become inactive.  
  - **Recommendation**: Launch strong win-back campaigns with compelling offers.  

- **Hibernating**  
  - **Insights**: Low engagement but occasional value contribution.  
  - **Recommendation**: Use periodic reactivation campaigns with moderate incentives.  

- **About to Sleep**  
  - **Insights**: Close to churn with low spend and recency.  
  - **Recommendation**: Provide urgent win-back offers and personalized communication.  

- **Lost**  
  - **Insights**: Fully disengaged customers.  
  - **Recommendation**: Consider deep discount campaigns or exclude from high-cost marketing efforts depending on ROI.  

---

This segmentation framework ensures clarity and provides actionable strategies to enhance customer engagement, retention, and value.

### Conclusion

RFM segmentation helps identify distinct customer groups based on their purchasing behaviors, enabling more targeted marketing campaigns. By understanding customer engagement and tailoring strategies for retention, growth, and re-engagement, businesses can maximize the value of each customer.

Future steps may include predictive modeling and more refined segmentation for further optimization of marketing efforts.

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