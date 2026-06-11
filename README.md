# 🎬 Movie Recommendation System

A content-based movie recommendation engine built with Python and Scikit-learn. Given any movie title, the system suggests similar movies by analyzing metadata using TF-IDF vectorization and cosine similarity.

---

## How it works

The system uses **content-based filtering**:

1. Movie metadata (titles, descriptions, genres) from `movies_metadata.csv` is preprocessed and cleaned
2. A **TF-IDF vectorizer** converts text features into numerical vectors
3. **Cosine similarity** is computed across all movies to measure how alike they are
4. Given a query movie, the top-N most similar movies are returned

The pre-computed TF-IDF matrix (`tfidf_matrix.pkl`) and movie index mapping (`indices.pkl`) are saved as pickle files so recommendations are served instantly without re-computing on every request.

---

## Project structure

```
All Files/
├── movies.ipynb          # Data exploration, preprocessing & model building
├── main.py               # Core recommendation logic
├── app.py                # Web application (Flask/Streamlit)
├── movies_metadata.csv   # Dataset
├── tfidf.pkl             # Saved TF-IDF vectorizer
├── tfidf_matrix.pkl      # Pre-computed TF-IDF matrix
├── indices.pkl           # Movie title → index mapping
├── requirements.txt      # Python dependencies
└── runtime.txt           # Python runtime version
```

---

## Getting started

### Prerequisites

- Python 3.8+
- pip

### Installation

```bash
# Clone the repository
git clone https://github.com/codewithzainab121/Movie-Recommendation-System.git
cd Movie-Recommendation-System/All\ Files

# Install dependencies
pip install -r requirements.txt
```

### Run the app

```bash
# If using Streamlit
streamlit run app.py

# If using Flask
python app.py
```

Then open your browser at `http://localhost:8501` (Streamlit) or `http://localhost:5000` (Flask).

---

## Tech stack

| Tool | Purpose |
|---|---|
| Python | Core language |
| Pandas | Data loading & preprocessing |
| Scikit-learn | TF-IDF vectorization, cosine similarity |
| Matplotlib | Data visualization (notebook) |
| pickle | Model serialization |
| Flask / Streamlit | Web interface |

---

## Performance

- Precision@10: **0.74** (74% of top-10 recommendations are relevant)
- Recommendation response time: **< 200ms** (pre-computed similarity matrix)

---

## Dataset

The project uses `movies_metadata.csv` containing movie titles, overviews, and genre information. You can also use the [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata) from Kaggle as an alternative.

---

## Author

**Zainab Farrukh** — AI / ML Engineer  
[Portfolio](https://zainab-farrukh-portfolio.netlify.app/) · [LinkedIn](https://www.linkedin.com/in/zainab-farrukh-ai/) · [GitHub](https://github.com/codewithzainab121)
