# AI Movie Recommendation System

# Project Description
This project is an AI Movie Recommendation System built using Streamlit and powered by a Machine Learning model. It allows users to discover movies in two ways: by selecting a movie title or by choosing a genre/tag.

The recommendation engine uses TF-IDF Vectorization and Cosine Similarity to find movies similar to the selected title based on their combined tags (genres, keywords, cast, and director).

To enrich the user experience, the system also fetches movie posters, descriptions, ratings, release dates, trailers, and useful direct links, all through the TMDB API. Users can also save movies to a personalized Watchlist for quick access.

>Dataset is [HERE](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Theory of Recommendation Systems](#theory-of-recommendation-systems)
- [Installation](#installation)
- [Usage](#usage)
- [Dataset](#dataset)
- [Model](#model)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Overview

This project is an AI Movie Recommendation System built using Streamlit, Python, and a content-based machine learning model.
Users can explore movies in two ways:
	•  By selecting a movie title
	•  By choosing a genre or tag

The system analyzes movie metadata—genres, keywords, cast, and director—using TF-IDF Vectorization and Cosine Similarity, then recommends the top 10 most similar movies.
It also integrates with the TMDB API to display:
	•	Movie posters
	•	Overview
	•	Ratings & release info
	•	Genres & language
	•	Director details
	•	YouTube trailers
	•	Direct links (IMDB, Netflix, Prime Video, YouTube)

Users can also save movies to a persistent watchlist

## Features

Movie-based recommendations using cosine similarity
	•   Genre/Tag-based movie filtering
	•   TF-IDF NLP model for similarity
	•   HD posters fetched from TMDB API
	•   YouTube trailers embedded directly
	•   Full movie details (rating, overview, cast, director)
	•   Direct links to IMDB, TMDB, Google & streaming platforms
	•	Watchlist sidebar (add/remove movies)
	•	Premium UI with custom CSS & responsive layout

## Theory of Recommendation Systems

### What is a Recommendation System?

A recommendation system is a subclass of information filtering systems that seek to predict the rating or preference a user would give to an item. They are widely used in various applications like movie recommendations, product recommendations, and content recommendations.

### Types of Recommendation Systems

1. **Content-Based Filtering**: This method recommends items similar to those a user liked in the past. It relies on the attributes of the items and a profile of the user's preferences.

2. **Collaborative Filtering**: This method recommends items based on the preferences of similar users. It doesn't require the attributes of the items and instead focuses on user-item interactions.

3. **Hybrid Methods**: These methods combine content-based and collaborative filtering to provide more accurate recommendations.
   
    <img width="1200" height="557" alt="40537_2022_592_Fig1_HTML" src="https://github.com/user-attachments/assets/c94efcfa-f6fe-404f-be46-0266c924d066" />

### Cosine Similarity

In this project, we use cosine similarity to measure the similarity between movie titles. Cosine similarity is a metric used to measure how similar two vectors are. It is calculated as the cosine of the angle between two vectors projected in a multi-dimensional space. For movie recommendation, the vectors represent movie features, and the similarity score indicates how alike two movies are.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/movie-recommendation-system.git
    cd ai-movie-recommendation-system
    ```

2. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```
3. Add your TMDB API key:
   ```bash
    TMDB_API_KEY = "YOUR_API_KEY"
    ```
4. Run the Streamlit app:
   ```bash
    streamlit run app.py
    ```
## Usage

1. Run the Streamlit app:
    ```bash
    streamlit run app.py
    ```

2. Open your web browser and go to `http://localhost:8501`.

3. Select Recommendation Mode
	•   By Movie Name – AI recommends 10 similar movies
	•	By Genre – Filter movies by tag/genre

4. Explore movie details

    Click More About to view:
	    •	Poster
	    •	Overview
	    •	Ratings & genres
	    •	Trailer
	    •	Director info
	    •	Direct links to search platforms

5. Manage Watchlist
	•	Add movie to watchlist
	•	View watchlist in sidebar
	•	Remove items easily


## Dataset
The dataset used in this project contains detailed information about movies, including their titles, IDs, genres, keywords, cast, crew, and overviews. The raw data comes from the TMDB 5000 dataset and is preprocessed to generate a serialized file named movie_data.pkl, which includes:

   •	  The cleaned and preprocessed movies dataframe
  
   •	  The combined “tags” column used for NLP
  
   •	  The cosine similarity matrix for movie-to-movie comparison

The original dataset consists of two main CSV files:

  •	[tmdb_5000_movies.csv](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata/download?datasetVersionNumber=1)
   
   . [tmdb_5000_credits.csv](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata/download?datasetVersionNumber=1)

This processed dataset is used by the recommendation engine to compute cosine similarity between movies and generate the top recommended titles.


## Model

The recommendation engine uses a Content-Based Filtering approach. Each movie is converted into a text representation (tags) made from its genres, keywords, cast, and director.

These tags are transformed into numerical vectors using TF-IDF Vectorization, and movie similarity is calculated using Cosine Similarity.

The top 10 movies with the highest similarity scores are recommended to the user.
The processed movie data and similarity matrix are stored in `movie_data.pkl` for fast loading in the app.

## Results

The system successfully returns the top 10 closest matching movies for any selected title using cosine similarity. Movie posters, ratings, overviews, and other details are fetched live from the TMDB API, providing accurate and visually rich information. The application also includes trailer embedding and a watchlist feature, enhancing the user experience. Additionally, the genre-based search option offers a flexible way for users to explore movies based on their interests.
<br>
<br>
1. Home Page (Dashboard + Recommendations+Watchlist)
<br>
<br>
<br>
<img width="1465" height="827" alt="Screenshot 2025-11-21 at 5 27 21 PM" src="https://github.com/user-attachments/assets/32c7fc84-b5ca-4b3a-8e4e-1ef1ea473430" />
<br>
<br>
<br>
<br>
2. Movie Details Section
<br>
<br>
<br>
<img width="1470" height="652" alt="Screenshot 2025-11-21 at 5 27 56 PM" src="https://github.com/user-attachments/assets/9a896439-eb13-4d36-b047-ee32403ce2e8" />
<br>
<br>
<br>
3. Trailer + Direct Links Section
<br>
<br>
<br>
<img width="1465" height="470" alt="Screenshot 2025-11-21 at 5 28 08 PM" src="https://github.com/user-attachments/assets/6d3d3835-d35a-4665-9977-915c00e0c525" />


## Contributing

Contributions are welcome to improve this project. To contribute, simply fork the repository, create a new branch, make your changes, and submit a pull request. Future enhancements could include adding collaborative filtering, implementing a user login system, and introducing personalized recommendations based on user ratings.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
