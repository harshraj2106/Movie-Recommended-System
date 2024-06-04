# Movie Recommender System

This is a Movie Recommender System built with Streamlit. The application suggests movies based on a selected movie from a dropdown menu. It leverages a precomputed similarity matrix to recommend movies that are similar to the selected movie.

## Features

- Select a movie from a dropdown menu.
- Get recommendations for similar movies.
- Display movie posters along with recommendations.

## Model Training

The similarity matrix is created using the following steps:

1. **Extract Features**:
   Using `CountVectorizer` from `sklearn` to extract features from the movie tags.

    ```python
    from sklearn.feature_extraction.text import CountVectorizer
    cv = CountVectorizer(max_features=5000, stop_words='english')
    vector = cv.fit_transform(new_df['tags']).toarray()
    ```

2. **Compute Similarity**:
   Using `cosine_similarity` from `sklearn` to compute the similarity matrix.

    ```python
    from sklearn.metrics.pairwise import cosine_similarity
    similarity = cosine_similarity(vector)
    ```


