🎬 Movie Recommendation System – Baseline Recommender Using Content Similarity

A complete walkthrough of building a simple, effective movie recommender using content-based filtering.

📝 Project Overview

Recommender systems power modern platforms like Netflix, YouTube, Amazon, Spotify, and more.
This project builds a Content-Based Movie Recommendation System that suggests movies similar to a user-selected title based on metadata such as:

Genres

Keywords

Overview

Cast

Crew (e.g., directors, writers)

The notebook explains the fundamentals of recommendation engines and implements a full working baseline model.

📚 1. Types of Recommender Systems (Concept Overview)

The notebook introduces the three major recommendation approaches:

1. Content-Based Filtering 🎯

Recommends items similar to what the user already likes using item features.
(This is the approach implemented in the project.)

2. Collaborative Filtering 👥

Uses user–item interactions to find patterns among similar users.

3. Hybrid Systems ⚡

Combines both methods.
(Used by Netflix, Amazon, YouTube)

📂 2. Dataset Summary

The project uses the TMDB Movie Dataset, typically containing:

Main files:

movies.csv

credits.csv

Key fields used:

Title

Overview

Genres

Keywords

Cast

Crew (for director extraction)

These features are used to create a unified “movie profile” for similarity comparison.

🧹 3. Data Cleaning & Preparation
✔ Merge datasets

movies and credits datasets are merged on common movie identifiers.

✔ Extracting Directors & Main Cast

Grab director from the crew

Extract top 3 cast members

Limit keywords for consistency

✔ Text Normalization

Remove spaces

Convert to lowercase

Remove duplicates

✔ Handle Missing Values

Where movie descriptions or metadata were missing, appropriate cleanup was performed.

🧩 4. Feature Engineering

The project constructs a "tags" feature — a single text field combining:

Genres

Keywords

Overview

Cast

Director

Example:
"action adventure space tom_hardy christopher_nolan mind_bending thriller"

These enriched tags help the similarity algorithm capture movie similarity more accurately.

🔠 5. Text Vectorization

To convert textual movie metadata into numerical vectors, the notebook uses:

TF-IDF / CountVectorizer

Converts tags into token vectors

Captures important movie descriptors

Cosine Similarity

Measures similarity between two movie vectors:

1 → exactly similar

0 → no similarity

This forms the basis of movie recommendations.

🤖 6. Recommendation Function

The notebook builds a custom function:

recommend(movie_title)


This function:

Finds the target movie

Retrieves its cosine similarity scores

Sorts and selects the top 5 similar movies

Returns highly relevant recommendations

Example output:

Recommendations for "Avatar":
- John Carter
- Guardians of the Galaxy
- Star Trek
- The Chronicles of Riddick
- The Fifth Element

📊 7. Exploratory Insights (Conceptual)

The notebook also explains:

Why content-based filtering is stable

How metadata impacts recommendations

Limitations:

Doesn’t learn user behavior

Limited personalization

Depends heavily on text quality

⚙ 8. Model Pipeline Summary

✔ Load and merge datasets
✔ Clean and preprocess metadata
✔ Create tags feature
✔ Convert text to vectors
✔ Compute similarity matrix
✔ Build recommendation engine
✔ Test with multiple movie titles

A full end-to-end baseline recommender is ready for deployment.

🎯 9. Project Output

The final deliverable is a functioning content-based movie recommendations,

Collaborative filtering (surprise library)

