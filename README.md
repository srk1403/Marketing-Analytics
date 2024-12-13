# Marketing-Analytics
**Problem Statement**
The objective of this marketing analysis is to understand customer demographics, purchasing behaviors, and campaign performance to optimize marketing strategies and product offerings. Specifically, the analysis aims to:

📌 Identify the key demographic factors driving customer orders and spending.
📌 Determine which products and purchasing channels generate the most revenue.
📌 Evaluate the success and ROI of different marketing campaigns to allocate resources effectively.

**Steps Followed** :-
**1. Data Preparation and Loading **
- Imported customer data into Power BI.
- Segmented data into demographics, products, and campaign categories for focused insights.


**2. Data Visualization**
- Created dashboards for demographics, product performance, and campaign analysis.
- Used visuals like bar charts, pie charts, and KPIs to represent data clearly.


**3. Key Metrics Calculation**
- Total Customers, Orders, and Spend across categories.
- Spend distribution by product type (e.g., Meat, Wine).
- Campaign performance metrics: ROI, Success Rate, and Acceptance Rate.


**4. Segmentation Analysis**
- Grouped customers by age, marital status, income, and location to analyze patterns.
-Evaluated the order count and spend for each demographic segment.


**5. Campaign Analysis**
- Assessed the performance of campaigns based on orders and ROI.
- Identified top-performing campaigns (Campaigns 4 & 6).


6. **Calculated DAX column**  

DAX Formulae used :

**1. ARC1 = DIVIDE(SUM('Marketing+Data'[AcceptedCmp1]),COUNTA('Marketing+Data'[AcceptedCmp1]))**
- where i am finding the Conversion/Acceptance Rate of the the ALL 6 different Campaigns 

**2.C1 Cost = DIVIDE(SUM('Marketing+Data'[Total Spend]),COUNTROWS(FILTER('Marketing+Data', 'Marketing+Data'[AcceptedCmp1] = 1)))**  
- The cost spend on each campaign is found out Individually by Dividing the Total spend by the Accepted orders for a Campaign 

**3. Cmp1 ROI = DIVIDE([C1 Orders],[C1 Cost])**  
- Calculating the Campaign ROI . This is used for all 6 diffferent Campaigns 

**  4. Dashboard Country = 
VAR Sel_value = SELECTEDVALUE('Marketing+Data'[Country])
VAR ct = COUNTROWS(VALUES('Marketing+Data'[Country]))
RETURN 
IF(ct > 2 , 
" PLEASE SELECT ONLY ONE COUNTRY",
IF(ct = 1 , 
 "Conversion Rate " & Sel_value , "Conversion Rate FOR MULTIPLE COUNTRIES")) **

 - This is the DAX Formulae for the Dynamic Textbox Dashboard which Changes to the Country name according to the Country selected in the Slicer 
 
**8. Insights Derivation**
- Highlighted actionable insights for business decision-making:
- 40-60 age group drives 50% of orders.
- Meat and Wine products account for 75% of spend.
- Campaigns 4 and 6 have the highest ROI.
