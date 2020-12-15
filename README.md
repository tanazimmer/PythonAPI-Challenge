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

* **Note:** Remember that any API usage beyond the $200 credit will be charged to your personal account. You can set quotas and limits to your daily requests to be sure you can't be charged. Check out [Google Maps Platform Billing](https://developers.google.com/maps/billing/gmp-billing#monitor-and-restrict-consumption) and [Manage your cost of use](https://developers.google.com/maps/documentation/javascript/usage-and-billing#set-caps) for more information.

* **Note:** if you having trouble displaying the maps try running `jupyter nbextension enable --py gmaps` in your environment and retry.

* Create a heat map that displays the humidity for every city from the part I of the homework.

  ![heatmap](Images/heatmap.png)

* Narrow down the DataFrame to find your ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Drop any rows that don't contain all three conditions. You want to be sure the weather is ideal.

  * **Note:** Feel free to adjust to your specifications but be sure to limit the number of rows returned by your API requests to a reasonable number.

* Using Google Places API to find the first hotel for each city located within 5000 meters of your coordinates.

* Plot the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](Images/hotel_map.png)

As final considerations:

* Create a new GitHub repository for this project called `API-Challenge` (note the kebab-case). **Do not add to an existing repo**
* You must complete your analysis using a Jupyter notebook.
* You must use the Matplotlib or Pandas plotting libraries.
* For Part I, you must include a written description of three observable trends based on the data.
* For Part II, you must include a screenshot of the heatmap you create and include it in your submission.
* You must use proper labeling of your plots, including aspects like: Plot Titles (with date of analysis) and Axes Labels.
* For max intensity in the heat map, try setting it to the highest humidity found in the data set.

## Hints and Considerations

* The city data you generate is based on random coordinates as well as different query times; as such, your outputs will not be an exact match to the provided starter notebook.

* You may want to start this assignment by refreshing yourself on the [geographic coordinate system](http://desktop.arcgis.com/en/arcmap/10.3/guide-books/map-projections/about-geographic-coordinate-systems.htm).

* Next, spend the requisite time necessary to study the OpenWeatherMap API. Based on your initial study, you should be able to answer  basic questions about the API: Where do you request the API key? Which Weather API in particular will you need? What URL endpoints does it expect? What JSON structure does it respond with? Before you write a line of code, you should be aiming to have a crystal clear understanding of your intended outcome.

* A starter code for Citipy has been provided. However, if you're craving an extra challenge, push yourself to learn how it works: [citipy Python library](https://pypi.python.org/pypi/citipy). Before you try to incorporate the library into your analysis, start by creating simple test cases outside your main script to confirm that you are using it correctly. Too often, when introduced to a new library, students get bogged down by the most minor of errors -- spending hours investigating their entire code -- when, in fact, a simple and focused test would have shown their basic utilization of the library was wrong from the start. Don't let this be you!

* Part of our expectation in this challenge is that you will use critical thinking skills to understand how and why we're recommending the tools we are. What is Citipy for? Why would you use it in conjunction with the OpenWeatherMap API? How would you do so?

* In building your script, pay attention to the cities you are using in your query pool. Are you getting coverage of the full gamut of latitudes and longitudes? Or are you simply choosing 500 cities concentrated in one region of the world? Even if you were a geographic genius, simply rattling 500 cities based on your human selection would create a biased dataset. Be thinking of how you should counter this. (Hint: Consider the full range of latitudes).

* Once you have computed the linear regression for one chart, the process will be similar for all others. As a bonus, try to create a function that will create these charts based on different parameters.

* Remember that each coordinate will trigger a separate call to the Google API. If you're creating your own criteria to plan your vacation, try to reduce the results in your DataFrame to 10 or fewer cities.

* Lastly, remember -- this is a challenging activity. Push yourself! If you complete this task, then you can safely say that you've gained a strong mastery of the core foundations of data analytics and it will only go better from here. Good luck!

* Ensure your repository has regular commits (i.e. 20+ commits) and a thorough README.md file

### Copyright

Trilogy Education Services © 2019. All Rights Reserved.
