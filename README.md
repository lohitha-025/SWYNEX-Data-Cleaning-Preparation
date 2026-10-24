# SWYNEX Data Cleaning & Preparation

## Project Overview
This project is Task 1 of my SWYNEX Technologies internship. I cleaned a messy public dataset using Python (pandas) in Jupyter Notebook.

## Dataset
- **Name:** Dirty Cafe Sales Dataset
- **Source:** https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training
- **Size:** 10,000 rows, 8 columns (cafe transactions: item, quantity, price, total, payment method, location, date)

## Files in this Repository
| File | Description |
|------|-------------|
| `raw_data.csv` | Original messy dataset |
| `cleaned_data.csv` | Final cleaned dataset |
| `data_cleaning.ipynb` | Jupyter Notebook with all cleaning code |

## Problems Found
1. **Missing values:** Item (333), Quantity (138), Price Per Unit (179), Total Spent (173), Payment Method (2,579), Location (3,265), Transaction Date (159)
2. **Incorrect values:** Many cells contained the placeholder text "ERROR" or "UNKNOWN" in every column (for example Item: 292 ERROR and 344 UNKNOWN)
3. **Incorrect data types:** All 8 columns were loaded as text, including Quantity, Price Per Unit, Total Spent, and Transaction Date
4. **Duplicate records:** 0 duplicates found
5. **Inconsistent values:** Missing entries were written in different ways (blank, "ERROR", "UNKNOWN")

## Cleaning Steps
1. Replaced "ERROR" and "UNKNOWN" with proper missing values (NaN)
2. Converted Quantity to integer, Price Per Unit and Total Spent to decimal numbers, and Transaction Date to date format
3. Recovered missing numbers using the formula `Total Spent = Quantity x Price Per Unit`
4. Dropped 58 rows where the numbers could not be recovered
5. Replaced missing Item, Payment Method, and Location with "Unknown"
6. Left missing Transaction Dates blank, because a date cannot be guessed reliably
7. Checked for duplicates (none found)

## Results
| | Before | After |
|---|---|---|
| Rows | 10,000 | 9,942 |
| Missing in Quantity, Price, Total | 490 | 0 |
| Missing in Item, Payment, Location | 6,177 | 0 |
| "ERROR" / "UNKNOWN" placeholders | Present in all columns | Removed |
| Data types | All text | Numbers and dates |
| Missing Transaction Date | 159 | 457 |

Note: Transaction Date has more blanks after cleaning because the "ERROR" and "UNKNOWN" dates were converted to blanks.

## Tools Used
Python, pandas, NumPy, Jupyter Notebook

## How to Run
1. Download `raw_data.csv` and `data_cleaning.ipynb` into one folder
2. Open the notebook in Jupyter
3. Run all cells
