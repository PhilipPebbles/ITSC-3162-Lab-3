# ITSC 3162 Lab 3: Google Play Store Data Wrangling

[![Open in Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PhilipPebbles/ITSC-3162-Lab-3/blob/main/lab_03_exercise.ipynb)

This repository contains a structured coursework exercise for **ITSC 3162: Introduction to Data Mining**. It works through a messy Google Play Store dataset to demonstrate practical data inspection, cleaning, validation, filtering, and aggregation with pandas.

## Dataset

The source dataset contains **10,841 rows and 13 columns** describing Google Play Store applications. Several numeric-looking fields are stored as strings and contain formatting characters such as commas, plus signs, currency symbols, and units.

The notebook loads the public dataset from its [GitHub mirror](https://raw.githubusercontent.com/sumitgirwal/google-play-store-data-analysis/master/googleplaystore.csv).

## What the Notebook Demonstrates

- Profiling data types, descriptive statistics, and missing values
- Quantifying missingness by count and percentage
- Detecting fully duplicated rows and repeated application names
- Converting formatted install counts into integers
- Parsing dollar-prefixed prices into numeric values
- Filtering highly rated, widely installed applications
- Creating an educational `Price × Installs` revenue proxy
- Building category-level summaries with `groupby` and aggregation

## Corrected Results

- Rows with a rating: **9,367**
- Fully duplicated rows identified: **474**
- Paid application records after correct price parsing: **613**
- Highly rated apps with at least one million installs: **1,234**

The revenue calculation is a simplified classroom proxy based on listed price and install count. It does not account for fees, discounts, refunds, regional pricing, repeat purchases, or duplicate application listings, so it should not be interpreted as actual revenue.

## Correction Note

The original submitted notebook converted the `Price` column without removing its leading `$` characters. That coerced paid prices to missing values and incorrectly reported zero paid apps. The notebook now strips the currency symbol before numeric conversion, avoids chained-assignment warnings, and has been rerun from top to bottom with saved outputs.

## Technologies

- Python
- pandas
- NumPy
- Matplotlib
- Jupyter / Google Colab

## Repository Contents

- [`lab_03_exercise.ipynb`](lab_03_exercise.ipynb) — corrected, fully executed notebook

## Run the Notebook

Open the notebook with the Colab badge above, or run it locally with Jupyter after installing:

```bash
pip install pandas numpy matplotlib jupyter
```

Internet access is required to load the public CSV from its source URL.

## Context

This is a completed class laboratory exercise. The cleaning workflow follows the assignment's supplied structure and is not presented as independently designed research.

## Author

**Philip Pebbles**
[GitHub](https://github.com/PhilipPebbles)
