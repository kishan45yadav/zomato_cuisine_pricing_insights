# Zomato Restaurant Analysis — Cuisine, Pricing & Rating Insights

An end-to-end data analysis project exploring 50,000+ restaurants from Zomato's Bangalore dataset to uncover patterns in cuisine popularity, city-wise pricing, and the relationship between cost and customer ratings.

## Key Findings

- **North Indian is the most popular cuisine** across Bangalore, followed by Chinese and South Indian — reflecting strong demand for familiar, hearty flavors.
- Premium areas like **Church Street, Brigade Road, and Lavelle Road** show significantly higher average costs, showing clear price segmentation by location.
- Higher prices don't guarantee higher ratings — cost and rating show only a **weak correlation**, suggesting quality matters more than price.
- **Fine Dining and Microbrewery** formats outperform Quick Bites in ratings, while restaurants offering table booking are priced at a premium.

## Dataset

| | |
|---|---|
| Source | [Kaggle – Zomato Bangalore Restaurants](https://www.kaggle.com/) |
| Original size | 51,717 rows × 17 columns |
| Key columns used | `name`, `online_order`, `book_table`, `rate`, `votes`, `location`, `rest_type`, `cuisines`, `approx_cost(for two people)`, `listed_in(type)`, `listed_in(city)` |
| Final unique cuisines | 105 (after cleaning combo-strings) |

## Workflow

Data was cleaned in **Python (Pandas)**:
- Removed non-essential columns (`url`, `address`, `phone`, `menu_item`, `reviews_list`, `dish_liked`) and duplicate rows
- Cleaned the `rate` column (e.g. `"4.1/5"` → `4.1`) and handled `NEW` / `-` values
- Cleaned `approx_cost(for two people)` by removing commas and converting to numeric
- Converted `online_order` and `book_table` from Yes/No to 1/0
- Dropped rows missing critical fields (`rate`, `cost`, `cuisines`, `location`)
- Standardized location/city text formatting
- Split the multi-value `cuisines` column into individual rows and trimmed extra whitespace, to get an accurate count of unique cuisines and correct popularity rankings

The cleaned dataset was modeled in **Power BI**, where a two-page interactive dashboard was built with DAX measures, cross-filtering slicers, and visuals covering cuisine trends, city pricing, and deeper restaurant-type comparisons.

## Dashboard

**Page 1 — Core Analysis:** Cuisine popularity, average cost by city, and rating vs cost scatter, with KPI cards for total restaurants, total cuisines, average rating, and average cost.

**Page 2 — Deeper Restaurant Trends:** Restaurant-type performance, listed-in-type cost comparison, and the impact of online ordering and table booking on rating/cost.

*(See `/screenshots` for dashboard images and `Zomato_Analysis_Report.pdf` for the full write-up.)*

## Tech Stack

`Python (Pandas)` · `Power BI` · `DAX`

## About

This project demonstrates a complete analytics workflow — from raw, messy real-world data to a polished, interactive business dashboard — answering practical questions a food-delivery platform or restaurant chain would actually care about: what to serve, where to price it, and what drives customer satisfaction.

**Author:** Kishan Yadav
Portfolio: [kishan45yadav.github.io](https://kishan45yadav.github.io)
GitHub: [github.com/kishan45yadav](https://github.com/kishan45yadav)

