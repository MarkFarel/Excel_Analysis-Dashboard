# 📊 Excel Sales Analysis Project

## 📝 Project Overview
This case study focuses on analyzing product sales data using **Excel formulas only**, without PivotTables. The dataset includes details of transactions such as **Month**, **Seller**, **Category**, **Product**, **State**, **Quantity**, **Sales**, and **Profit**.

Participants were tasked with cleaning the data and deriving insights related to **sales performance**, **profitability**, and **regional trends**.

---

## 🧼 Data Cleaning Steps

The original dataset required cleaning before analysis:

- **Sales and Profit Columns**  
  - These were stored as **text values** with dollar signs (`$`).  
  - Used Excel formula:  
    ```excel
    =VALUE(SUBSTITUTE(G2,"$",""))
    ```
    to convert them into numeric format.

- **Month Column**  
  - Some entries had extra spaces or inconsistent capitalization (e.g., `" jan"`, `"JUL"`, `"Nov "`). I also utilized **Find and Replace** to correct common misspellings
  - Used:
    ```excel
    =PROPER(TRIM(A2))
    ```
    to standardize the format (e.g., "Jan", "Feb", … "Dec").
 
    

- **Seller and State Columns**  
  - Cleaned to remove leading/trailing spaces with:
    ```excel
    =TRIM(B2)
    ```
  - Ensured consistency in capitalization using `=PROPER()`.
  -  utilized **Find and Replace** to correct common misspellings or abbreviations such as "NY for New York"

---

### Profit Margin Calculation Using "Add Measure"

1. **Profit Margin Measure**:
   - To calculate the **Profit Margin**, I used the **Add Measure** feature in Power BI. This allows us to create a dynamic formula that calculates profit margin for each transaction, category, or any other dimension.
   - The formula used to create the Profit Margin measure is:
     ```DAX
     Profit Margin = DIVIDE(SUM('Sales'[Profit]), SUM('Sales'[Sales]), 0) * 100
     ```
     This formula divides the total profit by the total sales and multiplies it by 100 to get the percentage.

2. **Using the Measure**:
   - Once the measure is created, it can be added to your visualizations to dynamically display the profit margin across different categories, months, sellers, or states.
   - This helps in analyzing profitability at a more granular level, such as by product category or by seller.

3. **Dynamic Calculation**:
   - The beauty of using **Add Measure** in Power BI is that the **Profit Margin** measure will adjust based on the context of the visual (e.g., if you filter by a specific month, seller, or product category, the profit margin will update accordingly).

## Project Overview and Deliverables Summary

We used PivotTables in Excel to analyze and summarize the dataset for key metrics, including:

 1. **Total Sales and Profit:**
- Calculated total sales, profit, and profit margin.

 2. **Monthly Sales and Profit:**
- Analyzed sales and profit trends by month.

3. **Sales and Profit by Seller:**
- Summarized total sales and profit for each seller.

4. **Sales and Profit by Category:**
- Breakdown of sales and profit by product category, along with profit margins.

 5. **Sales and Profit by State:**
- Examined sales and profit performance across different states.

Using PivotTables, we easily organized and aggregated the data to provide insights into the performance across various dimensions.

## Key Insights

- **Grace** achieved the highest profit among all sellers.
- **June** and **April** had strong sales performance, suggesting seasonal patterns.
- **Florida** stands out with the highest state profit margin of **50%**.
- **Electronics** performed well in sales but with a slightly lower margin compared to other categories.
- **Home Appliances** had the highest category-level profit margin (**49%**).

## Dashboard Development

After analyzing the dataset and uncovering key insights, we proceeded to build a comprehensive **Excel dashboard** to visualize the results. The dashboard provides an interactive interface for stakeholders to explore the data and key metrics easily.

### Key Components of the Dashboard:
- **Total Sales & Profit**: Displays the aggregate values of sales and profit.
- **Monthly Trends**: A chart showing sales and profit performance over the months to identify seasonal trends.
- **Top Sellers**: Highlights the top sellers based on sales and profit.
- **Profit Margin by Category**: A visual comparison of profit margins across product categories.
- **State Performance**: Breakdown of sales and profit by state, with profit margin insights.

The dashboard was designed to be interactive, allowing users to filter by month, seller, category, or state to explore the data more deeply.
