# Data Vortex - Round 1: Data Cleaning & Exploratory Data Analysis (EDA)

## Project Overview
This repository contains the data cleaning, preprocessing pipeline, and exploratory data analysis (EDA) for **Data Vortex Round 1**. The objective is to transform raw, corrupted social media and user datasets into clean, robust formats ready for advanced analytics, machine learning, and Natural Language Processing (NLP) in subsequent rounds.

---

## 1. Reproducible Workflow & Data Cleaning Pipeline
The cleaning pipeline is implemented in Python (`Notebook_of_code.ipynb`) using `pandas` and handles the following data issues:
* **Duplicate Removal:** Dropped redundant records across both `Social_Engine_Users.csv` and `Social_Engine_Posts_Corrupted.csv`.
* **Missing Value Imputation:**
  * **Numerical Columns (`likes`, `shares`, `comments`):** Imputed missing values using the **statistical median** rather than crude zeros to prevent zero-inflation bias in machine learning models.
  * **Categorical Columns (`platform`):** Labeled missing platform types as `"Unknown"`.
  * **Text Content (`text_content`):** Left missing text entries completely blank (`""`) to ensure compatibility with future NLP tokenizers and word embeddings.
* **Robust Timestamp Parsing:** Handled mixed date formats (Unix epoch numbers, ISO strings, and standard dates) uniformly without throwing warnings or corrupting valid time entries.

---

## 2. Exploratory Data Analysis (EDA) Findings
* **Platform Engagement:** Cumulative platform analysis shows that Facebook and YouTube drive the highest aggregate interaction volume (likes), though overall user engagement remains steady across platforms.
* **Engagement Correlation:** The correlation heatmap reveals near-zero linear correlation among `likes`, `shares`, and `comments`, indicating that individual user actions occur independently per post.
* **User Demographics:** The average user follower count sits at ~24,964, with major user concentration hubs located in global metropolitan centers.

---

## 3. Project File Structure
- `Notebook_of_code.ipynb`: The complete executable Jupyter notebook containing code, charts, and markdown findings.
- `Social_Engine_Users_Cleaned.csv`: The cleaned user dataset.
- `Social_Engine_Posts_Cleaned.csv`: The cleaned and imputed posts dataset.
- `platform_engagement.png`, `follower_distribution.png`, `engagement_correlation.png`: Generated EDA visualization plots.
