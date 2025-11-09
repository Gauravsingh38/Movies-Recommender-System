# Movies Recommender System

**Live Web App:** [Deployed Link](https://gauravmrs-47497d4fa554.herokuapp.com/)

This web application recommends movies based on user preferences and performs sentiment analysis on user reviews. It uses **Content-Based Filtering** along with **NLP techniques** to provide personalized suggestions.

Movie metadata (title, genre, runtime, rating, poster, etc.) is fetched via the **TMDB API** using the movie’s IMDB ID. User reviews are scraped from **IMDB** using BeautifulSoup and analyzed for sentiment.

---

## Directory Structure
```
Movie_Recommendation_System/
├── static/
│ ├── autocomplete.js        # Autocomplete feature for search
│ ├── recommended.js         # Fetch and render recommendations
│ ├── style.css              # Frontend styles
│ ├── loader.gif             # Loading animation
│ └── image.jpg              # UI assets
├── templates/
│ ├── home.html              # Homepage template
│ └── recommended.html       # Recommendation results page
├── data/
│ ├── main_data.csv          # Preprocessed dataset for recommendations
│ ├── finaldata.csv          # Feature-engineered dataset
│ ├── data1.csv              # Additional movie data
│ └── movies_metadata.csv    # Raw movie metadata
├── models/
│ ├── NLP_model.pkl          # Sentiment analysis model
│ └── transformer.pkl        # TF-IDF vectorizer
├── main.py                  # Flask application
├── Procfile                 # Heroku deployment config
├── requirements.txt         # Python dependencies
└── .gitignore               # Git ignore file
```


---

## Installation and Setup
1. Clone the repository:
```bash
git clone https://github.com/your-username/Movie_Recommendation_System.git
```

3. Navigate to the project directory:
```bash
cd Movie_Recommendation_System
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Run the application:
```bash
python main.py
```

5. Open your web browser and go to:
```
http://localhost:5000
```
## Features

- **Movie Recommendations**: Get personalized suggestions based on movie similarity.
- **Autocomplete Search**: Real-time suggestions while typing a movie name.
- **Sentiment Analysis**: Classifies IMDB reviews as Good or Bad.
- **Interactive UI**: Responsive and user-friendly interface for smooth navigation.
- **Preprocessed Data**: Datasets and models are preloaded for faster performance.

## System Architecture

### High-Level Flow
```
Frontend (HTML/CSS/JS) → Flask Web App → Recommendation Engine
↑ ↓
TMDB API Integration NLP Model (Sentiment Analysis)
↑ ↓
IMDB Scraping for Reviews
```


### Data Flow

1. User searches a movie using the autocomplete feature.  
2. TMDB API returns movie metadata (title, genre, poster, runtime, rating, etc.).  
3. The recommendation engine computes similar movies using cosine similarity.  
4. IMDB reviews are scraped and analyzed using NLP for sentiment (Good or Bad).  
5. Results, including recommended movies and sentiment analysis, are displayed dynamically on the frontend.

![logo](https://github.com/Gauravsingh38/Movies-Recommender-System/blob/main/static/Screenshot%20(259).png)
![logo](https://github.com/Gauravsingh38/Movies-Recommender-System/blob/main/static/Screenshot%20(260).png)
![logo](https://github.com/Gauravsingh38/Movies-Recommender-System/blob/main/static/Screenshot%20(261).png)
![logo](https://github.com/Gauravsingh38/Movies-Recommender-System/blob/main/static/Screenshot%20(262).png)


## Algorithm Deep Dive

### Content-Based Filtering
- Combines multiple features of a movie (genres, keywords, cast, director, overview) into a single text representation.  
- Converts the text representation into vectors using **CountVectorizer**.  
- Computes **cosine similarity** between movies to rank and recommend the most similar ones.

### Sentiment Analysis
- Applies **TF-IDF vectorization** to IMDB reviews to transform text into numerical features.  
- Uses a **pre-trained NLP model** for binary classification to predict whether a review is **Good** or **Bad**.  
- Allows users to gauge overall sentiment of a movie from real user reviews.

## Performance & Optimization

- **Response Time:** < 3 seconds for recommendations and sentiment analysis  
- **Recommendation Dataset:** ~45,000 movies  
- **Sentiment Model Accuracy:** ~85%  

### Optimizations Implemented
- **Precomputed Similarity Matrices:** Cosine similarity is calculated in advance for faster recommendations.  
- **Pickled Models:** NLP models and vectorizers are preloaded to reduce computation time.  
- **Asynchronous JavaScript (AJAX):** Frontend fetches data without reloading pages.  
- **Caching Frequent Queries:** Frequently searched movies are cached to improve response time.

## Deployment

- **Platform:** Heroku  
- **Runtime:** Python 3.9  
- **Dependencies:** Listed in `requirements.txt`  
- **Procfile:** 
```text
web: python main.py
```
- **Security:** HTTPS enabled and CORS handled by default

## Future Enhancements

### Short-Term (1-3 months)
- User authentication and personalized profiles  
- Multi-class sentiment analysis (e.g., Positive, Neutral, Negative)  
- Further performance optimizations using databases and caching  

### Medium-Term (3-6 months)
- Hybrid recommendation system combining content-based and collaborative filtering  
- Advanced analytics dashboards and a companion mobile application  

### Long-Term (6+ months)
- Deep learning-based recommendation models for improved accuracy  
- Real-time personalization based on user behavior  
- Social features, voice/image-based search, and AR/VR integration

## Key Technical Learnings

- **Full-Stack Development:** Integrating frontend, backend, APIs, and machine learning models.  
- **External API Handling:** Efficiently managing TMDB API requests and rate limits.  
- **Web Scraping:** Ensuring reliability while considering legal and ethical compliance.  
- **Scalability Strategies:** Implementing caching, database optimization, and microservices for improved performance.  
- **NLP Integration:** Applying natural language processing for sentiment analysis on IMDB reviews.

### Steps to Build the Application

1. **Data Collection & Extraction:** Gather and clean the movie dataset.  
2. **Exploratory Data Analysis (EDA):** Analyze data patterns, distributions, and key statistics.  
3. **Feature Engineering:** Create meaningful features for recommendation and sentiment analysis.  
4. **Model Development & Tuning:** Build content-based recommendation and sentiment analysis models; optimize for performance.  
5. **Flask API Development:** Wrap models in a Flask API to handle frontend requests.  
6. **Version Control:** Push the project code to GitHub.  
7. **Heroku Integration:** Connect the GitHub repository to your Heroku account.  
8. **Deployment:** Deploy the web application and ensure it runs smoothly on the live server.



## References

- Pazzani, M., & Billsus, D. (2007). *Content-Based Recommendation Systems*.  
- Manning, C., Raghavan, P., & Schütze, H. (2008). *Introduction to Information Retrieval*.  
- **Flask Documentation:** [https://flask.palletsprojects.com/](https://flask.palletsprojects.com/)  
- **TMDB API Documentation:** [https://developers.themoviedb.org/](https://developers.themoviedb.org/)  
- **Scikit-learn Documentation:** [https://scikit-learn.org/](https://scikit-learn.org/)


# Movies Recommender System

**Live Web App:** [https://gauravmrs-47497d4fa554.herokuapp.com](https://gauravmrs-47497d4fa554.herokuapp.com/)  
**Author:** Gaurav Singh  
**GitHub Repository:** [Link to Repository](https://github.com/Gauravsingh38/movies-recommender-system)







