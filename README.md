# Rainfall Prediction

Predicts whether it'll rain on a given day, using a Random Forest classifier tuned with grid search.

## How it works

Data has daily weather readings like pressure, temperature, dew point, humidity, cloud cover, sunshine, wind direction and speed. Dropped maxtemp, temparature, and mintemp after noticing they were highly correlated with each other and adding little on their own. The dataset was imbalanced (way more rainy days than dry ones), so I downsampled the majority class to balance it out before training.

Ran GridSearchCV over number of trees, max depth, and split/leaf parameters to find the best Random Forest setup, then evaluated on a held-out test set.

## Results

74.5% accuracy on the test set, with precision and recall both sitting around 0.72–0.78 for each class.

## Dataset

`data/Rainfall.csv` is included in this repo originally from Kaggle's [Playground Series rainfall competition](https://www.kaggle.com/competitions/playground-series-s5e3/data).

## Running it

Needs pandas, numpy, scikit-learn, matplotlib, seaborn. 
