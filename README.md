# 🧹 Netflix Dataset - Data Cleaning & Preprocessing

## 🎯 Project Objective
The **main goal** of this project is to clean and preprocess the raw **Netflix Movies and TV Shows dataset**.  
The dataset often contains **missing values, duplicates, and inconsistent formats**.  
This project resolves these issues to create a **structured and reliable dataset** ready for analysis.

---

## 🛠️ Tools & Libraries Used
- **Language:** Python  
- **Libraries:** `pandas`, `numpy`  
- **Environment:** Google Colab  

---

## ✨ Data Cleaning Steps

### 1️⃣ Handling Missing Values
- **`director`, `cast`, `country`** → Null values replaced with `'Unknown'`  
  *Reason:* Keeps records while indicating missing information.  

- **`date_added`** → Filled using **forward-fill (`ffill`)** and **backward-fill (`bfill`)**  
  *Reason:* Logical for chronological data; assumes missing dates are near existing ones.  

- **`rating`, `duration`** → Filled with the **mode** (most frequent value). Duration mode calculated separately for **Movies** and **TV Shows**.  
  *Reason:* Maintains column distribution without introducing bias.

---

### 2️⃣ Removing Duplicate Rows
- Removed using **`.drop_duplicates()`**  
- *Reason:* Ensures **data integrity** and avoids skewed analysis results.

---

### 3️⃣ Standardizing Text Values
- **`country`** → lowercase  
- **`rating`** → uppercase  
- Removed **leading/trailing whitespaces**  
- *Reason:* Prevents treating `"India"` and `"india"` as different categories.

---

### 4️⃣ Converting Data Formats
- **`date_added`** → Converted from string to **datetime format**  
- *Reason:* Enables **time-based analysis** like trends and sorting.

---

### 5️⃣ Renaming Columns
- **`listed_in` → `category`**  
- **`release_year` → `release_yr`**  
- *Reason:* Cleaner, intuitive column names for better readability.

---

## ✅ Final Output
The cleaned dataset is saved as:  
**`netflix_cleaned.csv`**

---

## 📬 Contact
- **Name:** [Your Name]  
- **LinkedIn:** [linkedin.com/in/your-profile-url](https://linkedin.com/in/your-profile-url)  
- **Email:** [youremail@example.com](mailto:youremail@example.com)
