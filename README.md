# Anand EcomExpress Sales Dashboard
An end‑to‑end Power BI analytics solution delivering executive‑level visibility into ecommerce performance. Designed to support revenue growth, margin optimization, and strategic decision‑making across products, regions, and customer segments.​
## Project Overview
The Anand EcomExpress Sales Dashboard is a production‑style Power BI report that consolidates order, product, and customer data into a single interactive view. It tracks revenue of $1.25bn, an AOV of $112.85K, $525.42M lost to cancellations, a 29.72% cancellation rate, and 15.69K total orders through dynamic KPIs and drill‑down visuals.​

The dashboard is intended for senior leadership, category managers, and analytics teams who need fast, self‑service answers to questions such as “Which products and states drive our revenue?” and “Where are we losing value due to cancellations?”.
## Scope, Data, and Modeling
### Data Coverage
- Granular order‑level data including order ID, purchase timestamp, quantity, delivery status, and delivery time.​

- Product attributes: product ID, product name, category (Laptop, Mobile, Headphones, etc.), price, rating, and number of raters.​

- Customer attributes: customer ID, full name, city, state, phone brand, OS, and contact details.​

- Aggregated metrics table containing revenue, AOV, cancellation value, and cancellation rate for efficient KPI computation.​
### Data Model

- Central Orders fact table linked in one‑to‑many relationships to Products and Customers, forming a clean star schema that supports robust filtering and drill‑through analysis.​

- Dedicated Metrics table for reusable measures such as revenue, AOV, and lost revenue from cancellations, enabling consistent KPI definitions across all visuals.​

- This modeling approach ensures high query performance, maintainability, and clear semantic layers that   mirror real business processes.

 ## Technology and Implementation
- **Power BI Desktop** – Core platform for report development, interaction design, and publishing.​

- **Power Query** – Applied to profile, cleanse, and transform raw CSV/Excel sources (type casting, null handling, normalization of categories).​

- **DAX (Data Analysis Expressions)** – Used to create robust business measures such as Total Revenue, AOV, Cancellation Rate, and trend calculations.​

- **Professional Data Modeling** – Enforced referential integrity, surrogate keys on dimension tables, and clear separation of measure logic from raw columns for enterprise readability.​
## Illustrative DAX Measures
```
Total Revenue =
SUM ( 'Table'[revenue] )

Average Order Value (AOV) =
DIVIDE (
    SUM ( 'Table'[revenue] ),
    DISTINCTCOUNT ( Orders[OrderID] ),
    0
)

Lost Revenue – Cancellation =
SUM ( 'Table'[lost_rev_cancellation] )

Cancellation Rate % =
DIVIDE (
    [Lost Revenue – Cancellation],
    [Lost Revenue – Cancellation] + [Total Revenue],
    0
)
```
These measures are used consistently across cards, charts, and tooltips, so decision‑makers always see a single version of the truth.

## Analytical Experience and Key Visuals
### Executive KPI Strip

- **Revenue:** $1.25bn

- **AOV:** $112.85K

- **Lost Revenue – Cancellation:** $525.42M

- **Cancellation Rate:** 29.72%

- **Total Orders:** 15.69K​

This panel functions as a real‑time health check for the business and reacts instantly to all filters (category, date range, etc.).​

### Product Performance

- Revenue by Product Name bar chart surfaces top performers such as high‑value laptops and smartphones (e.g., MacBook Air, OnePlus devices), enabling SKU‑level profitability reviews and assortment decisions.​

- Revenue by Category highlights Laptops as the primary revenue engine, followed by Mobile, Headphones, and other accessories, clarifying which categories merit deeper investment.​

### Geographical Insights

- Revenue by State shows Maharashtra and Gujarat as the strongest markets, followed by Rajasthan, West Bengal, Tamil Nadu, Karnataka, Delhi, and Telangana.​

- Stakeholders can quickly prioritize marketing budgets and inventory allocations toward high‑yield states while identifying whitespace regions for expansion.​

### Time‑Series Trend

- Revenue by Year, Quarter and Month line chart tracks performance from January to November 2024, revealing a stable pattern around $100M–$150M before a sharp decline in November.​

- This sudden drop acts as an early‑warning signal to investigate stock‑outs, pricing changes, or operational disruptions.​

### Interaction Design

- Category buttons (Accessory, Charger, Laptop, Mouse, Tablet, Cable, Headphones, Mobile, Speaker) act as intuitive slicers, enabling non‑technical users to explore the business from different angles in a single click.​

- Global date slicers and cross‑filtering between visuals support rich “click‑to‑explore” storytelling without leaving the main page.​

## Business Value and Executable Insights
This dashboard is positioned as a decision‑support asset rather than a static report. It delivers:

### Revenue Growth Opportunities

- Double‑down on Laptop and Mobile categories, which consistently rank at the top of revenue charts.

- Use insights from under‑performing categories (e.g., certain accessories) to refine catalog and bundling strategies.​

### Margin Protection

- A cancellation rate near 30% and over $525M in lost revenue directly highlight process issues in delivery, expectations, or product quality, guiding targeted operational fixes.​

### Regional Strategy

- Focus account management and local campaigns on Maharashtra and Gujarat while nurturing high‑potential states like Rajasthan and West Bengal.​

### Monitoring & Governance

- Single, governed source of truth for KPIs reduces dependency on ad‑hoc spreadsheets and aligns all stakeholders around consistent metrics.​

























