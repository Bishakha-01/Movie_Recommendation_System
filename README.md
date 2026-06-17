# 🎬 Movie Recommendation System

## 📌 Overview

Movie Recommendation System is a full-stack machine learning application that recommends movies based on content similarity using Natural Language Processing (NLP) techniques and metadata analysis.

The system leverages **TF-IDF Vectorization** and **Cosine Similarity** to identify movies with similar content and provides an interactive user experience through a **Streamlit frontend** and **FastAPI backend**.

To enhance recommendation quality and user experience, the system integrates with **The Movie Database (TMDB) API** to fetch real-time movie information such as posters, ratings, genres, release dates, and movie descriptions.

---

# 🚀 Features

### 🔍 Smart Movie Search

Search movies using title-based matching and TMDB integration.

### 🎯 Personalized Recommendations

Generate movie recommendations based on content similarity rather than popularity.

### 🖼️ Real Movie Posters

Fetch high-quality movie posters directly from TMDB.

### 📖 Detailed Movie Information

View:

- Movie Overview
- Release Date
- Genres
- Ratings
- Poster Images
- Backdrop Images

### ⚡ Fast Recommendation Engine

Uses precomputed TF-IDF matrices and serialized artifacts for low-latency recommendations.

### 🌐 REST API

Backend APIs built using FastAPI.

### 🎨 Modern User Interface

Interactive frontend developed using Streamlit.

### ☁️ Cloud Deployment Ready

Backend architecture designed for deployment on services such as:

- Render
- Railway
- AWS
- Azure
- Google Cloud

---

# 🎯 Problem Statement

With thousands of movies available across streaming platforms, discovering relevant content has become increasingly difficult.

The goal of this project is to build an intelligent recommendation system that suggests movies based on their content, themes, and descriptions rather than relying solely on user ratings or popularity rankings.

---

# 🧠 Recommendation Methodology

The system follows a **Content-Based Filtering** approach.

Instead of recommending movies liked by other users, the system recommends movies that are similar in content to the selected movie.

---

## Recommendation Pipeline

```text
Movie Metadata
       │
       ▼
Text Preprocessing
       │
       ▼
TF-IDF Vectorization
       │
       ▼
Feature Matrix Creation
       │
       ▼
Cosine Similarity Calculation
       │
       ▼
Top Similar Movies
       │
       ▼
Recommendation Results
```

---

# 📊 Dataset

The project uses movie metadata containing:

- Movie Titles
- Movie Descriptions
- Genres
- Keywords
- Additional Movie Information

### Dataset File

```text
movies_metadata.csv
```

The metadata is transformed into numerical representations for recommendation generation.

---

# 🔍 Data Preprocessing

The following preprocessing steps were applied:

### Data Cleaning

- Missing value handling
- Duplicate removal
- Invalid record filtering

### Text Processing

- Text normalization
- Feature extraction
- Metadata transformation

### Feature Engineering

Relevant textual information was combined to create a meaningful representation of each movie.

---

# 🤖 Machine Learning Model

## TF-IDF Vectorization

The recommendation engine uses:

```python
TfidfVectorizer()
```

to transform movie descriptions and metadata into numerical vectors.

### Why TF-IDF?

TF-IDF helps identify important words in movie descriptions while reducing the influence of commonly occurring terms.

Benefits:

✅ Lightweight

✅ Interpretable

✅ Fast

✅ Effective for content-based recommendation systems

---

# 📈 Similarity Calculation

Movie similarity is computed using:

```python
Cosine Similarity
```

### Formula

```text
Similarity(A,B) =
A · B
-----------
||A|| ||B||
```

Movies with higher similarity scores are considered more relevant recommendations.

---

# 🏗️ System Architecture

```text
                User
                  │
                  ▼
       Streamlit Frontend
                  │
                  ▼
           FastAPI Backend
                  │
       ┌──────────┼──────────┐
       │          │          │
       ▼          ▼          ▼
   TF-IDF     Cosine      TMDB API
 Vectorizer  Similarity   Integration
       │
       ▼
 Movie Recommendations
```

---

# ⚙️ Backend Development

The backend is developed using **FastAPI**.

