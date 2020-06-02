# Capital-BikeShare
Perform Linear Regression Analysis to research the usage of Capital Bikeshare usage

Introduction:

The purpose of this project is focusing on analyzing the usage of Capital Bikeshare in the Washington District of Columbia Area. By doing this analysis, we want to build a model to predict the bikes daily usage so that we can provide allocation suggestions for the Capital Bikeshare.

About the datasets:

The research dataset was downloaded from UCL Machine Learning Repository (https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset). The original data comes from Capital Bikeshare Official website(http://capitalbikeshare.com/system-data) It recorded the usage data of the Capital Bikeshare from 2011 to 2012. This dataset contains 17 variables and 731 records, they are:

instant: record index.
dteday : date
season : season (1:winter, 2:spring, 3:summer, 4:fall)
yr : year (0: 2011, 1:2012)
mnth : month ( 1 to 12)
hr : hour (0 to 23)
holiday : weather day is holiday or not (extracted from [Web Link])
weekday : day of the week
workingday : if day is neither weekend nor holiday is 1, otherwise is 0.
weathersit :
1: Clear, Few clouds, Partly cloudy, Partly cloudy
2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
temp : Normalized temperature in Celsius. The values are derived via (t-t_min)/(t_max-t_min), t_min=-8, t_max=+39 (only in hourly scale)
atemp: Normalized feeling temperature in Celsius. The values are derived via (t-t_min)/(t_max-t_min), t_min=-16, t_max=+50 (only in hourly scale)
hum: Normalized humidity. The values are divided to 100 (max)
windspeed: Normalized wind speed. The values are divided to 67 (max)
casual: count of casual users
registered: count of registered users
cnt: count of total rental bikes including both casual and registered

Our research procedures:

Considering that there are only 731 data records (which means the volume of data is small), we chose the linear regression model in this research. Our steps in this research are:
1.	Do the variate analysis to check the relationship between different variables
2.	Select appropriate features based on variables’ characteristics.
3.	Build up linear regression model
4.	Analyze model error and tune the model

Research finding (Base on the data we acquired):

1.	The seasons of Summer and Fall usually have higher bike users
2.	The amount of bike users will increase while temperature (or feeling temperature) is increasing. However, while temperature (or feeling temperature) reach at a certain level, the amount of bike users will decrease (temp: 24℃ or atemp: 23.6℃)
3.	The amount of bike users will decrease while wind speed is decreasing
4.	The amount of bike users will increase while the humidity is increasing. However, it will decrease when the humidity reaches 62
5.	People prefer riding bikes when the weather is good (which means the visibility is good)
6.	More detail please check the code 

About the model:

1.	We select 13 features while building the linear regression. Some of the features do not exist in the original data (For example: weathersit_is_2, windspeed_2…) We create (or reorganize) them because we want to make them has strong linear relationship with the dependable variable
2.	The predict error is around [-3144, 3315]
3.	The parameter for each feature is:
Atemp:              4631.576311
atemp_0.2:           5267.658280
atemp_0.6:        -17563.722390
atemp_0.7:         -3644.536063
holiday:            -577.083874
hum:                 -745.767161
hum_0.7:            -3928.056170
weathersit_is_2:     -417.751401
weathersit_is_3:    -1272.510040
windspeed:          -2349.674895
windspeed_0.3:      -7157.522811
workingday:            74.151903
yr:                  1946.245367
4.	More details please check the code
