# Movie Recommendation System

This is a movie recommendation system based on the **MovieLens** dataset. Two approaches are used for recommending movies:

## Approaches

### 1. Popularity-Based Approach
In this approach, a **weighted rating** is calculated using the **Bayesian ratings formula**. The weighted rating is used to recommend movies based on their popularity.

To calculate the **weighted rating** (WR) for movies in the popularity-based approach, the following steps are taken:

### Variables:
- **R**: Average rating of a movie.
- **v**: Number of ratings the movie has received.
- **C**: Mean rating across all movies.
- **m**: Minimum number of ratings required for a movie to be considered.

### Bayesian Weighted Rating Formula:
The weighted rating (WR) is calculated as:

$$
WR = \frac{v}{v + m} R + \frac{m}{v + m} C
$$

Where:
- **R** is the movie's average rating.
- **v** is the number of ratings for the movie.
- **C** is the overall average rating of all movies.
- **m** is the minimum number of ratings required.

### Steps:
1. **Determine the Minimum Number of Ratings (m)**:
   - Set **m** based on the distribution of ratings, such as the 75th percentile of the number of ratings.

2. **Calculate the Overall Mean Rating (C)**:
   - Compute **C** by taking the mean of all movie ratings in the dataset.


### 2. Content-Based Approach
In the content-based approach, movies are recommended based on their **genre** and **release year**. This method suggests movies that are similar to the ones the user has already interacted with, based on these attributes.

The content-based approach uses the **genre** and **release year** of movies to recommend similar movies. The process is divided into two main steps:

### Step 1: Genre Analysis
1. **Extract Unique Genres**:
   - All genres in the dataset were analyzed, and a unique list of genres was created.

2. **Generate Genre Vectors**:
   - For each movie, a vector was created based on the presence or absence of each genre.

3. **Cosine Similarity**:
   - The **cosine similarity** metric was used to measure the similarity between genre vectors of movies.

### Step 2: Release Year Analysis
1. **Scale the Year**:
   - The **release year** of movies was scaled using a **MinMax scaler** to bring the values into a normalized range.

2. **Calculate Absolute Distance**:
   - The **absolute distance** between the release years of two movies was computed.

### Hybrid Distance
1. **Combine Genre and Year Distances**:
   - The distances calculated for genre and release year were **weighted** to form a **hybrid distance**.

This hybrid distance was then used to recommend movies based on both genre and release year similarities.


## Dataset
The system is built using the **MovieLens** dataset, which provides a collection of movie ratings and metadata.
