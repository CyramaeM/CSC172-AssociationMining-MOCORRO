# Movie Recommendation Pattern Mining using Association Rules

**CSC172 Data Mining and Analysis Final Project**  
*Mindanao State University – Iligan Institute of Technology*  

**Student:** Cyramae P. Mocorro, 2018-1345  
**Semester:** AY 2025–2026, Semester 1  

---

## Abstract

This project applies association rule mining to a movie ratings dataset to uncover patterns in user preferences. Using the Apriori algorithm, the study identifies relationships such as *“People who like Movie A also like Movie B.”* The analysis pipeline includes data cleaning, transformation of user ratings into transaction format, exploratory data analysis, rule generation, and evaluation using support, confidence, and lift metrics. The results demonstrate the potential of association rules in building interpretable movie recommendation systems.

---

## 1. Introduction

### 1.1 Problem Statement
Movie streaming platforms store large volumes of user ratings, but extracting meaningful relationships between movies is challenging. This project aims to discover co-liked movies based on user ratings to support recommendation strategies.

### 1.2 Objectives
- Preprocess movie metadata and user ratings
- Convert ratings into transaction-based format
- Apply Apriori algorithm for association rule mining
- Generate interpretable movie recommendation rules
- Visualize and evaluate rule strength

### 1.3 Scope and Limitations
**Scope:**  
Analysis is limited to a subset of the MovieLens dataset using binary “liked” interactions.

**Limitations:**  
- No temporal viewing behavior  
- No demographic user data  
- Ratings treated as binary (liked / not liked)

---

## 2. Dataset Description

### 2.1 Source and Acquisition
**Source:** MovieLens Dataset  
- `movies_metadata.csv`
- `ratings_small.csv`

### 2.2 Data Structure

Raw format:
userId, movieId, rating
1, 31, 4.0
1, 1029, 5.0

Transaction format:


### 2.3 Sample Transactions
- User 1: `['Toy Story', 'Jumanji', 'Heat']`
- User 2: `['GoldenEye', 'Casino']`
- User 3: `['Seven', 'Usual Suspects']`

---

## 3. Methodology

### 3.1 Data Preprocessing
1. Removed missing movie titles and ratings  
2. Converted movie IDs to numeric  
3. Filtered ratings ≥ 4.0 (liked movies)  
4. Grouped movies per user  
5. One-hot encoded transactions using TransactionEncoder  

### 3.2 Exploratory Data Analysis
- Rating distribution shows positive bias
- Few popular movies dominate ratings
- Transaction matrix is sparse but suitable for Apriori

### 3.3 Apriori Algorithm Implementation
Implemented using:
- `apriori()` for frequent itemsets
- `association_rules()` for rule generation

### 3.4 Evaluation Metrics
- **Support:** Frequency of itemset occurrence  
- **Confidence:** Likelihood of consequent given antecedent  
- **Lift:** Strength of association (>1 indicates positive correlation)

---

## 4. Results

### 4.1 Top Association Rules

| Rule | Confidence | Lift |
|----|------------|------|
| People who like High Noon also like Terminator 3: Rise of the Machines | 0.90 | 2.39 |
| People who like Point Break also like Terminator 3: Rise of the Machines | 0.85 | 2.27 |
| People who like The Talented Mr. Ripley also like Terminator 3: Rise of the Machines | 0.85 | 2.25 |
| People who like Waiter also like Muxmäuschenstill | 0.82 | 9.82 |
| People who like The Science of Sleep also like Terminator 3: Rise of the Machines | 0.82 | 2.18 |

### 4.2 Key Visualizations
- Rating distribution plot
- Top-rated movies bar chart
- Transaction heatmap
- Confidence vs lift scatter plot

### 4.3 Performance Metrics
- Efficient execution on standard laptop
- Apriori completed within seconds on filtered dataset

---

## 5. Discussion

### 5.1 Insights
- Popular movies act as hubs in association rules
- Strong genre-based relationships emerge
- High-lift rules suggest meaningful co-preference

### 5.2 Recommendations
- Use rules for movie recommendations
- Suggest similar movies after user interaction
- Group related movies in platform UI

### 5.3 Limitations
- Binary ratings reduce nuance
- No personalization beyond co-occurrence

---

## 6. Conclusion

The project successfully demonstrates how association rule mining can uncover meaningful patterns in movie ratings data. The Apriori algorithm produced interpretable and actionable rules suitable for recommendation systems.

---

## 7. Video Presentation
*A 5-minute demo explaining the dataset, methodology, and key findings.*

---

## References
1. Agrawal, R., & Srikant, R. (1994). Fast Algorithms for Mining Association Rules.  
2. MovieLens Dataset: https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset/versions/5/data?select=ratings_small.csv
3. mlxtend Documentation

---

