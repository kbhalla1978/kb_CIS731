### kb_CIS731
### PTDSA_repository

# DATA PREPARATION 1
Data for each year starting from 2012 - 2023 was stored in .xlsx files. Data for each month was stored in the subsheets of each yearly .xlsx file. Since, the original data was a 15 minute interval data, therefore each day had 96 records (represented as colums). The rows represented days. Since there were 9 sources including Coal, Gas, Gas-CC, Nuclear, Hydro, Wind, Solar, Biomass, and Other, this required a given day of a month requiring 9 rows representing 9 different sources. Therefore, the number of rows would be 9 * (number of days in a month). This raw data for each month was transformed and reorganized into a time series format with 9 sources being the columns and the sequential set of 15 minute interval records for each day of the month representing the rows. This data was saved on the local machine.

# DATA PREPARATION 2
The data for all the years (2012 - 2023) was stored in separate folders. Within the year folder, each month data had a separate folder. Now the data organization task was to concatenate all the months of a given year in a sequential fashion and then concatenate all the years in a sequential fashion. This task was accomplished and further this 15 minute interval time series data was converted into an hourly data set from 2012 - 2023 and saved on the local machine as hourly_time_series.csv.

# PLOTS
Line graph plots/charts were created which shed light on the evolutionary behavior of different series. Hourly data was plotted for the sources for 2012, 2017, and 2023. Further, the hourly data was transformed or converted to a daily data and another plot of daily values was created for the entire dataset. In addition, the average hourly, average weekly, average monthly, and total annual values of power produced in mega watt hours (MWHs) from different sources were also created. To have a more refined and granular understanding of the hourly evolution for two selected months of January and August, another plot was created, which exhibited the growth and emergence of the series, their seasonal and cyclic behavior, the trend component including the level and the slope for the years 2012, 2017, and 2023.

# LSTM version 1
A long short term memory neural network model was run by rendering a specified value for each input parameter (hyperparameters). These parameters included number of layers, number of neurons, learning rate, patience, number of epochs, batch size, drop out rate (regularization), timesteps or the sequence length. Firstly, a five fold cross validation was done using different training and validation sets which were 2012 - 2017 (training) and 2018 (validation), 2012 - 2018 (training) and 2019 (validation), ..., 2012 - 2021 (training) and 2022 (validation). Then the final training and testing was done on 2012 - 2022 and 2023 respectively. Additionally, RMSE was calculated for each stage of cross validation and loss function plot was created. Even the residual plot was created. For the final training and testing, measures like MAE and R square were also generated along with the RMSE. 

# LSTM version 2
Another LSTM model was run by changing the specifications of the hyperparameters so as to control for any overfitting or underfitting problems. The new parameter specifications yielded a better model with a smaller RMSE.
