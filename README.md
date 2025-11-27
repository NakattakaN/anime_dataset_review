# anime_dataset_review

# How much popularity does a anime have by its rating and popularity?
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
| 4 | My own data | My own anilist data i am going to upload | 2019 - 2025|
| 5 | Anime Dataset | [A combined data for the popularity rankings] https://www.kaggle.com/datasets/calebmwelsh/anilist-anime-dataset | This is probaby the most important one | 1950-2023|

---

## Methodology  

### 1. Data Cleaning & Preprocessing  
- Merge multiple sources of datasets.  
- Remove duplicates, standardized names, and fixed missing data.  
- Encode categorical variables (genres, studios, sources).  
- Converte airing dates into `year` and `season`.  

### 2. Exploratory Data Analysis (EDA)  
- Summary stats for ratings, members, favorites, and episode counts.  
- Visualize genre distributions and correlations.  
- Examine release trends across seasons and decades.  

### 3. Statistical Analysis  
- Correlation and regression analysis for rating vs. features.  
- ANOVA tests for genre or studio differences.  
- Seasonal trend analysis for release and popularity data.  

### 4. Machine Learning Models (optional)  
- Regression models (Linear, Random Forest) to predict popularity score.  
- Classification (e.g., “Hit” vs “Non-Hit” anime).  
- Feature importance visualization.



## 💻 Technical Details  

**Language:** Python  
**Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `plotly`, `scikit-learn`, `statsmodels`, `requests`  


