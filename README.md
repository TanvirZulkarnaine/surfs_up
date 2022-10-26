# Project: surfs_up
## Overview:
For this project, I had to write queries to determine the temperature statistics (min, max, avg, etc.) for the months of June and December for the investor, W.Avy. The purpose behind this analysis is to demonstrate whether the months of June and December has desiarable temperature for having ice cream. I believe W.Avy asked for this temperature data from middle of the year and the end of the year to check if there is a sharp change in temperature for this particular location. 

## Results:
Summary Statistics of Temperature in June: 
--
![June_temp](/june_temps.png)
--
Summary Statistics of Temperature in December: 
--
![Dec_temp](/december_temps.png)
--
- Viewing the two tables above, we see that the average temperature of both these months is very close to each other. Avg temperature for June being 74.9 and December being 71.04. As expected of the end of December to be little colder since winter season, however, it is still relatively close to avg temp of June. 
- I have noticed the number of times the data was gathered is almost 200 more in June compared to December. However, this is not an issue as the number of times the data was gathered are still 1500+ and I feel that is sufficient enough to be very accurate.
-  I have also noticed average/mean is almost has the same value as the median/50th percentile. This gives me confidence that the data does not have any outliars and the min/max temperatures of both months are accurate. 

# Summary:
According to the data summary statistics of temperatures collected for these two months: June and December, I believe that it is an ideal location to build the icescream and surf shop as the average temperature of middle of the year and end of the year are ideal for surfing and having ice creams!
For further analysis, I believe it would be great to write a query to check the list of stations and which stations are gathering the most data. To do that, I would write:
- session.query(Measurement.station,func.count(Measurement.station)).group_by(Measurement.station).order_by(func.count(Measurement.station).desc()).all()

Another query I would write would be the same query of this analysis however, filtered to only gathering the data from the station with the highest number of times data is gathered (which is collected from running the above query). To do that, I would write:
- session.query(Measurement.tobs).filter(extract('month', Measurement.date) == 12).filter(Measurement.station == '>station id here<').all()

I would then put this query into a list variable, and turn it into a dataframe. Lastly, write "dataframe.describe()" to get the summary statistics!
