# Capstone_2
Springboard Capstone 2
Predicting NFL Performance based on Combine Results 

Problem & Context:
The NFL Scouting Combine is an annual event where college football players perform physical and mental tests in front of National Football League coaches, general managers, and scouts.  The purpose of the combine is to provide insight into the medical history, athletic
abilities, psychological state, as well as demonstrations of skill in positional drills of potential prospects.  It’s long been wondered do the results of these physical tests have any effect on future NFL Performance? The goal of this project is to predict individual players NFL performance based on Combine results.

Target Clients: 
The primary clients this project targets are NFL coaches, scouts, and general managers. The clients spend millions of dollars on the acquisition of talent every year when drafting players. The results of this project will hopefully aid them in picking potential players in the NFL Draft.   

Data:
The dataset that will be used for this project was created by Sports Viz Sunday  (https://data.world/sportsvizsunday) and posted on data.world.  The dataset comes in a single excel file with two sheets: one for NFL Combine results (10,228 rows, 16 columns) and one for NFL Draft results (8,435 rows, 34 columns). I’ll be using data from the years 1987 to 2015 in my project.  The dataset is available for download via the following link: https://data.world/sportsvizsunday/nfl-combine-data/workspace/file?filename=NFL+Combine+Data.xlsx

Constraints & Scope: 
Dealing with the different positions metrics that predict success. For example, the 40 yard dash may be a good indicator for NFL success for skill positions (WR, RB, DB) but not for a position like quarterback or offensive lineman.
Handling missing values in the combine dataset.  Many athletes only participate in select events at the combine, particularly quarterbacks.
Adding college stats would be helpful but might be beyond the scope of this project.

Approach: 
Multiple steps will be taken to build a predictive model for this project as well as to analyze the resulting predictions.
The excel file consisting of two sheets will be imported, merged, and cleaned via Python. Missing values and outliers will be handled appropriately based on specific factors.
The merged and cleaned dataset will be explored visually in order to find interesting trends/correlations in the data. 
A model to be determined will be employed on the dataset in hopes of predicting NFL Performance from Combine data. 

Deliverables: 
The final draft of the project will be presented in the form of a slide deck and formal project report . Jupyter Notebooks will be delivered detailing each step taken and code written for the analysis of the project. A Github repository for the project will be created as well.

