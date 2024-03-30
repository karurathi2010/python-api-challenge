# python-api-challenge
## 1-WeatherPy:
In this activity,visualized the weather of over 500 cities of varying distances from the equator using the citipy Python library and OpenWeatherMap API.
* As the first step generated the list of cities using the citipy Library.
* For showing  the relationship between weather variables and Latitude used the OpenWeatherMap API to retrieve weather data from the cities list generated in the first step.
* Used for loop to loop through all the cities in the list to fetch weather data.
* Used 'try - except' method to run API request for each of the cities and fetch the latitude, longitude, max temp, humidity, cloudiness, wind speed, country, and date information for each city.
* Append the city informations into 'city_data' list.
* Converted the cities weather data into a Pandas DataFrame as 'city_data_df'.
* Converted the temperature column from Kelvin to Celsious in the 'city_data_df'.
* Created a 'output_data' directory and exported the 'city_data' into a csv for further use.
* Visualized the following scatter plots using 'city_data_df':
    * Latitude Vs. Temperature.
    * Latitude Vs. Humidity.
    * Latitude Vs. Cloudiness.
    * Latitude vs. Wind Speed.
* Next computed linear regression for each of the above relationship,so that as first step defined a function to create Linear Regression plots.
* Created two differnt dataframes from 'city_data_df':
    * 'northern_hemi_df' for Northern Hemisphere data with condition Latitude >= 0.
    * 'southern_hemi_df' for Southern Hemisphere data with condition Latitude < 0.
* Using the above dataframes the following visualizations are generated:
   * Temperature vs. Latitude Linear Regression Plot for Northern Hemisphere and Southern Hemisphere.
   * Humidity vs. Latitude Linear Regression Plot for Northern Hemisphere and Southern Hemisphere.
   * Cloudiness vs. Latitude Linear Regression Plot for Northern Hemisphere and Southern Hemisphere.
   * Wind Speed vs. Latitude Linear Regression Plot for Northern Hemisphere and Southern Hemisphere.

## 2-VacationPy:
This activity is the continuation of the WeatherPy activity.

* Here the geoViews Python library, and the Geoapify API were used to visualize several maps.
* As first step the 'cities.csv' file from the WeatherPy activity is loaded as the source data.
* Greated a map that displays a point for every city in the 'city_data_df'. The size of the point is set as the humidity in each city.
* Next narrowed down the 'city_data_df' to find the ideal weather condition for vacation,for that the 'city_data_df' is filtered using the following conditions and named as 'narrow_df':
    * A max temperature lower than 27 degrees but higher than 21.
    * Wind speed less than 4.5 m/s.
    * Zero cloudiness.
* Next used the Pandas copy function to create DataFrame called 'hotel_df' to store the city, country, coordinates, and humidity.
* Added an empty column, "Hotel Name," to the DataFrame for storing the hotel found using the Geoapify API.
* Used the Geoapify API to find the first hotel located within 10,000 metres of the  coordinates for each city.For the following steps are performed:
    * Set parameters radious,api_key,filter,bias and category.
    * Used for loop to iterate through the 'hotel_df' dataframe and get latitude, longitude.
    * Set base url and made API request using the params dictionary.
    * Converted the API response to JSON format and fetched the first hotel from the results and store the name in the 'hotel_df' using the 'try-except' method.
* Visualized a map using 'hotel_df' with hotel name and the country as additional information in the hover message for each city.


 




