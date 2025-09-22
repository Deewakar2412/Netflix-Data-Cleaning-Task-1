🧹 Task 1: Netflix Dataset - Data Cleaning & Preprocessing
🎯 Project Objective
The primary objective of this task was to clean and prepare the raw Netflix Movies and TV Shows dataset. The goal was to resolve common data issues like null values, potential duplicates, and inconsistent formats, ultimately transforming it into a structured and reliable dataset ready for analysis.

🛠️ Tools & Libraries Used
Language: Python

Libraries: pandas, numpy

Environment: Google Colab

✨ Detailed Summary of Changes
Here is a step-by-step summary of the actions performed to clean the dataset.

1. Handling Missing Values
A crucial step to prevent errors or biased analysis. Different strategies were used for different columns.

director, cast, country:

What: Null values were replaced with the string 'Unknown'.

Why: This preserves valuable records that would otherwise be deleted, while clearly marking that the information was not available.

date_added:

What: Missing values were filled using forward-fill (ffill) followed by backward-fill (bfill).

Why: This is a logical approach for chronological data, assuming a missing date is likely close to the entries immediately before or after it.

rating, duration:

What: Missing values were filled with the mode (the most frequent value). For duration, this was done separately for 'Movie' and 'TV Show' types.

Why: Using the mode is a safe way to fill a small number of gaps without significantly affecting the column's overall distribution.

2. Removing Duplicate Rows
What: The dataset was scanned for duplicate entries using .drop_duplicates().

Why: This is a fundamental step for data integrity. Duplicate records can skew results and lead to inaccurate conclusions.

3. Standardizing Text Values
What: The country column was converted to lowercase, and the rating column to uppercase. Leading/trailing whitespaces were also removed.

Why: This ensures consistency, preventing values like "India" and "india" from being treated as separate categories during analysis.

4. Converting Data Formats
What: The date_added column's data type was converted from an object (string) to a proper datetime format.

Why: A datetime format is essential for any time-based analysis, such as plotting trends over time or sorting by date, which is impossible with plain text.

5. Renaming Column Headers
What: Columns were renamed for better clarity: listed_in was changed to category, and release_year became release_yr.

Why: Clean and intuitive column names make the dataset easier to read, understand, and work with.

After completing these steps, the final, cleaned dataset was saved to a new file, netflix_cleaned.csv.

📬 Contact Information
Name: [Your Name]

LinkedIn: linkedin.com/in/your-profile-url

Email: youremail@example.com
