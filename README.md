# coffee-shop-analysis

This repository documents the Exploratory Data Analysis and initial data quality checks performed on a coffee shop transaction dataset.

## Dataset

The dataset, sourced from Kaggle, contains transactional records from a fictional coffee shop with three branches. Attributes include transaction_date, transaction_time, transaction_qty, store_location, product_id, unit_price, product_category, and product_type.

## Preprocessing Steps Summary

The following key preprocessing steps were performed using primarily Pandas (potentially supplemented by analysis in Excel):

1.  **Data Loading & Initial Overview:** Loaded the CSV dataset and performed initial checks.
2.  **Data Completeness Assessment:** Checked for missing values using .isnull().sum(). Confirmed the dataset was complete with no missing entries.
3.  **Data Consistency Checks:**
    * Validated transaction_date (no future dates found).
    * Checked transaction_qty for non-positive values or excessively large orders (none found based on defined thresholds).
    * Examined unit_price for non-positive values (none found) and confirmed that high prices were associated with legitimate premium categories (e.g., 'Coffee beans', 'Branded') rather than errors.
4.  **Data Consistency Checks:**
    * Confirmed consistent mapping between store_id and store_location.
    * Verified transaction_id uniqueness per row.
    * Identified a key issue: inconsistent unit_price values associated with the same product_id across different transactions, highlighting a need for price standardization before aggregation.

## Outcome

The EDA provided a clear understanding of the dataset, confirmed its completeness, and pinpointed the inconsistent pricing issue as a critical point for cleaning. 
