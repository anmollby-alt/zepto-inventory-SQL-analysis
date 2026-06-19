# Zepto Inventory - SQL Data Analysis

A SQL project where I explored and analyzed Zepto's product inventory data using PostgreSQL. The dataset has around 3,700+ SKUs across 14 categories — things like pricing, discounts, stock availability, and inventory weight.

I did this project to get hands-on with real messy e-commerce data and practice writing business-driven queries from scratch.

---

## Dataset

Sourced from Kaggle — originally scraped from Zepto's live product listings.

Each row is a unique SKU. Same product can appear multiple times with different weights, pack sizes, or discount slabs (which is how real catalog data works).

**Columns:**
- `sku_id` — unique ID (primary key)
- `name` — product name
- `category` — e.g. Fruits & Vegetables, Snacks, Beverages
- `mrp` — max retail price (was in paise, converted to ₹)
- `discountPercent` — discount on MRP
- `discountedSellingPrice` — final price after discount
- `availableQuantity` — units in stock
- `weightInGms` — product weight
- `outOfStock` — true/false
- `quantity` — units per pack

---

## What I did

### 1. Table Setup & Data Import
Created the table in PostgreSQL with proper data types and loaded the CSV via pgAdmin.

### 2. Data Exploration
- Total row count
- Sample data check
- Null value scan across all columns
- Distinct categories
- In-stock vs out-of-stock split
- Products appearing multiple times (multiple SKUs)

### 3. Data Cleaning
- Removed rows where MRP or selling price was 0
- Converted prices from paise → rupees

### 4. Business Queries
- Top 10 products by discount %
- High MRP products currently out of stock
- Estimated revenue per category
- Expensive products (MRP > ₹500) with low discounts (< 10%)
- Top 5 categories by average discount
- Price per gram — value for money analysis
- Weight segmentation: Low / Medium / Bulk
- Total inventory weight per category

---

## Tools Used
- PostgreSQL
- pgAdmin 4

---

## Files
- `zepto_analysis.sql` — full SQL script (exploration + cleaning + analysis)
- `zeptodataset.csv` — raw dataset

---

## How to run
1. Open pgAdmin and create a new database
2. Run `zepto_analysis.sql` to create the table and load queries
3. Import `zeptodataset.csv` using pgAdmin's import tool (make sure encoding is UTF-8)
