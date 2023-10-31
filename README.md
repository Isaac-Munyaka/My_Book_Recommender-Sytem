# My_Book_Recommender-Sytem

 ##  Data Understanding

The Dataset used was from Kaggle,(https://www.kaggle.com/datasets/ruchi798/bookcrossing-dataset?select=Books+Data+with+Category+Language+and+Summary) 
extracted in csv form and excel form (both in text form) and containing important information with regards to Book Summary and Category which were 
the primary basis for perfoming Natural Language Processing, inorder to recommend similar books. The Dataset contains 1,031,175 books. 
I used the Csv (Comma Separated Values) form.

## Feature Engineering
I) Data Vectorization

Text data in the "new_book_df" dataframe is transformed into numerical vectors to make it suitable for mathematical
operations.
Techniques I used for vectorization are TF-IDF 
(Term Frequency-Inverse Document Frequency) Vectorization

### Term Frequency
This will measure the frequency of terms (tokens/words). Words that appear frequently within single document but rare acrosss the corpus are assigned higher scores. 
This will help to capture the uniqueness of terms 

### IDF
IDF measures the importance of a term across a collection of documents (corpus). IDF has an inverse relationship with the number of documents containing the term. 
If a term appears in many documents (high document frequency), its IDF value will be lower because it is considered less important for distinguishing documents. 
The primary purpose of IDF is to identify terms that are discriminative or rare in the corpus, giving them higher weights.

###  Dimensionality Reduction

Since book data is high dimensional, It will be necessary for me to reduce the number of features to avoid computational complexities when getting the 
cosine similarity.
Important information will be preserved. Otherwise; attempting without reducing the number of documents will return "Memory Error"

 #### Latent Semantic Analysis
LSA for analysing r/ship between words and undelying patterns of word co-occurence in the documents, while retrieving important information.
I used Truncated Singular Value Decomposition (which is the mathematical basis for LSA)

###  Cosine Similarity:

After vectorization, I have numerical representations of text documents. These vectors can be considered as points in a high-dimensional space.
Cosine similarity measures the cosine of the angle between two vectors. The cosine of 0 degrees is 1, and the cosine of 90 degrees is 0. 
In other words, if two vectors have a cosine similarity of 1, they point in the same direction (high similarity), and if the cosine similarity is 0, 
they are orthogonal (no similarity).
In the context of NLP, cosine similarity calculates how similar two text documents are based on their vector representations. 
If the vectors point in a similar direction, they have a higher cosine similarity, indicating that the documents are more similar.

### The model then goes ahead and recommends 5 similar books based on cosine similarity
