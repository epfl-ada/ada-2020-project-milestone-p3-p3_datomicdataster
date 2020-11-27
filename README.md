# ada-2020-project-milestone-p3-p3_datomicdataster
ada-2020-project-milestone-p3-p3_datomicdataster created by GitHub Classroom

**1. Title**: Does mobility make or break friendships?<br>

**2. Abstract**<br>
While the paper explores the effects of friendships on mobility, we propose to study the effects of mobility on friendships. To do so, we propose to use additional datasets capturing global-scale Check-in Data collected from Foursquare, another location based social network (LBSN). The dataset contains check-in information during a 22 month period with two snapshots of friendship data before and after the data collection period. This will let us evaluate the impact of mobility on friendships. We will use techniques developed during the replication phase to determine home locations. From here we will categorise users according to their travel habits. We will also give check-in venues a “venue social score” allowing us to determine if a user and his mobility is socially oriented or not. This format will allow us to train and test a model that predicts the amount of friendships a user will make or break during the data collection period.


**3. Research questions**<br>
* Depending on the social behaviour of users, how does mobility influence friendships?<br>
* Can we modelise and predict the dynamics of friendships based on user habits?<br>
* What factors will cause users to gain or lose friendships in a defined 22 month period?<br>

**4. Proposed datasets**<br>
* Global-scale Check-in Dataset collected from Foursquare<br>
* Two snapshots of user friendship networks before and after the check-in data collection period<br>
* Venue information from Foursquare<br>

<a href=https://drive.google.com/file/d/1PNk3zY8NjLcDiAbzjABzY5FiPAFHq6T8/view>Click here to access dataset</a>

**5. Methods**<br>
Compute users’ homes with a similar approximation as in our replicated paper:<br>
* Divide the world in grid cells (e.g. 25kmx25km)<br>
* Find the world cell with the most check ins for each user<br>
* Compute the home location by averaging the positions of all checkins inside the cell<br>

Compute a “venue social score” for each Point of Interest:<br>
* Either by manually assigning a score (0, 1 or 2 ) for each venue (eg. shop, bar, post office...) according to the level of social interaction in said venue.<br>
* Or by computing the social scores based on factors such as popularity, average time of check-ins, frequency of visits, etc.<br>

Determine two clusters of users: frequent travelers or not. Depending on the number of checkins abroad, we will compute and interpret the following to determine clusters:<br>
* The ratio of abroad_checkins/local_checkins<br>
* The ratio of abroad_checkins/total_checkins<br>
* Simply the number of abroad_checkins<br>

Categorise the users within the two clusters according to their type of mobility (social-motivated or not). <br>
We will compute a "user social score" according to their habits, for example we would do one of the following (**for each individual user**):
* Use the average social score of their visited venues<br>
* Use the ratio of max "venue social scores" and total checkins: user_score = sum(venue_score==2)/(total_checkins)<br>
* Use the value of the most frequent social score<br>
* Compare the ratio of max "venue social scores" and other "venue social scores": user_score = sum(venue_score==2)/sum(venue_score==0 or 1)<br>

This will allow us to group each user into social categories<br>

By using the snapshots of old and new friendships, we train a model in order to predict the dynamics of friendships, considering the traveler or not clusters as well as their social score. We will use cross validation and other selected methods to improve our predication accuracy.<br>

**6. Proposed timeline**

**Week 1**: Download the datasets and get familiar with them. <br>
Prepare the data by cleaning it and exploring it to make it usable for the analysis. <br>
Make a simple analysis and some quick visualisations to develop hypotheses.<br>
All members finish their second part of the replication<br>

**Week 2**: Develop and train a model that will predict the number of new connections a user will have after the data-collection period.<br>
Test this model on a testing set.<br>
Improve the accuracy of this model by tuning hyperparameters, etc.<br>
Start to look at how Jekyll works (we will be making a data story and not a pdf report)<br>

**Week 3**: Continue with the analysis and the improving of the model.<br>
Build the website. <br>
Make a short video presenting our work<br>

**7. Organization within the team**

During week 1, Thomas will work on merging the different datasets together, cleaning the data to make it ready for the analysis. <br>
In parallel, Leo and Shadi will get an understanding of how Jekyll works by following tutorials and reading the documentation, and will start making a quick template of the data story.<br>

During week 2, after the data is clean and the website is thought of, Leo will start making a first analysis of the dataset and try to answer some the questions we have defined. Shadi will work with him to create a model calculating how many friends a particular user will make / lose. These two team members will try to improve the accuracy of the model as best as they can (by tuning the hyperparameters, try out different methods, etc). Thomas will start writing text for the data story.

During week 3, all team members will work together to finalise the analysis and write the story on the website. Thomas will take lead this step and will also make the short video (as his native language is english).

**8. Questions for TAs (optional)**
Shall we give each venue an empirical “venue social score” ourselves, or should we calculate it according to check-in and friendship data?
