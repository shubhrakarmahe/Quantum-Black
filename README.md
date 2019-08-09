# Quantum-Black

ACRTA road taxation data engineering

Astro City Road transport authority (ACRTA) in US have come up with an idea to use car registration renewal charges to provide indirect incentives to safe drivers. Also, providing subsidies to certain areas as per the extreme climatic conditions in terms of heavy snow or rain.
ACRTA has contacted us to perform a quantitative study and design a prediction model to support the aforementioned applications.
We, being a part of the data engineering team, are working continuously with the business stakeholders as well as data scientists to create features around these scenarios.
Problem statement that we have been provided is to “Develop inputs for a model that predicts the chances of having a vehicle accident based on driving conditions. This model will help the transport authority to understand risk patterns and act upon them.”
This output then would be utilized so as to come up for a risk-based taxation on different drivers and locations as per crash-prone weather conditions.

Use cases would be –
Imposing “unsafe driving tax” on drivers to provide a positive feedback loop which may be revisited every year by looking at the past year trip data based on the driving patterns.
Lower the tax in the regions where the climatic conditions lead them to become a crash-prone site.

Data Description
Drive Data (Connected car data) – Data coming from the car-mounted devices, which provides you with the car statistics every second. This information will include – Speed, acceleration, engine temperature and other car statistics.
Trip – Parameters associated with location of car such as lattitude, longitude, altitude and other similar parameters.
Weather – Weather condition at different latitude & longitude during different times each day.
Vehicle Specifications – Different vehicle technical specifications which comes from the manufacturer of the car.

Engine Features (file name – engine_features.csv)- Grain - every vehicle aggregated at week start date(Monday) for the complete week in YYYY-MM-DD format. Sorted - by Vehicle ID and week_start_Date in ascending manner
Hints:
Convert timezone to PST before any calculations
All vehicles from drive data should be in the final output even if you do not have specifications (Fill with 0 if specs are not given)
Active horsepower - Engine load / 255 Max Torque RPM / 5252
Horsepower utilization – Active horsepower / Max Horsepower
Torque Utilization - calculated as Engine load/ 255
RPM Utilization – RPM / Maximum horsepower rpm

Drive features(file name – drive_features.csv) - Grain – Every trip’s aggregated features at a trip id level.
Sorted - by trip_id in ascending manner
Hints:
Acceleration m/s is calculated as a change in velocity over time
If a vehicle keeps on accelerating continuously over a period of time, please treat them as a single acceleration or deacceleration period.

Weather features (file name – weather_features.csv)
grain – Every vehicle detail should be aggregated at a week start date. Sorted - by vehicle_id and week_start_date in ascending manner
Hint: convert time zone to PST before any calculations
Assumptions & Hints–
Weather data is already in PST and may not need any timezone conversion. You may consider the weather data to be constant for complete hour basis. For example- if the temperature is given to be 284.51 for 2017-02-14 19:00:00, it would be the same for time 2017-02-14 19:15:45 as well.
Haversine formula must be utilized to measure the distance between any 2 consecutive points in between the trips.
Matches in between datasets must be on geohash precision point 5.

#-----------------------------------------------------------------------------#

Leaderboard Rank out of 3448 participants

Private LB - 63

Public LB - 64

#----------------------------------------------------------------------------#
