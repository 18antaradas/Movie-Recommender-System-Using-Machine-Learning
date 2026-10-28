# 🎬 Movie Recommender System Using Machine Learning

A content-based movie recommendation system that suggests similar movies using **NLP**, **Bag-of-Words vectorization** and **cosine similarity**, with a **Streamlit** web interface that shows posters, release year and ratings from the **TMDB API**.

> Machine Learning project (MC470305), MCA, Department of Computer Science & Engineering, **NIT Patna** (July 2025 – Dec 2025).

---

## 📌 Overview

Users face an overwhelming number of choices on streaming platforms. This project recommends movies similar to the one a user selects by analysing movie metadata: genres, keywords, cast, crew and overview.

```
TMDB movies + credits datasets
              ↓
   Cleaning + feature extraction
              ↓
 "tags" column + stemming (NLTK)
              ↓
 CountVectorizer (Bag-of-Words)
              ↓
      Cosine similarity matrix
              ↓
 Streamlit app → Top 5 recommendations
```

## ✨ Features

- Content-based recommendations from genres, keywords, cast, crew and overview
- Streamlit dropdown interface: pick a movie, get 5 similar ones
- Live posters, release year and ratings from the TMDB API
- Pickled model for fast loading without retraining

## ⚙️ Methodology

1. **Load and merge** the TMDB movies and credits datasets on `title`
2. **Clean** nulls and duplicates
3. **Extract features:** convert JSON-like strings to lists, keep the top 3 cast members and the director, remove spaces from names, lowercase everything
4. **Create tags** by combining overview, genres, keywords, cast and crew
5. **Stem** words with NLTK's Porter Stemmer
6. **Vectorize** tags using `CountVectorizer` (Bag-of-Words)
7. **Compute cosine similarity** between all movie vectors
8. **Recommend:** `recommend(movie)` returns the top 5 most similar movies
9. **Serve** via Streamlit and fetch posters and details from TMDB

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Language | Python 3.8+ |
| Data handling | Pandas |
| ML | Scikit-learn (CountVectorizer, cosine similarity) |
| NLP | NLTK (Porter Stemmer) |
| Web app | Streamlit |
| Model storage | Pickle |
| API | TMDB API, Requests |

## 📁 Project Structure

```
├── app.py                # Streamlit application
├── notebook.ipynb        # Data processing and model building
├── movies_dict.pkl       # Processed movie data
├── similarity.pkl        # Cosine similarity matrix
├── requirements.txt
└── README.md
```

*(Adjust file names to match your repository.)*

## 🚀 Getting Started

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
pip install pandas scikit-learn nltk streamlit requests
streamlit run app.py
```

Add your own [TMDB API key](https://www.themoviedb.org/documentation/api) in the app where poster requests are made. An internet connection is required to load posters.

## ⚠️ Limitations

- Content-based only; it does not learn user preferences
- Quality depends on the TMDB dataset
- Needs internet for posters via the TMDB API
- No collaborative filtering or deep learning

## 🔮 Future Enhancements

- User-based and hybrid recommendation
- Collaborative filtering for personalisation
- Deep learning (ANN / BERT embeddings)
- Richer Streamlit dashboards
- Deployment on AWS, Render or Heroku

## 👩‍💻 Author

**Nikita Mewada** (Roll No. 2447027)
**Supervisor:** Dr. Shyam Singh Rajput, Assistant Professor, CSE Department, NIT Patna

## 📚 References

Scikit-Learn, Streamlit, NLTK and TMDB API documentation; Kaggle TMDB Movie Dataset.

## 📄 License

For academic and educational purposes.
