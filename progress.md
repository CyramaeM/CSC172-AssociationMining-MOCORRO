# CSC172 Association Rule Mining Progress Report

**Student:** Cyramae P. Mocorro, 2018-1345  
**Date:** December 16, 2025  
**Repository:** https://github.com/CyramaeM/CSC172-AssociationMining-MOCORRO  

---

## 📊 Current Status

| Milestone | Status | Notes |
|-----------|--------|-------|
| Dataset Preparation | ✅ Completed | Movie metadata and ratings merged successfully |
| Data Preprocessing | ✅ Completed | Cleaned ratings, one-hot encoded transaction matrix |
| EDA & Visualization | ✅ Completed | Rating distribution, top movies, sparsity heatmap |
| Apriori Implementation | ✅ Completed | Frequent itemsets generated (min_support = 0.05) |
| Rule Evaluation | ✅ Completed | Confidence, lift-based filtering applied |

---

## 1. Dataset Progress

- **Total users (transactions):** 671  
- **Total ratings processed:** 100,000+ (ratings_small subset)  
- **Unique movies after filtering:** ~1,000  
- **Final transaction matrix:** 671 users × selected movies  
- **Preprocessing applied:**  
  - Missing values removed  
  - Movie IDs converted to numeric  
  - Ratings filtered (rating ≥ 4.0)  
  - One-hot encoding using TransactionEncoder  

**Sample transaction preview:**

- Transaction 1 (User 1): `['Toy Story', 'Jumanji', 'Heat']`  
- Transaction 2 (User 2): `['GoldenEye', 'Casino']`  

---

## 2. EDA Progress

**Key Findings:**
- Ratings are skewed toward higher values (4.0–5.0)
- A small number of movies dominate user ratings
- Transaction matrix is sparse, which is expected in recommendation datasets

**Current Metrics:**

| Metric | Value |
|-------|-------|
| Cleaned ratings | ~95% retained |
| Positive ratings threshold | ≥ 4.0 |
| Transaction sparsity | High (binary matrix) |
| Top rated movie | Appears in most transactions |

---

## 3. Challenges Encountered & Solutions

| Issue | Status | Resolution |
|------|--------|------------|
| Duplicate preprocessing steps | ✅ Fixed | Refactored notebook cells |
| Sparse transaction matrix | ✅ Expected | Used min_support filtering |
| Rule interpretability | ✅ Fixed | Converted rules to natural language |

---

## 4. Next Steps (Before Final Submission)

- [x] Generate readable rules (“People who like A also like B”)
- [x] Visualize rule confidence vs lift
- [ ] Fine-tune min_support and confidence thresholds
- [ ] Export top rules to CSV
- [ ] Finalize README and notebook markdown
- [ ] Prepare short video presentation

