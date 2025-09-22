🧹 Netflix Dataset - Data Cleaning & Preprocessing
🎯 Project Objective

The primary goal of this project is to clean and preprocess the raw Netflix Movies and TV Shows dataset. The dataset often contains missing values, duplicates, and inconsistent formats. This task resolves these issues to produce a structured and reliable dataset ready for analysis.

🛠️ Tools & Libraries Used

Language: Python

Libraries: pandas, numpy

Environment: Google Colab

✨ Steps Performed for Data Cleaning
1. Handling Missing Values

Missing data can lead to errors or biased results. Different strategies were applied depending on the column:

director, cast, country:

Action: Null values replaced with 'Unknown'

Reason: Keeps valuable records while indicating missing information clearly.

date_added:

Action: Missing values filled using forward-fill (ffill) and backward-fill (bfill)

Reason: Logical for chronological data; assumes missing dates are near available ones.

rating, duration:

Action: Missing values filled with the mode (most frequent value). Duration mode was calculated separately for Movie and TV Show.

Reason: Safe approach to maintain column distribution without introducing bias.

2. Removing Duplicate Rows

Action: Duplicate entries were removed using .drop_duplicates().

Reason: Ensures data integrity and prevents skewed analysis results.

3. Standardizing Text Values

Action:

country converted to lowercase

rating converted to uppercase

Leading/trailing whitespaces removed

Reason: Ensures consistency; avoids treating values like "India" and "india" as separate categories.

4. Converting Data Formats

Action: date_added converted from string (object) to datetime format.

Reason: Enables time-based analysis (e.g., trends, sorting) that is not possible with plain text.

5. Renaming Columns

Action:

listed_in → category

release_year → release_yr

Reason: Clean and intuitive names improve readability and usability of the dataset.

✅ Final Output

The cleaned and preprocessed dataset has been saved as:
netflix_cleaned.csv

📬 Contact Information

Name: [Your Name]

LinkedIn: linkedin.com/in/your-profile-url

Email: youremail@example.com
