TOOLS USED:

1.pandas
2.numpy
3.sklearn
4.sklearn_pandas
5.Geopy - Nominatim
6.tqdm

Final Model: LGBM Regressor

	
WORKFLOW:

1. General analysis of data was done with pandas

2. Column:'amenities' was split into 19 different categories using a custom 'amenitiesSplit' function.
   These were appended to the DF

3. Train and Test datasets were combined for easier manipulation, cleaning and feature engineering.

4. Column:'Latitude','Longitude' were combined to form a Column:'Coordinate'

5. Column:'Coordinate' was passed to Geopy - Nominatim Module to fetch addresses for each co-ordinate through its API.

6. Addresses were stored in a DataFrame:'locationDF' and was parsed to get 'State', 'City', 'Zone'. 
   Cleaning was done with these lists and was appended to DF.

7. Date was parsed

8. Nan Values were imputed using Categorical Imputer

9. Visualizations (Distribution Plots, Histograms, Heatmaps) were done wrt various features to understand them better.

10.Data types of features were changed to better suitability.

11.Column:'Amenities_Count' was created using the sum of values of sub amenities features.

12.Categorical Variables were encoded using Pandas:'get_dummies'.

13.Data was split into Train and Test

14.CatBoost, LightGBM, XGboost were fitted to the data and RMSE was chosen as the metric

15.Hyperparameters were chosen for LightGBM model and was retrained with set iterations along with early stopping round.
   Best Iteration num was saved.

16.Accuracy: 75% approx

17.Data was not scaled.

18.Submission CSV was created using model inference from test set

