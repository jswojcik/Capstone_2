# Predicting NFL Performance from Combine Results
Springboard Capstone 2

## 1. Problem & Context:
The NFL Scouting Combine is an annual event where college football players perform physical and mental tests in front of National Football League coaches, general managers, and scouts.  The purpose of the combine is to provide insight into the medical history, athletic
abilities, psychological state, as well as demonstrations of skill in positional drills of potential prospects.  It’s long been wondered do the results of these physical tests have any effect on future NFL Performance? The goal of this project is to predict individual players NFL performance based on Combine results.

## 2. Target Clients: 
The primary clients this project targets are NFL coaches, scouts, and general managers. The clients spend millions of dollars on the acquisition of talent every year when drafting players. The results of this project will hopefully aid them in picking potential players in the NFL Draft.   

## 3. Data:
The dataset that will be used for this project was created by Sports Viz Sunday  (https://data.world/sportsvizsunday) and posted on data.world.  The dataset comes in a single excel file with two sheets: one for NFL Combine results (10,228 rows, 16 columns) and one for NFL Draft results (8,435 rows, 34 columns). I’ll be using data from the years 1987 to 2015 in my project.  The dataset is available for download via the following link: https://data.world/sportsvizsunday/nfl-combine-data/workspace/file?filename=NFL+Combine+Data.xlsx

## 4. Data Wrangling: 
The main issue with the raw dataset was missing values and the need to merge the two separate sheets. Because I could only use players who were both drafted and attended the NFL Combine, after merging the two datasets, the resulting data frame was 5643 rows and 51 columns.  I removed the ‘HOF’ column due to all of the values being ‘no’ which was clearly incorrect. I also converted the ‘sk’ column into a float because it was previously an object data type. I dropped unnecessary columns including the ’To’ column. Instead I replaced it with a new feature by subtracting ‘To’ from ‘Draft_Year’ to get the number of seasons played. 

As for dealing with missing values, since dropping rows with any missing values would reduce the dataset to almost nothing, I decided to impute the missing values. Many rows had Na values for Combine results due to players bypassing certain drills for various reasons. The easiest and most efficient way to fill these missing values is by using K Nearest Neighbors (KNN) method. KNN is an algorithm that is useful for matching a point with its closest k neighbors in a multi-dimensional space. 

## 5. EDA:
* The data follows the pareto distribution
* In general, higher draft picks have higher approximate values.

![ECDF_av](https://user-images.githubusercontent.com/61096314/94972763-49514d00-04c7-11eb-84f9-864dc47919dd.png)

![image](C:\Users\Jake Wojcik\Documents\Springboard\DS Career Track Course\Capstone_2\Figures\AV_pick.png)

## 6. Modeling:
Separate by Player Position
Since the Combine is more important for some positions, I decided to separate the dataset by player position to see if the models improved any.
Unsurprisingly, quarterbacks had little to no predictive power. I was able to improve the model's score in wide receivers and running backs by using a ridge regression model and tuning hyperparameters.

![image](C:\Users\Jake Wojcik\Documents\Springboard\DS Career Track Course\Capstone_2\Figures\model_comparison.png)

We can see there is almost no predictive power in determining draft position for quarterbacks. It is a little surprising to see doing well on the Combine rarely has any effect in increasing one's chance of being drafted higher. 

## 7. Predictions: 
Overall the best performing model still has little predictive power in determining draft position and, in turn, NFL success. Predictions were generally off by a fair amount (Figure 5,6). Being off by an average of ~59 picks is very bad considering each round is 32 picks. I would consider this model a success if it were able to predict the round drafted reasonably well, but here it's off by almost two whole rounds. 

![image](C:\Users\Jake Wojcik\Documents\Springboard\DS Career Track Course\Capstone_2\Figures\predictions_rb.png)

## 8. Conclusions: 
* Raw athleticism may not be as critical as casual NFL fans claim it to be. 
* Work ethic, motivation, and attitude combined with athleticism are what it takes to really succeed in the NFL.
* Traditional scouting remains the best way to determine who to pick on draft day. 
* Use Combine measurements as supplemental material when selecting a player but don’t put too much stock in them.

## 9. Future Research: 
* Utilizing college statistics could improve prediction models for NFL performance for all positions.  
* It would be interesting to see the difference in NFL performance from players who excel at smaller colleges compared to players who excel at powerhouse programs.  
* It would also be helpful to obtain more data from the most recent draft years and see if that improves the models any. 
* I think it would be interesting to create a “draft grade” feature, assigning a grade to every player going into the draft based on scouting and media sentiment at the time. 




