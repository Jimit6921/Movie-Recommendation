# 🎬 Movie Recommendation System

> A Machine Learning project using **KNN** and **SVD** for personalized movie recommendations based on Collaborative Filtering.

---

## 📌 Project Overview

This system recommends movies to users by analyzing **100,000 ratings** from real users.
Instead of looking at movie content (genre, director), it finds patterns in **how people rate movies** — if two users liked the same 10 movies, they'll probably like each other's favorites too.

This technique is called **Collaborative Filtering** and it powers Netflix, Amazon, and Spotify recommendations.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.x | Core language |
| Pandas | Data loading and manipulation |
| NumPy | Matrix operations |
| Scikit-learn | KNN model |
| Scikit-surprise | SVD model |
| SciPy | Sparse matrix handling |
| Matplotlib & Seaborn | Data visualization |
| Google Colab | Development environment |

---

## 📦 Dataset

**MovieLens 100K** — GroupLens Research, University of Minnesota

| Stat | Value |
|------|-------|
| Total Ratings | 100,000 |
| Total Users | 943 |
| Total Movies | 1,682 |
| Rating Scale | 1 to 5 |
| Matrix Sparsity | ~93.7% |

📥 Dataset is auto-downloaded in the notebook — no manual setup needed.

---

## 🤖 Algorithms Used

### 1. KNN — K-Nearest Neighbors (Item-Based Collaborative Filtering)
- Builds a **User × Movie** matrix of ratings
- Transposes it to **Movie × User** matrix
- Uses **Cosine Similarity** to find movies with similar rating patterns
- Returns the top-N most similar movies

**Why Cosine Similarity?**
It measures the *angle* between two rating vectors, not their magnitude.
A user who rates 3 movies moderately is treated similarly to one who rates the same 3 movies highly — because the *preference pattern* is the same.

---

### 2. SVD — Singular Value Decomposition (Matrix Factorization)
- Decomposes the rating matrix into hidden **latent factors** (e.g., genre, mood, era)
- Predicts what rating a user would give to an unseen movie
- Won the **Netflix Prize** competition in 2009

---

## 📊 Results

| Metric | Value |
|--------|-------|
| KNN Similarity Score | 0% – 100% per movie pair |
| SVD RMSE (5-fold CV) | ~0.93 |
| SVD MAE (5-fold CV) | ~0.73 |

> RMSE of **0.93 on a 1–5 scale** means predictions are off by less than 1 star on average ✅

---

## 🚀 How to Run

1. Open the notebook in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

2. Run all cells from top to bottom (`Runtime → Run all`)
3. Dataset downloads automatically
4. Enter any movie name when prompted to get recommendations

---

## 💡 Sample Output

```
🎬 Because you liked: 'Star Wars (1977)'
📽️  Top 8 Recommendations:

Rank   Movie Title                                        Similarity
----------------------------------------------------------------------
1      Return of the Jedi (1983)                          92.34%
2      Raiders of the Lost Ark (1981)                     89.12%
3      Empire Strikes Back, The (1980)                    88.76%
4      Fugitive, The (1993)                               85.43%
5      Schindler's List (1993)                            84.91%
6      Shawshank Redemption, The (1994)                   83.67%
7      Silence of the Lambs, The (1991)                   82.55%
8      Fargo (1996)                                       81.23%
```

---

## 🔑 Key Concepts Explained

**Collaborative Filtering**
Recommends based on user behavior, not movie content. "Users like you also liked..."

**Cold Start Problem**
New users or movies have no ratings, so KNN can't recommend for them.
SVD partially solves this via latent factors.

**Sparse Matrix**
93.7% of ratings are missing (most users haven't seen most movies).
This is the core challenge of recommendation systems.

**RMSE vs MAE**
- RMSE penalizes large errors more heavily
- MAE gives equal weight to all errors
- Both used together for a complete picture of model performance

---

## 📁 Project Structure

```
movie-recommendation-system/
│
├── 📓 movie_recommender.ipynb    # Complete Colab notebook
├── 📄 README.md                  # Project documentation
```

---

## 🧠 Future Improvements

- [ ] Add Content-Based Filtering (using movie genres, cast, director)
- [ ] Build a Hybrid Model (Collaborative + Content-Based)
- [ ] Deploy as a Web App using Streamlit or Flask
- [ ] Use ALS (Alternating Least Squares) for better scalability
- [ ] Add FAISS for faster Approximate Nearest Neighbor search

---

## 👨‍💻 Author

**Your Name**
📧 your@email.com
🔗 [LinkedIn](https://linkedin.com/in/yourprofile)
🐙 [GitHub](https://github.com/yourusername)

---

## 🏢 Project Context

Built as part of the interview process for **Webosphere**.
Demonstrates practical ML skills in recommendation systems, collaborative filtering, and model evaluation.

---

## 📜 License

This project is open source and available under the [MIT License](LICENSE).

---

⭐ *If you found this helpful, give it a star!*
