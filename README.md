# udacity-p6-DataVisualisation

https://bl.ocks.org/doctavia/raw/31e61985fc675bcf335734f793611a17/

## Summary
This data visualization shows the performance of US airlines between 2007 and 2016. Over the past ten years, there has been steady decrease in flight delays with some setbacks in 2013 and 2014. Hawaiian Airlines leads as the most punctual carrier, followed by Alaska Airlines and Delta Airlines that have surpassed the performance of other carriers over the years.

## Design
### Exploratory Data Analysis 
The monthly dataset from 2007 to 2016 was obtained from <a href = "https://www.transtats.bts.gov/DL_SelectFields.asp?Table_ID=236">Bureau of Transportation Statistics. </a>  Due to the size of the file, instead of having all the dataset in one master file, they were combined into ten csv files grouping by year using RStudio. In the early stage of visualization design, three different charts were to be encoded hence three separate datasets was structured accordingly. The details can be found in <a href = "https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/P6_Flights_EDA.Rmd"> P6_Flights_EDA.Rmd. </a>

The visualization design was inspired by Hans Rosling's famous chart on Health & Wealth of Nations. It was applied to show US carriers performance over the past ten years.
![Alt text](https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/us_carriers_bubbles.jpg "Optional Title")

After putting together ten visualizations of US carriers annual delay arrival percentage, I noticed the clusters of airlines moving up the slope each year until 2013 and 2014 where there was obvious drop of performance for most of the airlines. The drafted animation is encoded in <a href = "https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/index1.html"> index1.html.</a> I then decided to look into the cause of increasing delay in those two years and finding the airport where the delay happened. Initial visualization sketch and charts are as shown below: <br>
![Alt text](https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/P6_Sketch.jpg "Initial Sketch")

![Alt text](https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/P6_initial_draft.jpg "First Visualization")

### Initial Design Decisions
#### Chart 1 - US Carriers Performance 
* Data story : Steady increase of carriers performance over the ten years period with some setbacks in 2013 and 2014, and Hawaiian Airlines leading the way
* Chart choice : animated bubbles chart is great for depicting changes in ranking/performance over time and each bubbles can be used to descibe more detailed information. 
* x-axis : delayed arrival percentage; y-axis : ontime arrival percentage. Ontime arrival percentage is inversely proportional of delayed arrival percentage. By having these two in x and y axes will show the up-and-down of each carrier performance.
* Visual encodings : position, different circle size to show total number of flights, color hue to distinguish carriers.
* Additional features: year buttons, legend for circle size (total number of flights) and tooltips to show airline name, x and y axes values, and total number of flights.

#### Chart 2 - Flight Delay Causes in Year
* Data story : extreme weather does not contribute to flight delay as much as late-arriving aircraft, carrier and National Aviation System (NAS) delays; When delay caused by weather happens, it has direct impact on airport operation (NAS delay) and airline's control (carrier delay), the proportionality can be seen in the line chart on June 2007, December 2007, December 2008 and January 2014; The increase of delay in 2013 was caused by NAS and late-arriving aircraft; delay in 2014 was due to weather in January 2014.
* Chart choice : Multi series line chart to track monthly changes of each delay type over ten year period
* x-axis : time ; y-axis : average delay duration in minutes
* visual encodings : position and color hue to encode different types of delay.
* Additional features : year buttons, text legend for delay types, tooltips to show delay types, time and value on y-axis (average delay duration)

#### Chart 3 - Percentage of Delayed Departure by Airport in Year
* Data story : The purpose of this chart was to show the location where delay occured over time. No clear trend was shown in visualization other than highlighting busy airports like O'Hare Airport and Hartsfield–Jackson Atlanta International Airport.
* Chart choice : animated dot map to show distribution of delayed flights across US airports over time
* visual encodings : circle size to encode number of delayed flights at an airport, color saturation to encode percentage of delayed flight
* Additional features :  year buttons, tooltips to show airport name, city, total number of delayed flights and percentage of delayed flight


### Design Changes
After receiving feedback to provide control widget after animation, the existing set of year buttons was moved from top right corner of the page to more strategic location. Reviewer A was not sure of the takeaway message from Chart 2, the line chart. The finding to be communicated in the line chart is that the delay average of NAS, late aircraft, weather and security in 2013 were higher than in year 2012 hence they were the delay categories that contributed to the setback of airlines performance in 2013. The changes made to convey this message were thicker line if the delay average is higher than the previous year.  

The feedback from second reviewer was to add legend to US Carrier Performance chart and the dot map, also to remove gap in the line chart. The design changes made was edited tooltips to explain what numbers are, in both “US Carriers Performance” and “ Percentage of Delayed Departures by Airport” graphs.

A set of month buttons to filter yearly data by month was added to Chart 3 after third feedback. 

