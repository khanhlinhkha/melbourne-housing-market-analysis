# Melbourne Real Estate Market Analysis Dashboard

## Introduction

This project presents an interactive **Power BI dashboard** analyzing the **Melbourne real estate market**. It was developed as a personal project to explore how data visualization can support real estate investment decision-making, especially for stakeholders looking for clear and actionable insights rather than raw market data alone.

The dashboard is designed to help users understand the size and evolution of the market, identify more attractive times to buy, compare locations across Melbourne, and evaluate the most common property profiles by type, size, and amenities. The analysis is especially relevant for organizations exploring a **coliving-oriented investment strategy**, where location, affordability, and property characteristics matter together.

You can view the interactive Power BI report here:

[Open the Power BI Dashboard](https://app.powerbi.com/view?r=eyJrIjoiMzQ4MTU2YTMtYTdjYy00YzdlLWE2MjctNTJjYjdhNWZkYmIxIiwidCI6IjYyZTEzYjg0LTE5NjAtNDU2Mi04YzdmLTcyNDcyOTUxZGE4ZiIsImMiOjl9)

---

## Focus and Audience

The dashboard is built for **property investors** and **investment managers** of a real estate company who are exploring opportunities in the Melbourne housing market. They need a quick, interactive way to understand overall market conditions, spot attractive entry points, and identify the locations and property types that best match the company’s coliving strategy.

The main questions this dashboard aims to answer are:

- How big is the market and how has it evolved over time?
- When is it more attractive to buy, in terms of seasonality and timing?
- Where are the most active or promising regions and suburbs?
- What types of properties (house, unit, townhouse, size, amenities) are most common and at what price levels?

---

## Charts and Layout

To answer these questions, the dashboard is organized into four pages: **Overview**, **Timing the Market**, **Location Insights**, and **Property Profile**.

### 1. Overview
The **Overview** page gives a high-level snapshot of the market through: total sales, overall median price, sales trend, price distribution, region activity and property type mix. This allows stakeholders to quickly understand the scale and shape of the dataset.

### 2. Timing the Market
The **Timing the Market** page focuses on when it may be more attractive to buy. a combo chart of sales and median price over time, a month-level view aggregating across years, and weekday analysis to highlight periods with high activity or relatively lower prices.

### 3. Location Insights
The **Location Insights** page answers where to invest: a map of sales by region, a scatter of price and sales versus distance to the CBD, a Top 10 suburbs chart, and a regional summary table. These show which areas are most active, how far they are from the CBD, and how expensive they are.

### 4. Property Profile
The **Property Profile** page focuses on what to buy: a pie chart of sales by property type, a scatter plot of price and sales by building area and type, and a decomposition tree breaking median price down by type, rooms, car spots and building area. This lets investors compare typical profiles and trade-offs between size, amenities and price.

### Layout Logic
The layout follows a consistent pattern: each visual is explicitly linked to a guiding question, shown as a subtitle, so stakeholders can immediately see what insight it provides. The left pane holds slicers so users can filter by time period, location, property type, price range and distance to CBD.

---

## Assumptions

The dashboard is based on the following assumptions:

- The analysis focuses on the available time period in the dataset, from **January 2016 to September 2017**, and assumes this period is representative enough to support useful insight generation and investment-oriented interpretation.
- Each row in the dataset is treated as one completed property sale, so counting rows approximates total sales. It is therefore assumed that all listed properties in the dataset have been sold.
- **Median price** is used as one of the main price metrics instead of average price because it is more robust to extreme values.
- For property characteristics, the dashboard focuses on **property type, number of rooms, car spots, and building area** as the key amenities, in order to keep the visual analysis focused and interpretable.

---

## Data Cleaning and Transformations

Several cleaning and transformation steps were applied in Power BI:

- The original **Date** column contained inconsistent formats, including both `mm/dd/yyyy` and `dd/mm/yyyy`. It was standardized into a proper Date type during import into Power BI.
- Outliers were checked in several fields, such as **Price** and **BuildingArea**. These values were not removed, because very expensive or very large properties can still be meaningful in the real estate market. Instead, values were grouped into bins so that extreme cases appear in the highest category rather than distorting the rest of the visuals.
- For fields such as **BuildingArea** that contain null or `0` values, the rows were not dropped. These properties may still be useful for other analysis dimensions such as price, rooms, and region, so they were grouped into a separate **"Unknown / 0"** category.
- **BuildingArea** was binned into size ranges, such as `0–100 m²`, `100–150 m²`, and so on, to make the relationship between size, price, and sales easier to interpret in charts.
- A few calculated measures, such as **Total Sales** and **Median Price**, were created directly in Power BI. Other small transformations, such as **property type grouping** and **big-region vs. region categories**, were also created while building the visuals. These transformations were applied only where needed to answer specific questions in the dashboard.

---

## Overall Insights

### 1. How big is the market and how has it evolved over time?

The dataset covers around **13.5k property sales** between **January 2016 and September 2017**. Sales increased from 2016 to 2017, with about **14% more sales**, while the overall median price remained relatively stable at around **$900k**, with only a small uptick.

This suggests a **growing and active market** with modest price growth and increasing transaction volume.

### 2. When is it more attractive to buy?

Sales activity rises in **autumn and spring** and is lower in the early part of the year and in mid-winter. Median prices are less volatile than sales volumes, but some months, such as **July**, show relatively lower prices.

Most transactions occur on **Saturdays**, while weekdays, especially **Monday**, have fewer sales and sometimes slightly lower median prices.

Overall, this suggests that lower-activity periods may offer slightly more attractive buying conditions, while peak periods reflect stronger market demand.

### 3. Where are the most active or promising regions and suburbs?

The market is concentrated in **Metropolitan Melbourne**.

Key findings include:

- **Southern, Northern, and Western Metropolitan** regions show the highest sales volumes.
- **Southern Metropolitan** also has the highest median prices while remaining relatively close to the CBD.
- **Northern and Western Metropolitan** combine strong activity with relatively lower median prices and short to moderate distance from the CBD, making them attractive for more affordable investments.
- **Eastern, Northern, and Western Victoria** show very low sales volume, lower prices, and much greater distance from the CBD.
- Top-selling suburbs include **Reservoir, Richmond, Bentleigh East**, and others.

Overall, the **Metropolitan regions** appear to be the main investment focus areas. In particular, **Northern and Western Metropolitan** stand out for relative affordability, while **Southern and Eastern Metropolitan** represent higher-priced market segments.

### 4. What types of properties are most common and at what price levels?

- **Houses** are the dominant property type in the market.
- **Units/duplexes** also represent a significant and more affordable segment.
- **Townhouses** sit between these two in both size and price.

Price tends to increase with size and amenities:
- larger building area is associated with higher median price
- more rooms increase median price
- more car spots increase median price

Most sales occur in **small to medium building sizes**, which suggests that **medium-sized houses or townhouses** may offer a useful balance between cost, space, and market availability.
