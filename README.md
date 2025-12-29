# anime_dataset_review

# DSA210 ANİME DATA ANALYSYS
**DSA210 – Introduction to Data Science**  
**Fall 2025 Term Project**

---

## Introduction  

This project explores what makes certain anime popular — and how factors like genre, studio, source material, and season of release affect audience ratings and engagement.  

Using datasets from **MyAnimeList (MAL)** and **AniList** and my own personal anilist data to understand a users general behaviours.

The goal is to find meaningful connections between an anime’s features and its success, as well as to see how online attention and release timing influence ratings. 

The latter transformator implementation will use ROBERTA and will try to guess the popularity considering MAL and ANILIST ratings.

---

## Motivation  

This projects motivation is to understand the correlation beetwen animes popularity and rating.

This project looks into questions like:  
- Do specific genres perform better in certain decades or seasons?  
- How do **studios** and **source materials** (manga, novel, game, original) impact ratings?  
- Is there a link between **online hype** and **user ratings**?  
- Can we predict an anime’s success from its metadata alone?  

By analyzing these aspects, we can better understand audience behavior and cultural trends within anime communities.

---

## Project Goals  

- Analyze **anime trends** over time by decade, genre, and studio.  
- Identify which factors most affect **ratings and popularity**.  
- Explore **seasonal release trends** (Winter, Spring, Summer, Fall).  
- Compare **online attention** with viewer scores.  
- Build simple **predictive models** for anime popularity.  
- Visualize data to show changes in the anime industry over time.

---

## Data Sources  

| # | Data Type | Source | Description | Years Covered |
|---|------------|---------|--------------|----------------|
| 1 | Anime Metadata | [MyAnimeList Dataset (Kaggle)](https://www.kaggle.com/datasets/dbdmobile/myanimelist-dataset) | Core anime data: title, genre, studio, rating, popularity, members | 1950–2024 |
| 2 | Anime Metadata | [AniList API](https://anilist.gitbook.io/anilist-apiv2-docs/) | Used for updating newer anime (2024–2025) | 2024–2025 |
| 3 | Anime dataset | [A combined metadata] (https://github.com/manami-project/anime-offline-database) | Combined metadata | 1950 -2025 |
| 4 | My own data | Anilist.xml file i uploaded contains my own data -> user anilist normaliz | 2019 - 2025|
| 5 | Anime Dataset | [A combined data for the popularity rankings] https://www.kaggle.com/datasets/calebmwelsh/anilist-anime-dataset | This is probaby the most important one | 1950-2023|

---

## Methodology  

### 1. Data Cleaning & Preprocessing  
- ID-Based Linking: Instead of unreliable string matching (names), I use the MyAnimeList ID (mal_id) as the primary key.
- The Join: I perform an Inner Join between my personal dataset and the Global AniList dataset: df_user['mal_id'] ↔ df_global['idMal']
- This creates a merged dataset containing only the anime I have watched, allowing me to calculate a "Score Divergence" (My Score - Global Score) for every entry.
- You can find these in test.py
- XML Conversion: Since the personal data comes in a raw XML format, I implemented a custom parser (xml.etree.ElementTree) to extract the my_score, my_status, and mal_id fields into a structured CSV format (user_animelist_normalized.csv).
-Binning: For the global analysis, I categorized anime into score tiers (e.g., <4, 4-5, 8-9, 9-10) to visualize the density of anime quality versus popularity.
- You can find these in test.py

### 2. Exploratory Data Analysis (EDA)  
- Correlation Analysis: I calculated the Pearson correlation coefficient (found to be ≈0.42) to quantify the relationship between an anime’s Rating and its Popularity.
- Outlier Detection: I implemented logic to identify "Hidden Gems" (anime with High Ratings >85 but Low Popularity < Median) and "Overhyped" shows.
- Bias Distribution: I plotted the distribution of my personal rating deviations to see if I am generally a "Hater" (negative deviation) or a "Fanboy" (positive deviation) compared to the global average.
- You can find these in test.py

### 3. Statistical Analysis  
- T-Test (Source Material): I compared the mean popularity of "Manga Adaptations" vs. "Original Anime." Result: Significant difference (p<0.05), proving Manga adaptations generally have higher pre-existing fanbases.
-One-Way ANOVA (Seasonality): I tested if the release season (Winter, Spring, Summer, Fall) has a statistically significant impact on the final score. Result: The release window does affect the critical reception of an anime (p≈0.01).
- You can find these in test.py

### 5. Recomendation engine
- Although my initial purpose was to make a hit-vs-nonhit anime with a roberta model i decided to add another model of a recomendation engine
- This will have some ml algorithms you can find the corresponding algorith in the corresponding jupiter notebook
- They are named as recom_[alg-name].py


## 💻 Technical Details  

**Language:** Python  
**Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `plotly`, `scikit-learn`, `statsmodels`, `requests`  


