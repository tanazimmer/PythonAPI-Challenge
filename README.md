# Python API Homework - What's the Weather Like?

## Primary Coding Language and skills: Python in Jupyter Notebook, API calls, Matplotlib

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. So let's take what you've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Now, we know what you may be thinking: _"Duh. It gets hotter..."_

But, if pressed, how would you **prove** it?

![Equator](Images/equatorsign.png)

### Part I - WeatherPy
####Challenge:
Create a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. Utilize [simple Python library](https://pypi.python.org/pypi/citipy) and the [OpenWeatherMap API](https://openweathermap.org/api).

Your first requirement is to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude

![lat v temp](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_maxtemp.png)
* Humidity (%) vs. Latitude

![lat v hum](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_humidity.png)
* Cloudiness (%) vs. Latitude

![lat v cloudiness](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_cloudiness.png)
* Wind Speed (mph) vs. Latitude

![lat v wind](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_wind.png)

After each plot add a sentence or too explaining what the code is and analyzing.

Your second requirement is to run linear regression on each relationship, only this time separating them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude

![lat v ntemp](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_temp_northern.png)
* Southern Hemisphere - Temperature (F) vs. Latitude

![lat v stemp](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_temp_southern.png)
* Northern Hemisphere - Humidity (%) vs. Latitude

![lat v nhum](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_hum_northern.png)
* Southern Hemisphere - Humidity (%) vs. Latitude

![lat v shum](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_hum_southern.png)
* Northern Hemisphere - Cloudiness (%) vs. Latitude

![lat v ncloud](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_cloud_northern.png)
* Southern Hemisphere - Cloudiness (%) vs. Latitude

![lat v scloud](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_cloud_southern.png)
* Northern Hemisphere - Wind Speed (mph) vs. Latitude

![lat v nwind](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_wind_northern.png)
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

![lat v swind](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/output_data/lat_v_wind_southern.png)

After each pair of plots explain what the linear regression is modeling such as any relationships you notice and any other analysis you may have.

Your final notebook must:

* Randomly select **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

#### Part II - VacationPy

Now let's use your skills in working with weather data to plan future vacations. Use jupyter-gmaps and the Google Places API for this part of the assignment.

* Create a heat map that displays the humidity for every city from the part I of the homework.

  ![heatmap](Images/heatmap.png)

* Narrow down the DataFrame to find your ideal weather condition. For example:
``ideal_df = weather_df.loc[(weather_df["Max Temp"] > 65) & (weather_df['Max Temp'] < 77) & (weather_df["Cloudiness"] == 0) & (weather_df['Humidity'] < 50) &(weather_df['Wind Speed'] < 15), :]``

* Using Google Places API to find the first hotel for each city located within 5000 meters of your coordinates.
``  "radius": 5000,
    "types": "lodging",
    "keyword": "Hotel",
    "key": gkey``
    
* Plot the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](https://github.com/tanazimmer/PythonAPI-Challenge/blob/master/Images/heatmap_with_markers.jpg)

