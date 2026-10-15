# End-to-End-E-commerce-Retail-Return-And-Performance-Analysis
An end-to-end e-commerce return analysis project using SQL Server and Power BI to analyse sales performance, return rates, refunds, profitability, and customer return behaviour, with actionable business recommendations.
## Table of Content
 - [Executive Summary](#executive-summary)
 - [Project Overview](#project-overview)
 - [Data Source](#data-source)
 - [Problem Statement](#problem-statement)
 - [Tools and Methodology](#tools-and-methodology)
 - [Exploratory Data Analysis](#exploratory-data-analysis)
 - [Key Insights](#key-insights)
 - [Dashboard Preview](#dashboard-preview)
 - [Recommendations](#recommendations)
 - [Limitations](#limitations)
 - [Conclusion](#conclusion)
## Executive Summary

This project analyzes e-commerce sales and product returns to evaluate business performance, assess the financial impact of returns, and identify the major factors driving returned orders. Using a dataset comprising six interconnected tables covering orders, products, customers, sales channels, return reasons, and payment methods, the analysis examines sales performance, profitability, refund amounts, return rates, and return patterns across product categories and time periods.

The analysis reveals an overall return rate of 24.03%, with Fashion recording the highest category return rate at 26.15%. Wrong size emerged as the leading return reason, highlighting a potential issue with product sizing information and customer purchase decisions. The analysis also identified recurring losses in the Electronics category during November, December, and May, indicating that strong sales activity does not always translate into profitability.

Key findings suggest that improving product sizing information, addressing the leading causes of returns, and reviewing the profitability of underperforming product categories could help reduce avoidable returns and protect profit margins. The project demonstrates how SQL and Power BI can be used to transform raw e-commerce data into actionable insights that support better business decisions.

## Project Overview
This project focuses on analyzing e-commerce sales and product return data to understand the factors influencing return behavior, financial performance, and customer purchasing patterns. The analysis uses interconnected datasets covering orders, products, customers, sales channels, return reasons, and payment methods to provide a comprehensive view of the business's performance and return management process.

The project was undertaken to help stakeholders understand the financial implications of product returns, identify the products and categories most affected by returns, and uncover opportunities to improve profitability and customer experience. Using SQL for data analysis and Power BI for interactive visualization, the analysis addresses the following core business challenges:

- Evaluating sales performance, profitability, and net revenue after accounting for discounts and refunds.
- Measuring return rates and assessing their impact on overall business performance.
- Identifying product categories with the highest return rates and greatest financial exposure.
- Investigating the major reasons for product returns and identifying potential areas for improvement.
- Analyzing return patterns across sales channels, payment methods, and time periods.
- Developing actionable recommendations to reduce avoidable returns, minimize financial losses, and improve business decision-making.

## Data Source
The dataset comprises of 4,287 recorded e-ecommerce retail 2025 transactions across multiple product categories and customer segments and sales channel. It is a transactional dataset encompassing structured attributes such as order details, product categories, customer segments, sales channel, profit, sales revenue, discount rates, and return status

## Problem Statement

The e-commerce business faces several interconnected challenges related to product returns, profitability, and customer purchasing behavior. High return rates can reduce net revenue, increase refund costs, and affect overall business performance. Without a clear understanding of the factors driving returns and their financial implications, management may struggle to identify underperforming product categories, address recurring return issues, and implement effective return reduction strategies. This project seeks to provide data-driven answers to the following critical business questions:

1. What are the overall sales performance, profitability, and return rates, and how do product returns affect net revenue and profit?
2. Which product categories record the highest return rates, and how do returns affect their financial performance?
3. What are the leading reasons for product returns, and which issues present the greatest opportunities for reducing return frequency?
4. How do return rates and financial outcomes vary across sales channels, payment methods, and product categories?
5. How do return patterns change over time, and which periods experience the highest return activity and associated financial impact?
6. Which product categories and return reasons should management prioritize to minimize refund losses and improve business performance?

**Business Implication:** Failure to address these questions may result in continued avoidable returns, reduced net revenue, recurring product-level losses, and missed opportunities to improve customer satisfaction and profitability. By identifying the major return drivers and quantifying their financial impact, the business can develop targeted strategies to strengthen return management and support data-driven decision-making.
## Tools and Methodology 

Tools Used

 - SQL- Analysis 
 - Power Query - Initial data exploration, cleaning, and validation
 - Power BI - Interactive dashboard development, DAX measures, and data modeling
 - DAX (Data Analysis Expressions) - Calculated Metrics, Custom Logic, SVG visuals, dynamic insights

## Methodology 
# Data Cleaning and Preparation
The following data quality steps were performed to ensure analytical reliability

   - Validated order date fields to ensure chronological integrity.
   - Standardized category names, return flags, payment methods, and sales channels by capitalizing values consistently.
   - Enforced naming consistency across tables and fields.
   - Validated and corrected data types and formats to support accurate calculations.
   - Identified and treated duplicate records where necessary.
   - Applied appropriate data formatting to improve data usability and consistency.

## Data Transformation and KPI Calculation
The following calculated metrics were developed in Power BI to support the analysis
  - Revenue: Quantity x Unit_Price (1-Discount_pct)
  - Refund Amount: Return_Quantity x Unit_Price x(1-Discount_pct) x(1-Refund_Deduction_pct)
  - Net Revenue: Revenue-Refund_amount
  - Cost of Goods: Quantity x Unit_cost
  - Profit: Revenue-Cost of goods-Refund amount
  - Profit Margin: Profit/Revenuie
  - Total Orders: Distinct count of Order_id
  - Returned Orders: Distinct count of Order_id, where Return_flag is Yes
  - Return Rate: Divide(Returned orders, Total orders) x 100

## Data Model
A star schema model was designed in Power BI by transforming the original retail order dataset in Power Query into a structured data model. This involved creating a central Fact Table supported by multiple Dimension Tables, including Customer, Products,channel,Return reason,and payment method.

One-to-many relationships were established between the fact table and each dimension table to ensure efficient data organization, improved query performance, and accurate aggregations during analysis.

Additionally, a dedicated Calendar Table was created and linked to the fact table via the Order Date field. This enabled the use of time intelligence functions such as month-over-month comparisons, enhancing the depth and flexibility of the analysis.

<img width="1541" height="790" alt="Screenshot 2026-10-09 013152" src="https://github.com/user-attachments/assets/20652d6a-b12b-468f-a245-263bef9ead1a" />


## Dashboard Structure
Three interactive Power BI dashboard pages were developed to answer the business case questions:

• Page 1 — Business Overview : Revenue, profit, net revenue, top customers • Page 2 — Return analysis: Most returned product ,return rate by sales channel, Return rate by payment method • Page 3 — Return Drivers : Return reasons

## Exploratory Data Analysis
- Key Patterns

Initial analysis revealed differences in return performance and profitability across product categories. Fashion recorded the highest category return rate at 26.15%, exceeding the overall return rate of 24.03%. Wrong size emerged as the leading return reason, suggesting that product sizing information and customer expectations are important areas for further investigation. The analysis also revealed recurring losses in the Electronics category during selected months, highlighting the need to evaluate profitability alongside sales performance.

- Distributions

The analysis examined the distribution of orders, product returns, refund amounts, and profitability across product categories, sales channels, payment methods, and return reasons. Return rates varied across categories, while the concentration of returns around specific reasons provided an opportunity to identify the issues contributing most to return activity. Financial metrics were also evaluated to understand how refunds affect net revenue and profit.

- Trends
- 
  December had the highest order volume, generated the highest revenue but not converting to profit, and highest return rate of  32.16% , with Product Not as Expected, Wrong Size and Damaged Product among the major return factors

Monthly analysis was used to examine changes in sales, profitability, and return activity over time. This made it possible to identify periods of elevated business activity and assess whether strong sales performance coincided with improved profitability. The analysis also highlighted recurring Electronics losses in November, December, and May, indicating that profitability should be monitored across individual months rather than assessed using sales volume alone.

- Outliers and Areas of Concern
  
 Electronics generated approximately ₦8.21 million, making it the highest-revenue category. However, the category contained several loss-making products.The five identified loss-making Electronics products were,SonicBay Bluetooth Speaker (-$79,973.59), PlusTech Over-Ear Headphone (-$35,239.30), PixelNest Streaming Stick (-$34,465.89), HomeSync Digital PhotoFrame (-$22,678.08), SonicBay Studio Headphone (-$1,218.89).

Fashion's 26.15% return rate stood out as a key category-level concern, while Wrong size emerged as the leading return reason. The recurring negative profit recorded by Electronics in November, December, and May also warranted further investigation. These findings identify priority areas for deeper analysis, although additional product-level and transaction-level evidence would be required to establish the specific causes of the losses and returns.

UPI accounts for the highest payment volume, with 1,268 orders and a 23.82% return rate. Among the other payment methods, Credit Card records a 27.14% return rate across 711 orders, Debit Card 21.29% across 498 orders, Cash on Delivery 23.15% across 311 orders, Wallet 23.76% across 181 orders, Net Banking 23.96% across 96 orders, and Cash 17.14% across 35 orders.


## Key Insights

- The business recorded an overall return rate of 24.03%, indicating that returned orders represent a significant area for improvement. Returns can reduce retained revenue through refunds and increase operational costs associated with processing returned products. Monitoring return rates alongside refund amounts, net revenue, and profit will help management identify the categories and products creating the greatest financial exposure and prioritize corrective actions accordingly.

- Fashion recorded the highest return rate at 26.15%, exceeding the overall return rate of 24.03%, with Wrong Size as its leading return reason. Electronics returns were primarily driven by Defective Product, while Beauty returns were associated with Product Not as Expected. Damaged Product was the leading return reason for both Home and Kitchen and Books. These category-specific issues can increase refund expenses, handling and replacement costs, and customer dissatisfaction. 
  
- Electronics recorded losses of $16,112.56 in December, $6,710.75 in November, and $801.68 in May, despite generating sales during these periods.The recurring losses suggest that revenue generation alone is insufficient to ensure category profitability. Management should review product-level costs, discounting, sales mix, and refund deductions to identify the transactions responsible for the losses. Addressing these issues could improve profit retention and prevent recurring losses from undermining overall business performance.

- Consumer customers account for approximately 59% of customers and orders and contribute 60.14% of total profit, making them the largest contributor to business profitability. However, return rates are relatively similar across segments, with Consumer at 24.40%, Corporate at 24.17%, and Home Office at 22.25%. This indicates that the return problem is not concentrated in a single customer segment, although Home Office records the lowest return rate. 
  
- The Website generates the highest order volume, with 1,019 orders (32.9%) and a return rate of 21.39%. Marketplace records the highest channel return rate at 26.67% across 806 orders, followed by Mobile App at 25.83% across 968 orders. Offline Store has the lowest return rate at 20.20%, although it accounts for only 307 orders. The higher return rates on Marketplace and Mobile App indicate that these channels require closer monitoring. Improving product listing accuracy and ensuring consistent product information across channels could help reduce avoidable returns and associated refund costs.

## Dashboard Preview
Three interactive Power BI dashboards were developed to present the findings of this analysis. Each page is designed to answer a specific set of business questions with KPI cards and dynamic visuals.

Page 1 - Business Overview
Covers Total revenue, Refund amount, Net revenue, Profit, Total orders and Return rate including who are our customers, most ordered product category, sales channel with the highest order, order by payment method, sales by category and sales trend

<img width="1295" height="736" alt="Screenshot 2026-10-09 043410" src="https://github.com/user-attachments/assets/bac9b25f-053a-4c76-adc1-b0cd7e615394" />

Page 2 - Return Analysis
Covers Return rate by category, Return rate by customer segment, Return rate by sales channel, return rate by payment method and product overview with months as slicer

<img width="1303" height="733" alt="Screenshot 2026-10-09 043520" src="https://github.com/user-attachments/assets/784e9654-6d01-4da6-809d-f8a94b4f50aa" />

Page 3 - Return Drivers 
Display highest return reason, return rate trend, and return rate by subcategory with product-category and customer segment as slicer

<img width="1292" height="730" alt="Screenshot 2026-10-08 152721" src="https://github.com/user-attachments/assets/e03e680f-e9ec-4722-a803-f6f86b7e0ce1" />

## Recommendations

 - Review loss-making Electronics products: Investigate unit costs, selling prices, discounts, refunds and return quantities before deciding whether to reprice, improve quality or discontinue individual products.
 - Add quality gates and protective packaging for electronics. Introduce pre-shipment inspection for Audio, Mobile Accessories, and Smart Devices, recover the cost of defective units through supplier chargebacks, and upgrade packaging for fragile items.
 - Introduce fit guidance across fashion . Add measurement-based size charts, fit notes, and customer fit feedback to every footwear and clothing listing, starting with Men's Clothing and Footwear. Review sizing and quality of StrideX Running Sneakers and Northlane Slim Fit Jeans with suppliers.
 - Close the expectation gap in product content . Audit images, dimensions, materials, and descriptions for Home Furnishing, Personal Care, and Skin Care listings, beginning with DermaNest Night Repair Cream and Casabloom Table Runner Set. Add real-use photos and clear specifications.
 - Improve packaging and order accuracy for Kitchen and Books . Reinforce packaging for Kitchen products and add pick-and-pack verification to reduce damaged and wrong-item shipments.
 - Prepare for the next peak season. Run pre-peak quality checks on electronics, publish sizing and delivery guidance early, add packing capacity, and monitor return rate weekly from October with defined escalation triggers.
 - Align Mobile App and Marketplace with the Website. Bring product content on these channels up to Website standard and review Marketplace listing quality. Analyse returns by product within each channel to separate channel effects from product mix.
 - Protect and promote high-profit, low-return products. Prioritise stock and promotion for the Air Fryer, Induction Cooktop, Blackout Curtains, and FootNest Block Heel Sandal. Fix, rather than delist, profitable high-return items such as MiraMode Cotton Kurta Set and MoveMax Kettlebell.
 - Monitor financial and return performance together: Use return rate, refund amount and profit to identify products that pose the greatest business risk.

## Limitations
 - The analysis is based on the available 2025 dataset and therefore reflects the information contained within that period.
 - The analysis identifies patterns and associations but does not establish causation, For example,the negative Electronics profit observed in May, November and December does not prove that returns caused the losses.
 - The available data does not provide enough information to isolate every possible operational cause of returns, such as individual supplier performance, packaging quality, warehouse handling or delivery partner performance.
 - Profitability is dependent on the definitions and calculations used for revenue, cost, refunds and deductions within the project.

 ## Conclusion
This analysis demonstrates that e-commerce returns should be evaluated as a business performance issue rather than solely a customer-service metric.
The business achieved significant sales volume during 2025, but returns represented a substantial financial exposure. More importantly, the analysis revealed that return and profitability problems are concentrated differently across products, categories and periods.
Electronics provides the clearest example. Although it generated the highest revenue, it contained several loss-making products and experienced negative profitability in May, November and December. At the same time, Electronics had a distinct return profile dominated by defective and damaged products.
Fashion presents a different problem: its return rate was the highest among the major categories, with wrong size being the dominant driver.
These findings indicate that the business should move away from a single return-reduction strategy and instead adopt targeted interventions based on product, category, channel and return reason.
The most important management opportunity is therefore not simply to reduce the number of returns. It is to identify which returns are financially significant, why they occur, and which interventions are most likely to improve profitability without unnecessarily restricting sales
















