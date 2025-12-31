# Netflix Data Cleaning & Analysis | End-to-End Data ELT Engineering Project

![SQL Server]()
![Python]()
![Pandas]()

## 📌 Project Overview
This project demonstrates a **ELT (Extract, Load, Transform)** pipeline. I took a raw, unorganized dataset of Netflix movies and TV shows and transformed it into a fully normalized relational database. The project focuses on solving data integrity issues, handling complex many-to-many relationships, and extracting meaningful business insights using advanced SQL.



---

## 🏗️ The Pipeline Architecture

1.  **Extraction:** Scoped the dataset and analyzed column constraints using Python.
2.  **Loading:** Ingested raw data into **Microsoft SQL Server** using `SQLAlchemy` and `Pandas`.
3.  **Transformation (The Core):**
    * **Normalization:** Split multi-valued columns (Directors, Cast, Country) into separate relational tables to reach 3rd Normal Form (3NF).
    * **Data Imputation:** Filled missing values in the `country` column by mapping directors to their most frequent production countries.
    * **Data Cleaning:** Resolved data type conflicts (e.g., duration values mistakenly placed in the rating column).
    * **Deduplication:** Used Window Functions (`ROW_NUMBER`) to ensure unique entries.

---

## 🛠️ Tech Stack
* **Data Processing:** Python (Pandas)
* **Database Engine:** Microsoft SQL Server (T-SQL)
* **Version Control:** Git & GitHub
* **SQL Concepts:** CTEs, Window Functions, `CROSS APPLY`, `STRING_SPLIT`, Schema Design.

---

## 📂 Database Schema Design
To eliminate data redundancy, the flat `netflix_raw` table was decomposed into:

* **`netflix_titles`**: Central table for unique show metadata.
* **`netflix_directors`**: Maps shows to their respective directors.
* **`netflix_cast`**: Maps shows to their cast members.
* **`netflix_genres`**: Maps shows to their categories.
* **`netflix_countries`**: Maps shows to production locations.



[]


---

## 📊 Business Insights Extracted
The following business questions were answered using SQL:
* **Content Versatility:** Identified directors who successfully produced both "Movies" and "TV Shows."
* **Regional Trends:** Determined which country produces the highest volume of "Comedy" content.
* **Growth Metrics:** Calculated the top-performing director of each year based on content additions.
* **Genre Analysis:** Average duration of movies categorized by genre.
* **The "Horror-Comedy" Bridge:** Found directors who have worked across both specific genres.

---

## 🚀 How to Run
1.  **Clone the Repository:**
    ```bash
    git clone []()
    ```
2.  **Setup Database:** Run the Python script `data_ingestion.py` to load the CSV data into your SQL instance.
3.  **Execute Transformations:** Run the `transformation.sql` script to build the normalized schema.
4.  **Run Analysis:** Use `analysis_queries.sql` to view the final reports.

---

## 💡 Key Learnings
* Moving from flat-file processing to a **relational database mindset**.
* Using **CTEs** to make complex SQL logic readable and maintainable.
* The critical role of **Schema Design** in data engineering to prevent data anomalies.

---
**
