# Toy-Store-E-commerce-database
This project focuses on analyzing Maven Fuzzy Factory, an e-commerce business that sells teddy bears online. Using Power BI and DAX (Data Analysis Expressions), I will transform raw business data into interactive dashboards that provide insights into website traffic, customer purchasing behavior, marketing performance, sales revenue, and product returns.

The project involves creating DAX measures to calculate key performance indicators (KPIs), including total website sessions, total orders, session-to-order conversion rate, total revenue, average revenue per order, and revenue per session. These metrics will help evaluate business performance, identify successful marketing channels, and uncover opportunities to improve website conversions and revenue generation.


## Project Objectives
Analyze trends in website sessions and order volume.

Calculate and monitor the session-to-order conversion rate.

Evaluate marketing channel performance and identify the most effective sources of traffic.

Measure revenue per order and revenue per website session.

Analyze product returns and their potential impact on business performance.

Build an interactive Power BI dashboard to support data-driven decision-making.

## Tools and Techniques
Power BI: Data modeling, interactive dashboards, and visualizations.

DAX: Calculated measures and KPI development.

Power Query: Data cleaning, transformation, and preparation.

## DATA SOURCE
MAVEN ANALYTICS

## VISUALISATIONS
<img width="880" height="561" alt="2" src="https://github.com/user-attachments/assets/c8da640a-ee41-4325-bd96-10328cf9eb5c" />

<img width="923" height="568" alt="Capture" src="https://github.com/user-attachments/assets/989cb256-5b1b-444a-a638-a7514f5b77a6" />


## DAXs

```
month_year = FORMAT(website_sessions[created_at],"MMM YYYY")
```
```
MONTH_YEAR_SORT = YEAR(website_sessions[created_at])*100 + MONTH(website_sessions[created_at])
```

```
Total website session = DISTINCTCOUNT(website_sessions[website_session_id])
```
```
order unique website session id = DISTINCTCOUNT(orders[website_session_id])
```
```
Revenue per order = DIVIDE([Revenue],[Total Orders],0)
```

```
Revenue per session = DIVIDE([Total Revenue],[Total website session],0)
```
```
session-to-order conversion rate = DIVIDE([Total Orders],[Total website session],0)
```
```
Total Cost = SUM(orders[cogs_usd])
```
```
Total Orders = DISTINCTCOUNT(orders[order_id])
```
```
Total Revenue = SUMX(orders,orders[items_purchased] * orders[price_usd])
```
```
Revenue = SUM(orders[price_usd])
```

## Key Findings
### Strong order volume

The business recorded approximately 32,000 orders, indicating substantial purchasing activity across the period analyzed.

### Significant revenue generation

Total revenue reached approximately $1.94 million. However, revenue alone does not reveal profitability because the dashboard also reports costs and refunds.

### Substantial operating costs

The recorded total cost is approximately $722,370. Comparing costs against revenue and other expenses can help management evaluate financial performance.


### Product returns require attention

The dashboard records 1,731 refunded items and approximately $85,340 in refunded amounts. Product quality, customer expectations, and order fulfilment should be investigated.

### Dominant Marketing Channel

Google Search drives the vast majority of the company's revenue, accounting for $1.43M (73.67%). Direct/Unknown traffic is the second-largest contributor at $0.31M (16.17%), followed by Bing Search at $0.17M (9.01%). Social Media brings in a negligible amount of revenue.

### Revenue per Order Trend

The average revenue per order remained stable at around $50 from March 2012 until early 2014. Around February 2014, there was a sharp, positive jump to over $60, and it has sustained that higher level through March 2015.

### Revenue per Session Trend

Unlike the flat-then-jump behavior of revenue per order, revenue per session shows a consistent, steady upward growth trajectory over the entire three-year period. It started at just above $1 in March 2012 and grew to over $5 by March 2015.

## Recommendations

1. Improve website conversion rates

Monitor session-to-order conversion by month and marketing channel. Investigate periods when website sessions increase without a corresponding rise in orders, and improve product pages, checkout speed, and the purchasing experience.

2. Invest in effective marketing channels

Compare sessions, orders, conversion rates, and revenue by marketing source. Allocate more budget to channels that generate valuable orders rather than focusing on traffic volume alone.

3. Reduce product refunds

Identify products with the highest refund rates. Review product descriptions, quality control, packaging, delivery accuracy, and customer feedback to reduce avoidable returns.


4. Maximize and Diversify Digital Marketing

• Protect the Core: Continue allocating primary budget and optimization efforts to Google Search, as it is the clear financial engine of the business.
• Optimize Bing: Review why Bing Search is underperforming compared to Google. Adjust keyword bidding or ad copy to capture a larger share of search traffic.
• Revamp Social Media Strategy: Social Media is currently underutilized. Test targeted paid social campaigns (e.g., video showcases of the fuzzy toys) or influencer partnerships to transform this into a viable revenue stream.

5. Capitalize on Increased Order Value

• Analyze the 2014 Lift: Investigate what caused the sharp increase in revenue per order in early 2014 (e.g., introduction of higher-priced products, a change in shipping pricing, or successful cross-selling bundles). Replicate this strategy if possible.
• Implement Upselling Strategies: To push the average order value even higher, introduce product bundles, gift wrapping options, or "frequently bought together" suggestions at checkout.

6. Maintain Website Conversion Momentum

• Keep Optimizing the Funnel: The steady rise in revenue per session indicates that website conversion rates, user experience, or product relevance have drastically improved over time. Continue running A/B tests on landing pages and the checkout flow to maintain this strong upward momentum.
