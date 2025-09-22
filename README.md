Task 1: Data Cleaning and Preprocessing
Project Objective
The primary objective of this task was to clean and prepare a raw dataset (Netflix Movies and TV Shows) which contained common issues such as null values, potential duplicates, and inconsistent data formats. The goal was to transform this raw data into a clean, structured, and reliable dataset suitable for analysis and visualization.




Tools Used: Python with the Pandas and NumPy libraries.

Detailed Summary of Changes
The following is a detailed, step-by-step summary of the actions performed to clean the dataset.

1.
Handling Missing Values


A crucial step in data preprocessing is addressing missing data, as it can lead to errors or biased analysis. Different strategies were applied based on the nature of each column.

Categorical Data (director, cast, country):

What: Null values in these columns were replaced with the string 'Unknown'.

Why: These columns contain important contextual information. Deleting the rows would result in significant data loss. By filling the nulls with 'Unknown', we preserve the records while explicitly acknowledging that the information was not available.

Date Data (date_added):

What: The few missing values in this column were filled using a forward-fill (ffill) followed by a backward-fill (bfill).

Why: For chronological data, it's a reasonable assumption that a missing entry date is close to the entries before or after it. This method ensures the column is complete without introducing arbitrary dates.

Numerical/Categorical Data (rating, duration):

What: Missing values were filled with the mode (the most frequently occurring value) of their respective columns. For duration, the mode was calculated separately for 'Movies' and 'TV Shows' to ensure logical imputation.

Why: Imputing with the mode is a standard technique when the number of missing values is small. It fills the gaps while having a minimal impact on the column's statistical distribution.

2.
Removing Duplicate Rows



What: The entire dataset was checked for duplicate rows, and any found were removed using the .drop_duplicates() method.

Why: Duplicate records can skew analytical results, leading to inflated counts and incorrect conclusions. Ensuring every row is unique is fundamental for data integrity. (Note: No duplicates were found in this dataset, but this check remains a critical best practice).

3.
Standardizing Text Values


Inconsistent text formatting can cause a single category to be treated as multiple different ones.

What: The country column was converted to lowercase, and the rating column was converted to uppercase. Leading/trailing whitespaces were also removed.

Why: This ensures that values like "India", "india", and " india " are all treated as a single entity, allowing for accurate grouping and analysis.

4.
Converting Data Formats



The data type of a column dictates what operations can be performed on it.


What: The date_added column was converted from a generic 'object' (string) type to a datetime type.


Why: A proper datetime format is essential for any time-based analysis, such as plotting trends over time, sorting by date, or calculating time differences. These operations are not possible when dates are stored as plain text.

5.
Renaming Column Headers



What: Columns were renamed to be more intuitive and uniform. Specifically, 

listed_in was renamed to category and release_year to release_yr.

Why: Clean, descriptive column names improve the readability of the dataset, making the code and subsequent analyses easier to understand for anyone working with the data.
