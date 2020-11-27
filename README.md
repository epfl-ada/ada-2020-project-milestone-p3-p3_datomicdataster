# ada-2020-project-milestone-p3-p3_datomicdataster
ada-2020-project-milestone-p3-p3_datomicdataster created by GitHub Classroom

**1. Title**: Does mobility make or break friendships?

**2. Abstract**
While the paper explores the effects of friendships on mobility, we propose to study the effects of mobility on friendships. To do so, we propose to use additional datasets capturing global-scale Check-in Data collected from Foursquare, another location based social network (LBSN). The dataset contains check-in information during a 22 month period with two snapshots of friendship data before and after the data collection period. This will let us evaluate the impact of mobility on making or breaking friendships. We will use techniques developed during the replication phase to determine home locations. From here we will categorise users according to their travel habits. We will also give check-in venues a “social score” allowing us to determine if a user and his mobility is socially oriented or not. This format will allow us to train and test a model that predicts the amount of friendships a user will create during the data collection period.


**3. Research questions**
Does mobility influence friendship dynamics?
Depending on the sociability of users, how does mobility influence friendships?
Can we predict / modelize the dynamics of friendships based on mobility and sociability of users?
Are users going to gain or lose friendships in the next 22 month period?

**4. Proposed datasets**
Global-scale Check-in Dataset collected from Foursquare
Two snapshots of user social networks before and after the check-in data collection period
Locations information from Foursquare


**5. Methods**
Compute users’ homes with a similar approximation as in our replicated paper:
Divide the world in grid cells (e.g. 25kmx25km)
Find the world cell with the most check ins for each user
Compute the home location by averaging the positions of all checkins inside the cell

Compute a “social score” for each Point of Interest:
Assign manually a social score (0 to 2 ) for each POI (=shop, restaurant, bar or other public places and stores):
Social score 0: The POI does not encourage social interactions, like a post office
Social score1: Social interactions and new meetings can occur in those POIs, like a restaurant
Social score 2: The POI is a social meeting place where there is a lot of social interaction, like a bar or a club
Automatically compute social scores based on mystic factors analysing the dataset


Determine the type of user (Traveler or not):
Depending on the number of checkins aboard, we either:
Compute and interpret the ratio aboard_checkins/local_checkins, by comparing it to a threshold
Or simply use a threshold on the number of aboard checkins instead of the ratio
Users are thus grouped into “Travelers” and “Locals”


Categorise users (into 4-6 groups)  according to the type of mobility (social-motivated or not) and the type of user (Travelers or not) 
For each type of user (“Travelers” and “Locals”):
Compute a social score for users’ mobility:
 Either with the average social score of its visited POIs
Or by comparing the number of POIs with the maximum social score (2) to a threshold
Or with by comparing the ratio  score_2_POIs/score_0&1_POIs with a threshold
Group each type of user into 2 or 3 social categories
At the end we have 4 to 6 categories of user


By using the snapshots of old and new friendships, we train a model in order to predict the dynamics of friendships.
We use K-fold methods to increase accuracy





**6. Proposed timeline**

**Week 1**: Download the datasets and get familiar with them. 
Prepare the data by cleaning it and exploring it to make it usable for the analysis. 
Make a simple analysis and some quick visualisations to develop hypotheses.
All members finish their second part of the replication

**Week 2**: Develop and train a model that will predict the number of new connections a user will have after the data-collection period.
Test this model on a testing set.
Improve the accuracy of this model by tuning hyperparameters, etc
Start to look at how Jekyll works (we will be making a data story and not a pdf report)

**Week 3**: Continue with the analysis and the improving of the model, get ready to implement our story on our website. 
Build the website. 
Make a short video presenting our work




**7. Organization within the team**

During week 1, Thomas will work on merging the different datasets together, cleaning the data to make it ready for the analysis. 
In parallel, Shadi will get an understanding of how Jekyll works by following tutorials and reading the documentation, and will start making a quick template of the data story.

During week 2, after the data is clean and the website is thought of, Leo will start making a first analysis of the dataset and try to answer some the questions we have defined. Shadi will work with him to create a model calculating how many friends a particular user will make / lose. These two team members will try to improve the accuracy of the model as best as they can (by tuning the hyperparameters, try out different methods, etc). 

During week 3, all team members will work together to finalise the analysis and write the story on the website. Thomas will take lead this step and will also make the short video (as his native language is english)

Questions for TAs (optional)
Shall we give each venue an empirical “social score” ourselves, or should we calculate it according to check-in and friendship data?
