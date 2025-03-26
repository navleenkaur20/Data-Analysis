
# Gold Rate Analysis - Comprehensive Project Report

## Project Objective

The Gold Rate Analysis project aims to explore and analyze historical data on daily gold prices recorded in various currencies. This analysis helps in understanding trends, identifying patterns over time, and comparing the price movements across different currencies. The project uses Python libraries such as Pandas and NumPy.

---

## Dataset Description

The dataset includes daily gold rates across multiple currencies. Each row in the dataset represents the gold rate on a specific date.

- Columns include:
  - `Date`: The date of the recorded gold rate
  - `USD`, `CNY`, and other currency columns representing gold rates

---

## Step 1: Load the Dataset

- Loaded a CSV file into a Pandas DataFrame named `gold`
- Ensured the dataset was ready for further analysis

---

## Step 2: Initial Exploration

- Inspected data types using `.dtypes`
- Previewed the first 10 rows using `.head(10)`
- Verified column structure and identified `Date` as an object (string) that needs conversion

---

## Step 3: Date Conversion and Filtering

- Converted the `Date` column to `datetime64` format
- Filtered and formatted dates from index 100 to 150 using US format (MM/DD/YYYY)

```python
gold['Date'] = pd.to_datetime(gold['Date'])
us_format_dates = gold['Date'].iloc[100:151].dt.strftime('%m/%d/%Y')
```

- Enabled future date-based filtering and resampling

---

## Step 4: USD Rate Analysis for 2020 and 2021

- Filtered data to include only years 2020 and 2021
- Created a NumPy array `gold_usd_2020and2021` from the `USD` column

```python
filtered = gold[(gold['Date'].dt.year >= 2020) & (gold['Date'].dt.year <= 2021)]
gold_usd_2020and2021 = filtered['USD'].to_numpy()
```

- Tasks performed:
  - Identified the median gold rate in USD
  - Sorted the array in descending order
  - Calculated the price range using NumPy functions

```python
median = np.median(gold_usd_2020and2021)
descending = np.sort(gold_usd_2020and2021)[::-1]
price_range = np.ptp(gold_usd_2020and2021)
```

---

## Step 5: CNY Rate Analysis

- Focused on the `CNY` column
- Likely performed similar operations:
  - Filtering data by date
  - Computing statistics such as mean, median, range
  - Possibly visualizing trends or comparing with USD

---

## Tools and Techniques Used

- Pandas:
  - Data loading and DataFrame manipulation
  - Date parsing and filtering
- NumPy:
  - Efficient statistical operations (e.g., median, range)
- Data analysis techniques:
  - Time series filtering
  - Descriptive statistics
  - NumPy array transformations

---

## Summary of Insights

- Gold prices showed variation across years and currencies
- Date conversion was essential for time-based analysis
- Median and range values provided insight into price centrality and volatility
- NumPy simplified array-based numerical computations

---

## Conclusion

This project demonstrates effective data handling and analysis techniques using Python. The workflow included:

- Preparing and transforming time series data
- Performing year-specific filtering
- Applying statistical analysis
- Extracting key insights about price trends

The methods used in this analysis provide a strong foundation for more advanced financial modeling and forecasting tasks.
