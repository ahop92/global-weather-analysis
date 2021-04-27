# python-api-challenge

## Background 

Two programs were developed using Jupyter Notebooks: Weather.py and Vacation.py. 

Weather.py uses the OpenWeather API system to pull current weather data according to a random list of cities generated using the citipy library in Jupyter Notebooks. Comparisons of different weather metrics (complete with lienar regressions and organized by hemisphere) were completed in an effort to idenitfy correlations.

Once correlations were evaluated, the compiled weather dataframe was output to a csv file for use in Vacation.py. The Vacation.py script imports the weather dataframe and converts the information about humidity into a heatmap visualization using the Google gmaps. According to desired vacation preferences specified in the assignment, the weather data was filtered to idenify only those locations deemed fit for vacation. Using the Google Nearby API and Google Geocoder API, hotels within 5000 meters of the vacation spots were identified (along with city and country info). Lastly, using gmaps markers were superimposed onto the original heatmap that identify the hotel location corresponding to the vacation spot. 

### Analyses

#### Weather.py

 A series of scatter plots was created to showcase the following relationships:

Temperature (F) vs. Latitude
Humidity (%) vs. Latitude
Cloudiness (%) vs. Latitude
Wind Speed (mph) vs. Latitude

After each plot, add a sentence or two was added explaining what the visual is analyzing.
Separating the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude) linear regressions were run on the four previous graphs in the following order:

Northern Hemisphere - Temperature (F) vs. Latitude
Southern Hemisphere - Temperature (F) vs. Latitude
Northern Hemisphere - Humidity (%) vs. Latitude
Southern Hemisphere - Humidity (%) vs. Latitude
Northern Hemisphere - Cloudiness (%) vs. Latitude
Southern Hemisphere - Cloudiness (%) vs. Latitude
Northern Hemisphere - Wind Speed (mph) vs. Latitude
Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots, there is a brief description stating whether or not a correlation exists. 

#### Vacation.Py

First, the CSV file output from the previous program was imported. 

Using gmaps, a basic heatmap using humidity as the primary metric was generated with maximum intensity being specified as 100 % humidity. 

The following metrics were used to filter down to acceptable vacation spots: 

1. A max temperature lower than 80 degrees but higher than 70.
2. Wind speed less than 10 mph.
3. Zero cloudiness.

Hotels were identified using the Google Nearby Places API with 5000 meters as the associated distance. 

Considering the locality of the hotel could be different than the vacation spot, Google Geocoder API was implemented to identify the formatted address, city, and country of the hotel location using the latitude and longitude derived from the Nearby Places API. 

### Results 

Please see the either output data file folder in the repository or the main scripts to view the results (graphs and heatmaps)

1. There was only one strong correlation for the weather data: temperature and latitude. 
2. There were only 3 locations identified that meet the vacation criteria. 
3. For the three hotel locations, the address information was not clearly identifiable due to language preferences (locations in Egypt and Iran contained information in a different language)

