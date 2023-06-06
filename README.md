# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
To find patterns and gain insights with data from city_bikes API and a city
## Process
Once I got the Data Frame for all bike stations in the city by using city_bike API and normalising the JSON file, I iterated over a series of concated latitude and longitude values, and retrieved all data of restaurants in a 1km radius (by continously concating the it with a Data Frame of All POIs (Point of Interests) for all stations).

A goal I had in mind was to keep the data tables in a normalized state, so I created a DataFrame to hold all records of how each bike station relates to each POI and their respective distances. 

Similarly doing the same thing for data that holds categories, so each POI and its category id (FYI, they have a one to many relationship) 

I complied YELP's API and compared that to FOURSQUARE'S. The result is each API has its own use cases. Yelp had a higher number of reviews and FOURSQUARE had more POI for each bike station. I decided to continue using data from FOURSQUARE simply becuase it supplied distance between POI and stations and had a meaurement named 'popularity' that measured the visits that POI recieved in the last 6 months.

I also found out that data from both YELP and FOURSQUARE have bias , this is illustrated by querying the top 10 rated POI from YELP and FOURSQUARE, that of which the intersection was small. 

Inserting data tables to sqlite has never been easier with a built in method (to_sql()). 
## Results
Unfortunetly my model only explained 0.4% of the variability in the dependent variable. But this is actually very insightful we can confident say that # of ratings or ratings , # of tips, or even if the POI has been verified or not does not change the # of bikes available.

With the EDA visuals we can see that there is no clear trend, POIs that have less than 6 bike stations in a 1km radius have the same expected popularity as POIs that have 20 in a 1km radius.

## Challenges 
1 challenge I faced was the resulting DataFrame after applying operations to a dataframe, the index would be messed up, this was fixed by reindexing but I learned the hard way. 

Another challenge is knowing that you will only recieve upto 50 POIs for every bike station in a 1km radius, but theorotically there can be a really big number. This fact introduces bias and is incomplete data. I reduced the bias by sorting by distance for the 50 POIs, If I sorted by rating, the bias would be even bigger.

## Future Goals
If I had more time, I would create an ERD for the sqlite DataBase I created, so that it could be easily understood by viewers. 

I also would try other regression models, to find out which model explains the variability in the dependent variable the most.  
