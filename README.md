
#### ETL Midterm Project - Yar_125
## Project Overview
This project implements an ETL (Extract, Transform, Load) pipeline for the DSA 2040A US 2025 Mid Semester Exam. It processes two datasets (`raw_data.csv` and `incremental_data.csv`), applies meaningful transformations, loads the results into SQLite databases, and includes a visualization for analysis. The pipeline is organized into three Python scripts and follows the specified folder structure.

## ETL Phases
1. **Extract (`etl_extract.py`)**
   - Loads `raw_data.csv` (100 rows) and `incremental_data.csv` (10 rows).
   - Displays head and info for both datasets.
   - Observes missing values, duplicates, and suspicious columns (e.g., inconsistent data types).
   - Saves raw copies to `data/` directory.

2. **Transform (`etl_transform.py`)**
   - Applies four transformations to both datasets:
     - **Cleaning**: Imputes missing `customer_name` and `region` with 'Unknown', `quantity` and `unit_price` with median, and `order_date` with default dates.
     - **Cleaning**: Removes duplicate rows (1 duplicate found in `raw_data.csv`).
     - **Enrichment**: Adds `total_price` column (`quantity * unit_price`).
     - **Structural**: Converts `order_date` to datetime and extracts `order_year`.
   - Saves transformed data as `transformed_full.csv` and `transformed_incremental.csv` in `data/transformed/`.
   - Includes a bar chart of total sales by product for bonus marks, saved as `total_sales_by_product.png`.

3. **Load (`etl_load.py`)**
   - Loads transformed data into SQLite databases (`full_data.db` and `incremental_data.db`) in `loaded/`.
   - Verifies loading with SQL queries (`SELECT * FROM table LIMIT 5`).

## Tools Used
- **Python**: Core programming language.
- **Pandas**: Data manipulation and analysis.
- **SQLite3**: Database for loading transformed data.
- **Matplotlib**: Visualization for bonus marks.

## How to Run the Project
1. Clone the repository: `git clone https://github.com/<your-username>/DSA2040A_ETL_Midterm_Yar_125.git`
2. Ensure Python 3.8+ and required libraries are installed:
   ```bash
   pip install pandas sqlite3 matplotlib

SREENSHOT
![image](https://github.com/user-attachments/assets/88593f86-1cdb-4cf4-955f-434bd16b8ce8)
The chart titled "Total Sales by Product" appears to be a list of sales values ranging from $0 to $424. However, the provided content does not include a visual representation (e.g., bar chart, line graph, or pie chart) or any product labels, making it difficult to interpret the data fully.

Key Observations:
Sales Range: The sales values span from $0 to $424, with some values repeated (e.g., $424 is listed multiple times).

Data Format: The data is presented as a text list rather than a visual chart, which limits insights into trends, comparisons, or distributions.

Potential Issues:

The list includes many repeated values (e.g., $424) and skips some numbers (e.g., $303 is missing).

No product names or categories are associated with the sales figures.

