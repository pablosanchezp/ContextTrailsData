# Context Trails

Repository containing the data used in the paper:  
**Context Trails: A dataset to study contextual and tour recommendation**


### 📂 Repository Structure
 - **data**: directory containing the data of the three cities explored in the dataset:
  - NewYorkCity: data  corresponding to New York City.
  - PetalingJaya: data corresponding to Petaling Jaya (Kuala Lumpur district).
  - Tokyo: data corresponding to the city of Tokyo.

The structure of the data contained in each city is as follows:

- POIS_INFO_\<WikidataID>_\<city>_lvl1_categories.csv: it is a CSV containing the following information obtained from the Foursquare API:
    - fsq_id: original Foursquare id.
    - latitude.
    - longitude.
    - category (each POI might contain more than one category). Each category separated by "-".
    - price.
    - rating.
    - total_ratings.
    - total_tips.
    - a set of booleans denoting if the POI is open in that interval (1 open, 0 closed) in both weekdays (monday to friday) and weekends (Saturdays and Sundays).
        - EarlyMorning is between 00:00 to 06:00.
        - Morning is between 06:00 to 12:00.
        - Afternoon is between 12:00 to 18:00.
        - Night is between 18:00 to 24:00.
        - the category of level 1 from Foursquare.
    - \<WikidataID>_\<city>_trails_weather.zip: zip directory containing a CSV separated by ; containing the following information:
        - trail_id: the id of the trail.
        - user_id: the id of the user.
        - venue_id: original Foursquare id.
        - timestamp: date following the ISO 8601 format.
        - temp: temperature in Cº at the moment of the check-in.
        - precip: value of the precipitation at the moment of the check-in.
        - windspeed: wind speed at the moment of the check-in.
        - preciptype: type of the precipitation at the moment of the check-in.
        - conditions: sky condition at the moment of the check-in.

    - \<WikidataID>_\<city>_trails_weather_aggregated.zip: ZIP file containing 3 different files:
        - \<WikidataID>_\<city>_trails_weather_aggregated.csv: CSV file separated by ";" containing the aggregated check-ins of each user (hence, all the trails are removed). It contains an additional column denoted as number_of_visits that contains the number of visits that that user have visited the specific POI. The timestamp represents the last time that the user visited that venue.
        - \<WikidataID>_\<city>_trails_weather_aggregated_Temp80train.csv: CSV containing the check-ins of the users used to train the recommenders (80% of the most ancient ratings were used for training).
        - \<WikidataID>_\<city>_trails_weather_aggregated_Temp20test.csv: CSV containing the check-ins of the users used to test the recommenders (20% of the most recent ratings were used for test).

    - \<WikidataID>_\<city>_trails_routes_2_minroutes_4_minPois_training_test.zip: ZIP file containing the training and test set used for the route recommendation task. For every user with at least 2 different routes, if the last route contains at least 4 POIs, then is sent to test, else, it is sent to the training file. It contains 2 different files:
        - \<WikidataID>_\<city>_trails_routes_2_minroutes_4_minPOIS_TestRouteTraining.csv: training file used for the route recommendation problem.
        - \<WikidataID>_\<city>_trails_routes_2_minroutes_4_minPOIS_TestRouteTest.csv: test file used for the route recommendation problem.

 - **NOTE**: the experiments conducted in the paper can be found [here](URL REPOSITORY)






### 👥Authors
- Pablo Sánchez - [Universidad Pontificia Comillas](https://www.comillas.edu/)
- Alejandro Bellogín - [Universidad Autónoma de Madrid](https://uam.es)
- José Luis Jorro Aragoneses - [Universidad Autónoma de Madrid](https://uam.es)

### 📬 Contact

* **Pablo Sánchez** - <psperez@icai.comillas.edu>


### 🙏 Acknowledgments
 - This work was supported by grant PID2022-139131NB-I00 funded by MCIN/AEI/10.13039/501100011033 and by ``ERDF A way of making Europe.''