The updated visualization design is shown below
![Alt text](https://github.com/doctavia/udacity-p6-DataVisualisation/blob/master/P6_first_submission.jpg "First submission")

The first visualization submitted contains three charts and it is more of a exploratory than explanatory visualization. The updated visualization now focuses only on the bubbles chart (Chart 1) to tell a story about US carriers performance over ten years period with some setbacks in 2013 and 2014. The title of visualization was changed to "US Carriers Improve Arrival Performance Year-on-Year with a Dip in 2013 and 2014" as suggested to emphasize on the story. Legend of circle size was added to show total number of flights. A set of buttons was also added to toggle carrier's visibility on the chart, each carrier button has the same color as its carrier circle element hence the buttons also double-up as a legend. 


## Feedback
### First Review
"I think you did a great job in using animation to spice up the visualization. In the meantime, if you can keep the US Carrier Performance graph static after the animation, and better yet, provide a control widget that allows for exploration based on years, it'll be great! (same for the bottom right map)

Also, for the "Flight Delay Causes in 2016" graph, if you want to communicate that late aircraft is the leading cause for delays, it's better to highlight the line with a different color to let it stand out."     

### Second Review
"The animated US airlines performance chart is interesting, it is like a marathon race among airlines climbing upwards to higher ontime arrival%. I can see the Hawaiian Airlines stays on as the front runner. What does the different circle size mean? A legend would help I think.
In this line chart, the thick lines highlight the delay causes for each year. Why are there gaps between each years?  I think the delayed departure % by airport map needs a legend too" 

### Third Review
“ Southwest Airlines has the most number of flights every year and its ontime performance dropped 5% in 2013. I am surprised that weather is not the biggest cause of flight delay. 
What stands out from the map is those busy airports, the airports with darker red draw my attention. It’d be cool to be able to filter the map data by months so that there is a deeper layer of information. Maybe by having monthly option, we can see which region have the most delay on, say June 2013 where the late aircraft delay is at its peak.” 

### Fourth Review (First Submission)
" You've made some considered design choices so far. I particularly like:

the Hans Gosling style bubble chart
the Animation
the use of boldness to indicate delay increase
However, bearing in mind the goal is an EXPLANATORY visualisation there are a few changes you need to make.

I think the overwhelming issue is that there is just too much going on. It is a fantastic technical achievement to get these three different chart types up and running in d3.js and it will stand you in good stead for the future but I'm not sure that they are all needed if you are going to tell a clear and specific story?

It is often useful to put yourself in the mindset of a reader seeing your graphic for the first time. Will they understand your message in that crucial first 10/15 seconds? Is there anything you can do to make this clearer.

For all the charts which you choose to include in your next submission, you need to make sure that each one contributes to your overall story (see above) and that the point you are making is clearly explained and illustrated.

Chart 1 - this is looking fantastic overall. You've successfully replicated the Hans Gosling model and it is great to see the clear drop in performance in 2013 and 2014 as well as the rise and fall of various airlines. However, there are some outstanding issues:

there is no legend and the bubbles are very overcrowded so it is very difficult to track individual airlines or find out who they are - Delta and JetBlue for example, who both have interesting shifts in performance. It would be really helpful to add a legend or to add some sort of filtering after the animation has finished (small, medium and large airline?) to cut down the data points and track individual performance.
what does the bubble size mean? I'm pretty sure it is number of flights but you need to communicate this to the reader rather than letting them work it out by comparing the tooltips.
Chart 2 - this looks great but I'm finding it very difficult to deduce your conclusions as there is so much going on. I think the problem is that you are trying to do two things at once:

a) looking in more detail at the cause of the delays during 2013 and 2014 (where you've seen the dip in performance in Chart 1).
b) illustrating a correlation between weather, NAS delay and carrier delay - particularly during the four quoted date periods.
These are difficult things to show in one chart. My suggestion would be to split this into two 'stories' with a chart for each.

Your line chart will work perfectly for point A but I'd recommend only showing the data for your key years (2013 and 2014).

The second story is more tricky. I find it very hard to see the patterns you have highlighted. Would a snapshot chart for each period with a month either side work? You would have to test it out first. The other thing I thought might be worth testing is only showing the bold lines (higher average delay than previous year?) It is not such a clear conclusion but it does illustrate that an increase in one delay type often comes alongside another?

Chart 3 - as mentioned above, this looks good but I'm not clear what story you are trying to tell. I'd suggest either removing this chart for the scope of this project (you've got quite a lot of work to do already with Charts 1 and 2 and you are already going over and above in terms of chart quantity and coding quality) or analysing the data and focussing on a specific, clear story that your chart is trying to tell."




## Resources
* https://bost.ocks.org/mike/nations/
* http://bl.ocks.org/ZJONSSON/3918369
* http://eric.clst.org/Stuff/USGeoJSON
* https://stackoverflow.com/questions/6487366/how-to-generate-event-handlers-with-loop-in-javascript
* https://stackoverflow.com/questions/25418333/how-to-draw-straight-line-in-d3-js-horizontally-and-vertically
* https://nickqizhu.github.io/d3-cookbook/src/chapter4/ordinal-scale.html
* http://www.rapidtables.com/web/color/RGB_Color.htm
* https://github.com/d3/d3-collection/blob/master/README.md#map
* http://bl.ocks.org/d3noob/5d621a60e2d1d02086bf
* https://stackoverflow.com/questions/13613680/remove-spaces-in-a-javascript-variable
* https://stackoverflow.com/questions/34640807/how-to-select-dom-elements-with-number-value-id-using-d3/34641038
* https://stackoverflow.com/questions/40981761/how-to-toggle-this-element



