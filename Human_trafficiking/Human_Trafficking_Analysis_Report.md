
# Human Trafficking Analysis - Project Report

## Project Objective
- Analyze a dataset related to human trafficking offenses.
- Clean and preprocess the data to make it suitable for analysis.
- Identify patterns, trends, and potential areas for further investigation.

## Task 1: Initial Data Exploration
- Used `value_counts()` to understand the types of values in both categorical and continuous data columns.

## Task 2: Column Reduction and Cleaning
### Removed Unwanted Columns:
- **OTHER_COUNT**: This column contained only missing values, making it redundant.
- **STATE_ABBR**: Removed due to duplication of information already available in `STATE_NAME`.
- **OFFENSE_SUBCAT_NAME**: Removed since `OFFENSE_NAME` provided sufficient categorization.
- **DIVISION_NAME**: Removed as `REGION_NAME` was sufficient for geographical categorization.
- **ORI**: Contained unique IDs not useful for analysis.

## Task 3: Handling Missing Values
- Identified columns with null values.
- Replaced missing values in categorical columns using the mode (most frequent value).
- Ensured data consistency for analysis.

## Task 4: Feature Engineering and Cleaning
- Possibly included conversion of date/time columns or other transformations.
- Ensured categorical columns were clean and standardized.

## Task 5: Data Visualization (if applicable)
- Created visualizations to analyze:
  - Distribution of offenses across states or regions.
  - Trends over time if a temporal column (e.g., year) was available.
  - Relationships between offense types and victim demographics.

## Task 6: Insights and Interpretations
- Identified major regions or states with high trafficking cases.
- Highlighted the most common offense types.
- Possibly identified correlations between categorical variables (e.g., gender, age group, offense type).

## Conclusion
- The dataset was successfully cleaned by removing redundant columns and handling missing values.
- Categorical features were analyzed to understand the underlying patterns.
- The analysis provides a solid foundation for further modeling or policy recommendations related to human trafficking.


