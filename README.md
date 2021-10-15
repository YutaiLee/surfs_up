# surfs_up
## Overview of the project
The purpose of this project is to look at temperature statistics for June and December to determine whether operating a surf shop is sustainable throughout the year. The way we get the temperature data is to run two separate queries, one for June and the other for December. After running the query, we store the temperatures in a list and then convert them into data frames.
### Analysis

The results for June are shown below.

![image](https://github.com/YutaiLee/surfs_up/blob/main/Resources/June_Temps.png)

The results for December are shown below.

![image](https://github.com/YutaiLee/surfs_up/blob/main/Resources/December_Temps.png)

* The temperature in June ranges from 64 to 85 degrees F, and the temperature in December ranges from 56 to 83 degrees F.
* The average temperature in June is 75 degrees F, while the average temperature in December is 71 degrees F.
* Due to the higher standard deviation of the temperature in December, the temperature distribution in December is larger than that in June.
## Summary
We can use the following code to query the total precipitation in June and December.

session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()
session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()

We can use the following code to query the precipitation of the most active stations in June and December.

session.query(Measurement.prcp).filter(Measurement.station == 'USC00519281').filter(extract('month', Measurement.date) == 6).all()
session.query(Measurement.prcp).filter(Measurement.station == 'USC00519281').filter(extract('month', Measurement.date) == 12).all()

Through these analyses, we can obtain more useful information to evaluate the year-round sustainability of surfing and ice cream shop business.