### Core Responsibilities

- Movie Search APIs
- Recommendation APIs
- TMDB Integration
- Movie Details Retrieval
- Similar Movie Generation

### Backend Technologies

- FastAPI
- HTTPX
- Pydantic
- Python Dotenv

---

# 🎨 Frontend Development

The frontend is developed using **Streamlit**.

### Features

- Movie Search Interface
- Recommendation Grid
- Movie Detail View
- Poster Display
- Dynamic Navigation
- Query-Based Routing

### User Experience Features

- Responsive Layout
- Cached API Requests
- Fast Navigation
- Modern UI Components

---

# 🔗 TMDB Integration

The application integrates with:

**The Movie Database (TMDB)**

to retrieve:

- Posters
- Ratings
- Genres
- Release Dates
- Movie Descriptions
- Backdrop Images

This significantly improves recommendation quality and user experience.

---

# 💾 Model Serialization

To improve performance and avoid retraining during runtime, several artifacts are precomputed and stored.

### Serialized Files

```text
tfidf.pkl
tfidf_matrix.pkl
indices.pkl
df.pkl
```

### Purpose

| File | Description |
|--------|-------------|
| tfidf.pkl | Trained TF-IDF Vectorizer |
| tfidf_matrix.pkl | TF-IDF Feature Matrix |
| indices.pkl | Movie Index Mapping |
| df.pkl | Processed Dataset |

This enables instant recommendation generation.

---

# 📂 Project Structure

```text
Movie_Recommendation_System/
│
├── app.py
├── main.py
│
├── movies.ipynb
├── movies_metadata.csv
│
├── tfidf.pkl
├── tfidf_matrix.pkl
├── indices.pkl
├── df.pkl
│
├── requirements.txt
├── runtime.txt
├── .gitignore
├── README.md
│
└── assets/
```

---

# 🛠️ Technologies Used

## Programming Language

- Python

## Data Analysis

- Pandas
- NumPy

## Machine Learning

- Scikit-Learn

## NLP

- TF-IDF Vectorization
- Cosine Similarity

## Backend

- FastAPI
- Uvicorn
- HTTPX
- Pydantic

## Frontend

- Streamlit

## External APIs

- TMDB API

---

# 🚀 Installation

## Clone Repository

```bash
git clone https://github.com/your-username/Movie_Recommendation_System.git
```

## Move into Project Folder

```bash
cd Movie_Recommendation_System
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🔑 Environment Variables

Create a `.env` file:

```env
TMDB_API_KEY=YOUR_TMDB_API_KEY
```

Obtain a free API key from:

https://developer.themoviedb.org

---

# ▶️ Running the Backend

```bash
uvicorn main:app --reload
```

Backend runs at:

```text
http://127.0.0.1:8000
```

---

# ▶️ Running the Frontend

```bash
streamlit run app.py
```

Frontend runs at:

```text
http://localhost:8501
```

---

# 📊 Future Improvements

### Recommendation Improvements

- Collaborative Filtering
- Hybrid Recommendation System
- User-Based Recommendations
- Deep Learning Embeddings

### Personalization

- User Profiles
- Watch History Tracking
- Favorite Movies

### Scalability

- Redis Caching
- PostgreSQL Storage
- Docker Containerization
- Kubernetes Deployment

---

# 📚 Learning Outcomes

This project helped develop practical experience in:

- Machine Learning Recommendation Systems
- Natural Language Processing
- TF-IDF Vectorization
- Cosine Similarity
- FastAPI Development
- REST API Design
- Streamlit Application Development
- Third-Party API Integration
- Model Serialization
- Full-Stack Machine Learning Deployment

---

# ⭐ Project Highlights

✅ Content-Based Recommendation Engine

✅ FastAPI Backend

✅ Streamlit Frontend

✅ TMDB API Integration

✅ Real Movie Posters & Metadata

✅ Production-Ready Architecture

✅ Serialized ML Models

✅ REST API Development

✅ End-to-End Full-Stack ML Project

---

## 📬 Contact

If you found this project useful, consider giving it a ⭐ on GitHub.

Contributions, suggestions, and feedback are always welcome.