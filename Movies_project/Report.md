# Movie Data Analysis Project Report

## 1. Objective
- Perform exploratory data analysis (EDA) on a movie dataset.
- Understand trends in movie popularity, ratings, and vote counts.
- Categorize movies based on their vote averages.

## 2. Dataset Overview
- Source: `moviedb.csv` (imported via Google Drive)
- Initial records: 17,620 movies
- Final records after cleaning: 9,041 movies

## 3. Data Cleaning & Preparation
- Dropped irrelevant columns: `Unnamed: 0`, `poster_path`, `id`
- Removed 8,579 duplicate rows
- Converted `release_date` from string to year (integer format)
- Created quartile-based categories for `vote_average`: `not_popular`, `below_avg`, `average`, `popular`
- Verified and handled minimal missing values (only 1 missing `overview`)

## 4. Descriptive Statistics

| Metric            | Popularity | Vote Average | Vote Count |
|-------------------|------------|---------------|-------------|
| Count             | 9041       | 9041          | 9041        |
| Mean              | 28.54      | 6.65          | 2000.37     |
| Standard Deviation| 45.35      | 0.79          | 3154.56     |
| Minimum           | 0.60       | 3.70          | 300         |
| 25th Percentile   | 14.53      | 6.11          | 469         |
| Median            | 19.86      | 6.66          | 847         |
| 75th Percentile   | 29.77      | 7.22          | 1982        |
| Maximum           | 1857.80    | 8.71          | 34,961      |

**Key Observations:**
- Popularity and vote count are right-skewed; a few movies have extremely high values.
- Vote average is more normally distributed with most movies rated between 6 and 7.
- Suggests a possible positive correlation between popularity and vote count.

## 5. Categorical Analysis
- The `vote_average` column was categorized into four quartile-based groups.
- Counts for each group:
  - `not_popular`: 2261
  - `below_avg`: 2260
  - `average`: 2264
  - `popular`: 2255

## 6. Key Findings
- **Most Popular Movie:**
  - Title: *Rebel Moon - Part One: A Child of Fire* (2023)
  - Popularity Score: 1857.80

- **Least Popular Movies (Popularity = 0.6):**
  - *Grave of the Fireflies* (1988)
  - *Hotarubi no Mori e* (2011)
  - *Odds and Evens* (1978)
  - *Tracks* (2013)
  - *G.B.F.* (2014)
  - *Serial Teachers* (2013)

- Some least popular movies had relatively high vote counts, suggesting niche or cult followings.

## 7. Popularity Trends Over Time
- A line plot of movie popularity by release year shows:
  - Increasing trend in popularity for recent movies (especially after 2000).
  - Older films may retain critical acclaim but have lower popularity scores.

## 8. Tools and Technologies Used
- Programming Language: Python
- Libraries: Pandas, Matplotlib, Seaborn
- Platform: Google Colab

## 9. Conclusion
- The dataset was successfully cleaned and analyzed.
- Popularity and engagement vary widely, with recent films dominating popularity metrics.
- The vote average distribution suggests a tendency toward moderate to high ratings.
- Future work could involve:
  - Adding genre-based analysis
  - Incorporating text mining on overviews
  - Building a model to predict popularity or rating based on features
