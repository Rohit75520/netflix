## Netflix Data Exploration Project

### Overview
This project involves a comprehensive data exploration and analysis of a Netflix Movies and TV Shows dataset. The primary goal is to extract meaningful insights and provide actionable recommendations for aspiring data analysts and scientists, as well as for Netflix, to inform content strategy and business growth.

### Dataset
The dataset used in this project is a tabular CSV file containing listings of all movies and TV shows available on Netflix. It includes various details such as `show_id`, `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in` (genre), and `description`.

**Source:** [Netflix Shows on Kaggle](https://www.kaggle.com/shivamb/netflix-shows)

### Problem Statement & Objectives
As a data analyst/scientist at Netflix, the objectives of this case study are to:
* Analyze the provided Netflix dataset to identify trends and patterns.
* Extract valuable insights regarding content characteristics, production, and viewer behavior.
* Provide data-driven recommendations.
* Enhance practical skills in data analysis using Python.

### Analysis Steps & Key Insights

The analysis involved several stages, from data preparation to detailed exploratory data analysis.

#### 1. Data Preparation: Un-nesting Columns & Handling Null Values

**Objective:** To clean and prepare the dataset for analysis by addressing structured data within single cells and managing missing values.

* **Un-nesting Columns:** Columns like `director`, `cast`, and `listed_in` often contained multiple comma-separated values within a single cell. These columns were "un-nested" by creating new rows for each individual value, duplicating the associated information from other columns. This transformation significantly increased the number of rows (from 8,807 to 161,216), allowing for individual analysis of directors, actors, and genres.
* **Handling Null Values:** All remaining null values in categorical columns (`director`, `cast`, `country`, `date_added`, `rating`, `duration`) were replaced with an "Unknown" placeholder (e.g., "Unknown Director," "Unknown Actor"). For `date_added` and `release_year`, these columns were also converted to appropriate datetime formats (`date_added_dt` and `release_date_approx`) to facilitate time-series analysis.

#### 2. Categorical Variable Counts (Non-Graphical & Graphical Analysis)

**Objective:** To understand the distribution and frequency of different categories within key variables.

* **Insights:**
    * **Content Type:** Movies are significantly more prevalent than TV Shows on Netflix.
    * **Top Talent/Countries:** The dataset includes a substantial number of entries with 'Unknown Director', 'Unknown Actor', and 'Unknown Country', highlighting data completeness challenges. Among known entries, the **United States** leads significantly in both movie and TV show production.
    * **Ratings:** `TV-MA` and `TV-14` are the most common content ratings.
    * **Duration:** The majority of movies are around **90-100 minutes**, while TV shows typically have **1 or 2 seasons**.
    * **Genres:** `Dramas`, `Comedies`, `International Movies`, and `International TV Shows` are among the most frequent genres.

#### 3. Comparison of TV Shows vs. Movies by Country

**Objective:** To identify the leading countries in content production for both movies and TV shows.

* **Insights:**
    * **Movies:** The **United States** and **India** are the top two countries producing movies available on Netflix.
    * **TV Shows:** The **United States** is also the primary producer of TV shows, with **South Korea** and the **United Kingdom** being notable contributors.

#### 4. Best Time to Add Content to Netflix (by Date Added)

**Objective:** To determine optimal months and weeks for adding new content to the platform.

* **Insights:**
    * **By Month:** **October, December, and January** show the highest volume of both movies and TV shows being added, aligning with holiday seasons and year-end content pushes.
    * **By Week:** While there isn't a single "best" week, high activity is generally observed in the latter part of the year, corresponding to the peak months.

#### 5. Analysis of Top Actors and Directors

**Objective:** To identify the most prolific actors and directors on Netflix.

* **Insights:**
    * **Directors:** **Raul Campos** and **Jan Suter** are highly prolific directors on Netflix based on the number of titles associated with them.
    * **Actors:** **Anupam Kher** and **Shah Rukh Khan** frequently appear in Netflix titles, indicating a strong presence of Indian cinema in the content library.

#### 6. Most Popular Genres (Word Cloud)

**Objective:** To visually represent the most dominant genres in the dataset.

* **Insights:** The word cloud visually confirms the dominance of `International Movies`, `Dramas`, `Comedies`, `International TV Shows`, and `Action & Adventure`, reflecting Netflix's broad and global content strategy.

#### 7. Time Between Movie Release and Netflix Addition

**Objective:** To understand the typical delay between a movie's original release and its availability on Netflix.

* **Insight:** The **most common time (mode)** for a movie to be added to Netflix after its release year (approximated to January 1st of that year) is **365 days (approximately one year)**. This suggests a pattern in content acquisition or licensing agreements.

### Tools Used
* **Python:** Programming language for data analysis.
* **Pandas:** For data manipulation and analysis.
* **Matplotlib:** For creating static, animated, and interactive visualizations.
* **Seaborn:** For statistical data visualization, built on Matplotlib.
* **WordCloud:** For generating word cloud visualizations of text data.
