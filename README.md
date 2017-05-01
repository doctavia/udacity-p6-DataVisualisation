# udacity-p6-DataVisualisation

https://bl.ocks.org/doctavia/raw/0a6d24a15f3188e1d0a276cb4bee4211/

## Summary
This data visualization shows the performance of US airlines between 2007 and 2016, average delay duration by delay causes and percentage of delay by airports. The dataset was obtained from <a href = "https://www.transtats.bts.gov/DL_SelectFields.asp?Table_ID=236">Bureau of Transportation Statistics. </a>  

## Data Story
Over the past ten years, US carriers have been striving to improve their flights performance, with Hawaiian Airlines leading as the most punctual carrier. However there seems to be some setbacks in 2013 and 2014. The high average delay in 2013 was due to weather, NAS, security and late aircraft. The delay by late-arriving aircraft was at its peak on June 2013. It could be related to extreme weather event which was also peaked on June 2013. There was noticeable increase of delayed flights throughout US from 2012 to 2013. In 2014, delay by carrier, weather and late aircraft contributed to ontime performance setback.       

## Design
### Exploratory Data Analysis 
The monthly dataset from 2007 to 2016 was downloaded from BTS website and combined into multiple csv files by year using RStudio. Due to file size, the dataset was then grouped and cleaned according to the visualizations. The details can be found in <a href = "https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/P6_Flights_EDA.Rmd"> P6_Flights_EDA.Rmd. </a>

The visualization design was inspired by Hans Rosling's famous chart on Health & Wealth of Nations. It was applied to show US carriers performance over the past ten years.
![Alt text](https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/us_carriers_bubbles.jpg "Optional Title")

After having ten years of visualization in animation, I noticed the clusters of airlines moving up the slope each year until 2013 and 2014 where there was obvious drop of performance for most of the airlines. I decided to look into the cause of increasing delay in those two years and finding the airport where the delay happened. Initial visualization sketch is as shown below: <br>
![Alt text](https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/P6_Sketch.jpg "Optional Title")

The causes of flight delay are based on <a href="https://www.rita.dot.gov/bts/help/aviation/html/understanding.html">BTS website</a> that they are grouped into five main categories:<br>
"
* Air Carrier: he cause of the cancellation or delay was due to circumstances within the airline's control (e.g. maintenance or crew problems, aircraft cleaning, baggage loading, fueling, etc.).
* Extreme Weather : Significant meteorological conditions (actual or forecasted) that, in the judgment of the carrier, delays or prevents the operation of a flight such as tornado, blizzard or hurricane.
* National Aviation System (NAS) : Delays and cancellations attributable to the national aviation system that refer to a broad set of conditions, such as non-extreme weather conditions, airport operations, heavy traffic volume, and air traffic control.
* Late-arriving aircraft : A previous flight with same aircraft arrived late, causing the present flight to depart late.
* Security : Delays or cancellations caused by evacuation of a terminal or concourse, re-boarding of aircraft because of security breach, inoperative screening equipment and/or long lines in excess of 29 minutes at screening areas. "


The initial design of the monthly flight delay causes was shown in summation of delay duration in minutes. It was then changed to average of delay duration in minutes to give a better perception to viewers. 
![Alt text](https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/P6_lineChart_sum.jpg "Optional Title")

The line chart shows that the increase of delay in 2013 was caused by NAS and late-arriving aircraft while the delay in 2014 was due to weather in January 2014. When delay caused by extreme weather happens, it has direct impact on airport operation (NAS delay) and airline's control (carrier delay). This proportionality can be seen in the line chart on June 2007, December 2007, December 2008 and January 2014.   

The initial idea for delay location chart was to have two charts that show delayed departure flight and delayed arrival flight. This idea was then scrapped as the visualization of delayed departure or arrival flight were identical and no additional information could be drawn by having both charts. The similarity of departure and arrival delay is because duration of delays are logged per flight. 

The flexibility to have delay location chart that could pinpoint both delay location and event was constrained by the file size of dataset with daily airport log and the lack of database that could offer explanation to flight delay cause. The delay location visualization was then trialled based on yearly data. 

The visualization before feedback collection is as shown below:
![Alt text](https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/P6_initial_draft.jpg "Optional Title")


## Feedback and Design Changes
### First Feedback:
"I think you did a great job in using animation to spice up the visualization. In the meantime, if you can keep the US Carrier Performance graph static after the animation, and better yet, provide a control widget that allows for exploration based on years, it'll be great! (same for the bottom right map)

Also, for the "Flight Delay Causes in 2016" graph, if you want to communicate that late aircraft is the leading cause for delays, it's better to highlight the line with a different color to let it stand out."

### Design Changes on First Feedback:
* The location of years buttons was not strategic hence they were moved from top right corner to centre of the page. 
* The finding to be communicated in Flight Delay Causes chart is that the delay average of NAS, late aircraft, weather and security in 2013 were higher than in year 2012 hence they were the delay categories that contributed to the setback of airlines performance in 2013. The changes made to convey this message were thicker line if the delay average is higher than the previous year.       

### Second Feedback:
"The animated US airlines performance chart is interesting, it is like a marathon race among airlines climbing upwards to higher ontime arrival%. I can see the Hawaiian Airlines stays on as the front runner. What does the different circle size mean? A legend would help I think.
In this line chart, the thick lines highlight the delay causes for each year. Why are there gaps between each years?  I think the delayed departure % by airport map needs a legend too"

### Design Changes on Second Feedback:
*	Fixed tooltips to explain what numbers are, in both “US Carriers Performance” and “ Percentage of Delayed Departures by Airport” graphs.
*	No changes to “Flight Delay Causes” chart as (in my opinion) the gaps help to guide the eyes to start and end of each year, and I am not sure how to fill the gaps.   

### Third Feedback:
“ Southwest Airlines has the most number of flights every year and its ontime performance dropped 5% in 2013. I am surprised that weather is not the biggest cause of flight delay. 
What stands out from the map is those busy airports, the airports with darker red draw my attention. It’d be cool to be able to filter the map data by months so that there is a deeper layer of information. Maybe by having monthly option, we can see which region have the most delay on, say June 2013 where the late aircraft delay is at its peak.” 

### Design Changes on Third Feedback:
*	Added buttons to filter data by months for each year.  





## Resources
* https://bost.ocks.org/mike/nations/
* http://bl.ocks.org/ZJONSSON/3918369
* https://stackoverflow.com/questions/6487366/how-to-generate-event-handlers-with-loop-in-javascript
* http://eric.clst.org/Stuff/USGeoJSON


