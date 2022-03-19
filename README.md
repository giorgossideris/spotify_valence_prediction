# spotify_valence_prediction

## Purpose
* One of the metrics that Spotify uses to characterise its songs, is valence. Valence is used to measure how happy or sad a particular song is.
  * The calculation of valence was developed by [The Echo Nest](https://en.wikipedia.org/wiki/The_Echo_Nest), which was acquired by Spotify in 2014.
  * Though the valence of each song is publicly available, there is a mystery that surrounds its calculation. Some information can be found [here](https://web.archive.org/web/20170422195736/http://blog.echonest.com/post/66097438564/plotting-musics-emotional-valence-1950-2013) but not something very specific.
* In this project we will use Machine Learning methods to create a predictive model for the valence calculation.

## Tools and Packages
The analysis was executed on [Jupyter](https://jupyter.org/) *(Jupyter Notebook 6.4.4 and Python 3.9.0 will work for sure)*. 

Additional packages required for the project to run are:
  * [pandas](https://pandas.pydata.org/)
  * [matplotlib](https://matplotlib.org/)
  * [NumPy](https://www.numpy.org/)
  * [Spotipy](https://spotipy.readthedocs.io/en/2.19.0/)
  * [statsmodels](https://www.statsmodels.org/stable/index.html)
  * [scikit-learn](https://scikit-learn.org/stable/)
  * [XGBoost](https://xgboost.readthedocs.io/en/stable/)
  * [LightGBM](https://lightgbm.readthedocs.io/en/latest/)

All the packages above can be installed using the `pip install` command-line command.

## Data
Two data sources were used:
  * [Spotify's Web API](https://developer.spotify.com/documentation/web-api/): Spotify offers numerous metrics for every song through its API. Specifically, [Get Tracks' Audio Features](https://developer.spotify.com/documentation/web-api/reference/#/operations/get-several-audio-features) and [Get Track's Audio Analysis](https://developer.spotify.com/documentation/web-api/reference/#/operations/get-audio-analysis) operations were used.
  * [Spotify-Data 1921-2020](https://www.kaggle.com/ektanegi/spotifydata-19212020) from [Kaggle](https://www.kaggle.com/). This dataset was used to get the Spotify ids from many songs.  
  
***Important Note**: Some files that contain data, obtained from the API of Spotify, were too large to by uploaded. If a user wants to access this files without executing the corresponding code, please contact the author.*

## Notebooks
This repository contains 4 notebooks, and each of them has its own purpose. Specifically:
  * **data_preparation**: contains the code used to collect and prepare the data that will be used by the other notebooks.
  * **statistics**: contains some statistical analyses, that were done in order to understand better the correlation between numerous features and valence.
  * **non_nn_predictive**: contains the development of various predictive models (not including neural networks).
  * **nn_predictive**: contains the development of neural network models, for valence prediction.

## Results
The best results were achieved by the **Neural Network built around all the data collected and metadata created**. Specifically, its *Mean Absolute Error* on the test set was **0.0846**.
