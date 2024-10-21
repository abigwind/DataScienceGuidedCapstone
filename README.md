# Big Mountain

## Problem: 
Have you ever bought a new car? If driving is your job, then a new car is a solid investment that will improve your business until…the first payment is due. It’s easy to forget the greatness the car brings to you when the recurring bill is on the horizon. So what do you do? 

In the case of Big Mountain resort, that new car is a chair lift with a high  annual operating cost. Where will that money be made up? Should some of the ski runs be cut or is there justification for increasing ticket prices? This is what I found.

## Goal: 
Recoup $1,540,000 annually to cover operational costs within the 123 day season.

## Method:  
From a database of national ski resorts within the market share, I wrangled the data to find unnecessary information, homogenized data types, merged it with a database of state sizes and populations, and dropped rows without ticket prices. An interesting find in this stage was that Big Mountain’s current ticket price of $81 is an outlier in Montana (Figure 1).

During Exploring Data Analysis, I wanted to find features that could predict the adult weekend ticket price for resorts. Montana is one of the biggest states but doesn’t have as big of a population, but with ratios of resorts per 100k capita, Montana comes in fourth. I then, in order to start comparing features, scaled the data, did a PCA transformation, created a heat map of correlations (Figure 2), and a collection of scatterplots. I found positive correlations for vertical drop, fast quads, total chairs, runs, and snow making acres (Figure 3).  My next step was to build a machine learning model. 


I started by testing the mean price of tickets, then the median data and the mean absolute error for both, but at this point, I was worried the model was overfitted. I used sklern’s SelectKBest feature in a pipeline with cross-validation and GridSearchCV to find the best value for k to figure out the features with the highest (and lowest) correlation. I wanted to recheck these features (Figure 4) using a random forest model and I decided to go forward with the random forest model.
	I refitted the data and calculated the expected Big Mountain ticket price from the model and found it to be $95.87 with an expected mean absolute error of $10.39.  After checking national and state data, Montana is very high for many features (Figure 5). 

                   
I ran some scenarios and found that a price plateau of lost revenue happens at closing 3-5 runs, if a run is added and the vertical drop is increased and an additional chairlift is installed it would support a ticket increase of $1.99. The same increase would be supported even if 2 acres of snow making were added to the chairlift, vertical drop, and additional run. Lengthening the longest run and adding 4 acres of snow coverage would support no increase in ticket prices. I found that the biggest price increase is from adding one fast quad ($23.17/ticket), but I don’t know what it costs to buy, install, or operate . 

## Conclusion: 
Big Mountain should raise its price at least to $96. If operational costs need to come down as well, close 5 runs and lower ticket prices to $95.50. 

## Future scope:	
In the future, I would like to have more information about the operational costs and look into mappings of chair lift to runs and skiable terrain ratios as well as estimated use in order to pinpoint which runs to close. Also, I’d want to explore futures wherein another fast quad is added to the resort. 
