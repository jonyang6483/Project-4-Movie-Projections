</div>
<div align="center">

# Final Project - Movies & Box Office Performance Prediction
</div>

![pexels-tima-miroshnichenko-7991489](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/d67079ed-e8a7-4d05-9ff4-760bbeb9307d)                        

## Table of Contents
* [Presentation](#Presentation)<br>
    * [Movies & Predictive Revenue Success](#Movies-&-Predictive-Revenue-Success)<br>
    * [Technologies Used](#Technologies-Used)<br>
          *  [Data Cleaning and Analysis](#Data-Cleaning-And-Analysis)<br>
          *  [Database Storage](#Database-Storage)<br>
          *  [Machine Learning](#Machine-Learning)<br>
          *  [Dashboard](#Dashboard)<br>
* [Database](#Database)<br>    
    * [Dataset](#Dataset)<br>         
* [Machine Learning Model](#Machine-Learning-Model)<br>
    * [Question we would like to answer with our machine learning model](#Question-we-would-like-to-answer-with-our-machine-learning-model)<br>
    * [Machine Learning Model](#Machine-Learning-Model)<br>
    * [Output Label](#Output-Label)<br>
    * [Model Accuracy](#Model-Accuracy)<br>
    * [Data Preprocessing](#Data-Preprocessing)<br>
    * [How the model works](#How-the-model-works)<br>
* [Limitations & Looking Ahead](#Limitations-&-Looking-Ahead)<br>
    * [Limitations](#Ideas-for-further-development)<br>
    * [What are some possible improvements we could make?](#What-are-some-possible-improvements-we-could-make?)<br>


## Presentation

#### <ins><b>Movies & Predictive Revenue Success</ins></b><br> ####
For this repository we chose to explore movie & film datasets compiled from Kaggle. As a group, we selected this topic because obviously who doesn't love movies! But also because we were all very intrigued about the film industry's pre-production phase and what factors most likely help contibute to Movie Studios and Executives in making that final decision of greenlighting and developing a motion picture. With that being said, our final project aims to get a better understanding of the movie industy by exploring films that were both successful and profitable at the box office and further analyzing which factors those films had in common the most. For an in-depth look at our project, see our [Movies & Box Office Performance Prediction Presentation](insert slides link) on Google Slides.<br><br>

<div align="center">
   
</div>

#### <ins><b>Technologies Used</ins></b><br> ####

* ##### <b>Data Cleaning and Analysis</b><br> #####
  We performed our data transformation and analysis with Python and Pandas using Jupyter Notebook. All members of the group were     familiar with Pandas so this came as an easy decision and allowed the analysis to run smoothly. We created the Y variable as a success or failure on whether a movie had been able to earn back three times the movie’s budget. Creating the X-variables for the machine learning model we created a variable for the character count in the title of the movie, whether a movie was a sequel or not, we created an average score for the writer, director, and star of the movies equal to the sum of all their available movie scores divided by the count of their available movie scores.  We also group the directors, writers, stars, country, company, rating, and genre to remove entities with too few movies. Then we adjusted the budget and average ticket price by the yearly CPI rate to control inflation. Finally, we created dummies for non-numeric variables.<br>
* ##### <b>Database Storage</b><br> #####
  We used PostgresSQL for database storage and stored the database on render. Connections to our SQL database were created in our machine learning and data analysis notebooks.<br>
* ##### <b>Machine Learning</b><br> #####
  For the machine learning portion, we chose to use a SciKitLearn Random Forest model due to the algorithm's high degree of accuracy, the reduced chance of overfitting, and the need to use a supervised model..<br>.<br>
  ![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/c3be8eac-851c-4439-ae0f-51c17c7a593a)
![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/b5b16c42-4288-4436-b0ff-ec4ac01e2c13)

![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/fc35d6bf-ea3c-4886-9004-bd466f51d18a)

![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/63a63d00-21e3-4be5-abd7-ea64801f2945)

![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/3f224900-cd67-47cc-bdf9-90e5910f7e62)

![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/135b7c10-d20b-4075-9067-82f222c69dbf)

![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/e96f0213-f786-4227-8796-f68ee0d7018c)


![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/1d84ab6e-dabf-4e4e-8e0e-1fb6b4908259)

![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/2d93b54a-a1ff-45cf-ad80-e9247380c6a4)


![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/d48c5418-103f-4a58-b8ec-63aff32fe065)
  
* ##### <b>Dashboard</b><br> #####
  [Tableau Story](https://public.tableau.com/app/profile/christopher.lynch8861/viz/movie_success_2/Story1)<br>


</div>

</div>

</div>

## Database<br><br>

#### <ins><b>Dataset</ins></b><br> ####
(........)<br><br>

<div align="center">

</div>


## Machine Learning Model

#### <ins><b>Question we would like to answer with our machine learning model</ins></b><br> ####
The primary question we were trying to answer with our model is what makes a successful movie, there appears to be many factors determining the success or failure of a movie ranging from the actor, director or writer to even what time of year the movie is released.<br><br>
#### <ins><b>Machine Learning Model</ins></b><br> ####
(.........)<br><br>
#### <ins><b>Data Preprocessing</ins></b><br> ####
To preprocess the data, we pulled it off a database on render and created a data frame. We then split the release data and changed the date to a month format. We assigned the necessary datatypes to the data frame columns. Then created a character count column for the title of the movie. We extracted integer values from the movie title to look for sequels in the list. As well we created a score for each director, writer, and lead actor based on ratings. We assigned a 1 or 0 for success or failure in the success column based on gross exceeding three times the budget. We dropped the columns unnecessary for the analysis and dropped rows not meeting certain criteria budget under fifteen million or movies made prior to 1985 and dropped any columns with blank rows. We adjusted the budget and ticket prices based off the CPI and finally grouped the non-numeric categories based on representation per column.<br><br>
#### <ins><b>How the model works</ins></b><br> ####
(.........).<br><br>
#### <ins><b>Model Accuracy</ins></b><br> ####
(...........)<br><br>

<div align="center">
  


</div>


## Limitations & Looking Ahead

#### <ins><b>Limitations</ins></b><br> ####
(........)<br><br>
#### <ins><b>What Are Some Possible Improvements We Could Make?</ins></b><br> ####
(.........)<br><br>

<div align="center">
   
   
</div>
 


