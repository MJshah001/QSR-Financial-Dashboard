# QSR-Financial-Dashboard


Welcome to the **Crunchy Corner QSR Dashboard** project! This repository showcases an end-to-end solution designed for one of the largest fast-food restaurant chains, **Crunchy Corner**, serving millions of customers daily across 1,000+ restaurants. The primary goal of this dashboard is to provide actionable insights into the company’s financial performance, business operations, and budgeting strategies, helping decision-makers optimize their resources and increase profitability.

## Table of Contents

- [Business Overview](#business-overview)
- [Client Requirements](#client-requirements)
- [Data Modeling](#data-modeling)
- [Financial Performance Analysis](#financial-performance-analysis)
  - [Performance Analysis](#performance-analysis)
  - [Cost Analysis](#cost-analysis)
  - [Revenue Analysis](#revenue-analysis)
- [Business Optimization Analysis](#business-optimization-analysis)
  - [Pareto Analysis](#pareto-analysis)
  - [Category Analysis](#category-analysis)
  - [Profit Analysis](#profit-analysis)
  - [PVM Analysis](#pvm-analysis)
  - [Variance Analysis](#variance-analysis)
- [Financial Planning & Budgeting Analysis](#financial-planning--budgeting-analysis)
  - [Actual vs Budget Financial Analysis for Business Drivers](#actual-vs-budget-financial-analysis-for-business-drivers)
  - [Actual vs Budget Financial Analysis for Cost Drivers](#actual-vs-budget-financial-analysis-for-cost-drivers)

---


## Business Overview

Crunchy Corner is a market leader in the fast-food industry, with a presence in numerous cities and one of the largest SKUs in the sector. With such a vast network and diverse operations, data-driven decision-making is essential to maintaining profitability, optimizing operational efficiency, and effective budgeting.

### Project Objectives

This project involved creating a comprehensive dashboard in Power BI to meet the following key objectives:
- **Financial Performance Tracking**: Gain real-time insights into revenue and cost trends across multiple dimensions (e.g., region, category, time).
- **Business Optimization**: Identify areas for operational improvement and strategic focus.
- **Budgeting and Forecasting**: Provide tools for accurate financial planning, helping the business allocate resources wisely.

The dashboard integrates various forms of analysis (performance, cost, revenue, optimization, and budgeting) and dynamic user inputs to allow interactive exploration of the data.

---

## Client Requirements

Crunchy Corner requested a dashboard that could:
- **Monitor financial performance**: Track revenue, costs, and key financial metrics across different regions and categories.
- **Optimize business operations**: Provide insights that could guide decision-makers toward the most profitable areas and suggest where improvements could be made.
- **Assist with budgeting**: Enable financial planning by forecasting future revenue and expenses based on historical data and trends.

The dashboard is designed to meet these needs through an intuitive and dynamic interface, offering various interactive features and visualizations to help guide business strategy.

---

## Data Modeling

Behind this powerful dashboard lies robust data modeling, which serves as the backbone for all analysis. A well-structured **Snowflake schema** is employed, ensuring optimal performance and clarity in data relationships.This schema supports complex relationships between various entities, enabling detailed analysis while maintaining performance and data integrity.

### Schema Overview

The data model consists of:
- **2 Fact Tables**: Capturing both actual and budget data.
- **9 Dimension Tables**: Providing detailed contextual information for the analysis.
- **Measure/Parameter Tables**: Supporting dynamic calculations and custom inputs for interactive analysis.

### Fact Tables

1. **Fact_Actual**: Contains the business's actual performance data, including key metrics such as actual revenue and costs. This fact table is connected to multiple dimensions, allowing for detailed analysis across time, location, and product categories.
2. **Fact_Budget**: Stores the budgeted performance data, providing a basis for comparison against actuals. Like the actuals fact table, this is linked to various dimensions to allow for flexible and in-depth comparisons.

Both fact tables are integral to the **Actual vs Budget** comparisons across key business drivers and cost drivers, enabling stakeholders to track whether the business is meeting its financial targets.

### Dimension Tables

The dimension tables in this schema provide contextual details for the fact data, enabling detailed breakdowns and filtering across various aspects of the business.

- **Dim_Date**: Contains date information, enabling time-based analysis such as year, quarter, month, and day.
- **Dim_Location**: Holds location-specific data (e.g., city, region), allowing performance tracking across geographic areas.
- **Dim_Cluster_Head**: Represents leadership clusters, supporting performance comparisons across different teams and regions.
- **Dim_Channel**: Stores sales channel data (e.g., online, in-store), helping the business analyze revenue and costs by channel.
- **Dim_SKU**: Holds stock-keeping unit (SKU) information, providing the foundation for product-level analysis.

#### Snowflake Structure for Product Hierarchy

The **Dim_SKU** table forms the core of a hierarchical structure, connecting to additional dimension tables that capture product details at varying levels of granularity:
- **Dim_Product**: Contains higher-level product details.
- **Dim_Sub_Product**: Breaks down products into more specific categories.
- **Dim_Category**: Provides category-level data, grouping products into broader categories.
- **Dim_Sub_Category**: Further refines the product hierarchy into sub-categories for deeper analysis.

This snowflake design allows for a comprehensive view of the product hierarchy, making it possible to analyze performance at any level, from the broad category view to specific SKUs.

### Measure/Parameter Tables

In addition to the fact and dimension tables, the model includes **measure and parameter tables**, which store calculations and custom inputs used for dynamic analysis in the dashboard. These tables help compute metrics such as percentages, variances, and other key performance indicators (KPIs), ensuring that the dashboard provides actionable insights in real time.

Data is pre-processed and transformed to ensure quality, consistency, and accuracy, enabling the smooth and efficient operation of the dashboard's interactive elements.

---

## Financial Performance Analysis

The **Financial Performance** section of the dashboard provides critical insights into the overall health of the business. By analyzing key metrics such as **revenue**, **costs**, and **profits**, stakeholders can monitor trends, compare performance across different regions and categories, and identify areas that require attention.

### 1. Performance Analysis

This section presents a high-level view of the company's overall performance through key performance indicators (KPIs). It allows users to:
- **Track trends over time**: Visualizations display how revenue, costs, and profit have evolved.
- **Monitor key metrics**: Analyze KPIs like revenue growth, cost efficiency, and profit margins.

**Dynamic User Inputs**: Users can filter data by different dimensions such as **time periods**, **regions**, and **product categories**, offering flexibility to drill down into specific performance areas.

### 2. Cost Analysis

A detailed breakdown of **costs** is available in this section, covering both **fixed** and **variable costs**. Understanding how costs are distributed across operations is critical for identifying inefficiencies and potential areas for cost-saving.

Key insights include:
- **Operational costs**: Review the total operational expenses, broken down by different categories.
- **Cost distribution**: See where costs are concentrated and which areas may need further optimization.

**Dynamic User Inputs**: Similar to performance analysis, users can filter cost data by **region**, **category**, and **time** to gain a granular view of cost structures.

### 3. Revenue Analysis

The **Revenue Analysis** section provides detailed insights into how the company generates income, highlighting top-performing regions, product categories, and time periods.

Key features include:
- **Revenue breakdown**: View revenue by product category, region, or period.
- **High-performing areas**: Quickly identify which products or regions are driving the most revenue.

**Dynamic User Inputs**: Users can select from different dimensions such as **region**, **category**, or **time** to explore revenue trends and identify the most profitable segments of the business.

---

## Business Optimization Analysis

The **Business Optimization Analysis** section is designed to identify key opportunities for improving the profitability and efficiency of the business. This section leverages dynamic inputs and advanced analytics to help users explore various optimization strategies in real time.

### 1. Pareto Analysis

The **Pareto Analysis** uses the **80/20 rule**, showing that 80% of revenue often comes from 20% of the products or categories. This analysis helps businesses prioritize their efforts, focusing on the high-impact areas that contribute the most to revenue.

- **What it does**: The analysis identifies the most critical categories that drive the majority of revenue.
- **How it helps**: By focusing on these top-performing categories, the business can allocate resources more effectively and strategize improvements in other areas.

#### **Dynamic User Inputs**:
- Users can **dynamically adjust the cutoff value** for the Pareto principle (default is set to 0.80). This flexibility allows users to change the ratio to better understand how different groupings contribute to the overall revenue. 
- As the cutoff value is changed, **the entire chart and side table colors update automatically**, providing instant visual feedback and highlighting how the new ratio impacts the business focus.

---

### 2. Category Analysis

The **Category Analysis** focuses on analyzing the performance of different product categories, showing which ones are driving revenue and which may need improvement. This analysis allows businesses to dive deeper into the granular details of their product portfolio, offering insights into each category’s contribution to overall performance.

- **What it does**: Provides a breakdown of performance by product category, identifying top-performing and underperforming categories.
- **How it helps**: It enables the business to make data-driven decisions regarding product offerings—whether to invest more in successful categories or re-strategize underperforming ones.

#### **Dynamic User Inputs**:
- At the top of the dashboard, users can select specific filters such as **channel**, **year**, **cluster head**, and **location**. These filters allow for a more refined analysis based on the business structure.
- By adjusting these filters, users can focus on how different channels or locations perform over time, offering a highly customized view of category performance.

---

### 3. Profit Analysis

The **Profit Analysis** provides an in-depth look at the profit margins across various products and categories, allowing stakeholders to understand where the business is generating the most profit. This section enables strategic decision-making by highlighting high-margin areas and underperforming segments.

- **What it does**: Breaks down profit data by category or product, helping users see which areas generate the most profit.
- **How it helps**: This analysis aids in determining where the business should focus its efforts for maximizing profitability, such as adjusting pricing or focusing on high-margin categories.

#### **Dynamic User Inputs**:
- Users have the option to **toggle between "Revenue" and "Volume" buttons** at the top of the chart. This allows them to switch the perspective of the analysis:
  - **Revenue View**: Focuses on how much profit is being generated based on revenue.
  - **Volume View**: Shows how sales volume is affecting profit margins.
- As users switch between these views, the chart updates in real time, offering insights into how changes in revenue or volume impact overall profitability.

---

### 4. PVM (Profit-Volume Mix) Analysis

The **Profit-Volume Mix (PVM) Analysis** explores the relationship between profit margins and sales volume, helping the business understand how changes in volume and pricing affect profitability. This analysis is particularly useful for businesses looking to optimize their pricing strategy or increase sales volume while maintaining healthy margins.

- **What it does**: Evaluates how the mix between sales volume and profit margin impacts overall profitability.
- **How it helps**: The PVM analysis provides valuable insights into pricing and sales strategies, helping businesses optimize the balance between profit margins and sales volume.

#### **Dynamic User Inputs**:
- Users can **simulate changes in pricing or volume** and observe how those changes would impact overall profitability. For example, by increasing the volume sold or adjusting the pricing, users can see the potential effects on the business's bottom line.
- The dashboard updates dynamically to reflect the impact of these simulations, giving users a powerful tool to test different scenarios.

---

### 5. Variance Analysis

The **Variance Analysis** compares actual performance against projected performance, highlighting areas where the business has either exceeded or fallen short of expectations. This analysis is crucial for identifying deviations from the business plan and allowing for quick corrective actions.

- **What it does**: Shows the variance between projected and actual performance, both for revenue and gross profit.
- **How it helps**: By understanding these variances, the business can make more informed decisions on future forecasts and identify areas where performance did not meet expectations.

#### **Dynamic User Inputs**:
- Users can dynamically input values for **Revenue Variance %** and **Gross Profit Variance %**. As these values are adjusted, the lines in the chart **move dynamically**, and the colors update to reflect changes in the variance.
- This feature allows stakeholders to quickly test different assumptions and see how these variances might affect future financial outcomes.

---

With these advanced features and dynamic inputs, the **Business Optimization Analysis** section of the dashboard offers unparalleled flexibility and insight, enabling stakeholders to make more informed, data-driven decisions. Whether it’s identifying the top 20% of revenue-driving products, simulating profit margins based on volume, or tracking variances in projections, this section equips the business with the tools needed to optimize performance and drive growth.

---


## Financial Planning & Budgeting Analysis

This section of the dashboard focuses on comparing **actual performance** against the **budgeted targets** for both **Business Drivers** (revenue) and **Cost Drivers** (COGS and Packaging). By tracking these comparisons across key dimensions, stakeholders can easily identify areas where the business is performing well or where adjustments may be needed to stay within budget. The analysis includes a visual representation of **how much of the budget was achieved** for each metric, offering a clear and actionable summary.

---

### 1. Actual vs Budget Financial Analysis for Business Drivers

In this analysis, we compare **actual revenue** with **budgeted revenue** across key business dimensions, providing a clear view of the business’s financial performance relative to its goals. This is essential for understanding whether the company is on track to meet its revenue targets.

#### Key Insights:
- **Actual vs Budget Revenue**: The charts present a side-by-side comparison of the actual revenue generated versus the budgeted targets, making it easy to see any variances.
- **Percentage of Budget Achieved**: A line on each chart displays the percentage of the budgeted revenue that was actually achieved, helping users quickly gauge the performance relative to the target.

#### Visuals:
The analysis is broken down into four key dimensions:
1. **Year**: Displays the actual vs budget revenue performance for different years, providing a long-term view of how well revenue goals were met.
2. **Category**: Breaks down the revenue by product category, helping to identify which categories are meeting or exceeding their revenue targets.
3. **Location**: Compares actual vs budget revenue across different locations, offering insights into geographic areas that are performing well or underperforming.
4. **Cluster Head**: Shows revenue performance by cluster heads, enabling the business to track how different leadership teams are performing relative to their revenue goals.

Each chart includes:
- **Actual Revenue** (bars)
- **Budgeted Revenue** (bars)
- **% of Budget Achieved** (line)

**How it helps**:  
This analysis allows the business to closely monitor revenue performance across critical dimensions. By identifying where actual revenue falls short of or exceeds the budget, stakeholders can take targeted actions to address underperformance or capitalize on high-performing areas.

---

### 2. Actual vs Budget Financial Analysis for Cost Drivers (COGS, Packaging)

In this slide, the focus shifts to **cost drivers**, specifically **Cost of Goods Sold (COGS)** and **Packaging Costs**. Comparing actual costs against budgeted costs is essential for managing expenses and maintaining profitability.

#### Key Insights:
- **Actual vs Budget Costs**: The charts show the actual costs versus the budgeted targets, helping stakeholders identify any cost overruns or savings.
- **Percentage of Budget Achieved**: A line on each chart displays the percentage of the budgeted costs that were actually incurred, providing a clear indicator of whether costs are being controlled effectively.

#### Visuals:
This analysis is also broken down across four key dimensions:
1. **Year**: Compares actual vs budget cost performance for different years, offering insights into cost management trends over time.
2. **Category**: Analyzes cost performance by product category, showing where costs are exceeding or staying within budgeted amounts.
3. **Location**: Highlights cost performance across different locations, providing a regional breakdown of cost control.
4. **Cluster Head**: Tracks cost performance by cluster head, enabling stakeholders to assess how different leadership teams are managing their budgets.

Each chart includes:
- **Actual Costs** (bars)
- **Budgeted Costs** (bars)
- **% of Budget Achieved** (line)

**How it helps**:  
This analysis provides a clear view of cost control across various dimensions, allowing the business to monitor whether costs are staying within budget. By identifying categories, locations, or teams where costs are exceeding expectations, decision-makers can take timely corrective actions to prevent budget overruns.

---

### Conclusion

The **Financial Planning & Budgeting Analysis** section of the dashboard equips Crunchy Corner with a powerful tool to compare **actual vs budget** performance for both **Business Drivers** (revenue) and **Cost Drivers** (COGS and Packaging). By providing insights into the **percentage of the budget achieved** across key dimensions—such as year, category, location, and cluster head—this section helps decision-makers ensure that the business stays on track with its financial goals.

With this detailed and interactive analysis, the business can make informed decisions to optimize both revenue generation and cost control, ultimately driving more effective financial management.

---
