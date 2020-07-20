# Recommendation Engine Using Million Playlist Data from Spotify
Project authors: Jamilla Akhund-Zade, Alpha Sanneh, Denise Yoon, and Bella Gu

Project website (updated December 2019): https://sites.google.com/view/songrecommender/

## Project Scope

Using Spotify's Million Playlist Dataset (MPD), found at [https://recsys-challenge.spotify.com/](https://www.google.com/url?q=https%3A%2F%2Frecsys-challenge.spotify.com%2F&sa=D&sntz=1&usg=AFQjCNEa0ZkVuNiBmABpDCwgye04hHehvw), we set out to build a model that could recommend relevant songs based on the songs already in a playlist. We chose to build our model using **matrix factorization** on a sparse playlist-by-song matrix in order to learn the latent variables that will allow us to make predictions as to whether a particular song belongs to a playlist [1,2,3]. 

## Notebooks

**eda-sqlite-db**: Exploratory Data Analysis (EDA) on Spotify's MPD. An SQLite database was built locally in order to facilitate querying the 12GB dataset. 

**create-sparse-matrix**: Creating sparse matrix for use with our matrix factorization model. Includes a function to control the sparsity of the matrix by filtering out rarely featured songs and short playlists. Adapted to use SQLite database. 

**FinalProject31**: Original collaborative notebook for the matrix factorization recommendation system. Contains EDA, sparse matrix creation, train-test split, matrix factorization and hyperparameter optimization, and recommendations. 

**audio_V2**: Extracting song features from Spotify API for small portion of songs in the MPD in order to perform EDA for a potential cosine similarity model (using item similarity in high dimensional space). 

## In Progress

1. Improve efficiency of current hyperparameter grid search - employ Bayesian Optimization [4].
2. Evaluate effect of matrix sparsity on recommendation performance.
3. Improve flexibility of recommendation engine - be able to generate recommendations for novel playlists/users. 

## References

1. [https://www.ethanrosenthal.com/2016/10/19/implicit-mf-part-1/](https://www.google.com/url?q=https%3A%2F%2Fwww.ethanrosenthal.com%2F2016%2F10%2F19%2Fimplicit-mf-part-1%2F&sa=D&sntz=1&usg=AFQjCNF7K6RQ4YcqBfZjen-udbbSBqSnYg) 

2. [https://jessesw.com/Rec-System/](https://www.google.com/url?q=https%3A%2F%2Fjessesw.com%2FRec-System%2F&sa=D&sntz=1&usg=AFQjCNGvkdJMiBQrcIrIPSoil-urbT8caQ) 
3. https://github.com/benfred/implicit
4. https://distill.pub/2020/bayesian-optimization/