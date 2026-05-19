# **Minneapolis Housing Price Prediction**







##### Problem Statement:



In order for the homebuyer to have a better idea of housing costs, a model could be used to predict the cost, and then the home buyer could compare to the expected price given by the model.



##### Goal:



Build a Model that can be used to determine if a property is over/under valued





##### Project Description:



After acquiring housing price data from Kaggle/Redfin for the Minneapolis/St.Paul area, the data was cleaned, and an EDA analysis was conducted. The EDA showed a correlation between the price and Beds, Baths, and square feet showing that the data is usable for modeling. Next, for all models, the data was split (80/20; training/test). All models were optimized for the mean absolute error (MAE) across the entire price range, and then the optimized models were compared using the MAE and the mean absolute percent error (MAPE) for different price ranges. Different models worked better for different price ranges, but the most consistent was the Simple 3-Layer Neural Network. Below you can find the data, and the information for the optimized models.





##### Model Summary and Findings:





A total of 8 different models were optimized and compared. First the best fit linear regression model was used as a baseline to compare the other models to. The models were all optimized to MAE, and were compared at different price ranges using MAPE.





|Model|R^2|MAE|Low Price (<$300K) MAPE|Med Price ($300K-$500K) MAPE|Med-High Price ($500K-$1M) MAPE|High Price (>$1M) MAPE|
|-|-|-|-|-|-|-|
|# of Samples in test set|135|135|61|49|20|5|
|Linear - Best Fit|0.66|$98,053|30.51%|21.40%|24.81%|26.45%|
|Linear - Ridge|0.54|$96,896|33.67%|20.43%|19.75%|32.87%|
|Linear - Lasso|0.67|$99,996|32.78%|22.14%|23.82%|26.83%|
|Random Forest|0.66|$88,425|28.62%|16.90%|24.28%|30.04%|
|XGBoost|0.68|$82,132|27.24%|15.57%|21.00%|30.78%|
|Neural Network|0.70|$80,114|22.7%|18.08%|22.86%|23.51%|







Random Forest best parameters: {'n\_estimators': np.int64(1900), 'min\_samples\_split': np.int64(2), 'min\_samples\_leaf': np.int64(1), 'max\_features': 'log2', 'max\_depth': np.int64(22)}



XGBoost best parameters: {'subsample': 0.9, 'n\_estimators': 1000, 'max\_depth': 5, 'learning\_rate': 0.01, 'gamma': 1.5, 'colsample\_bytree': 0.6}





The simple neural network model consisted of 3 layers.



1. Input Layer: linear transformation followed by ReLu fit, takes the 30+ features and then expands them to 64 neurons
2. Hidden layer: Linear transformation, from 64 neurons to 32 neurons (training involved a drop rate of 0.2)
3. Output layer: Linear transformation, from 32 neurons to 1 neurons (training involved a drop rate of 0.1)



The loss function was focused on Mean Squared Error(MSE)

Optimizer was Adam



##### 

##### Data Source:

https://www.kaggle.com/datasets/soulaimanebenayad/united-states-redfin-housing-market-csv



##### Jupyter Notebook for Models:

MN\_Housing\_Modeling.ipynb

