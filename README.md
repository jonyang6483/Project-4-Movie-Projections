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
  
The initially we cleaned the dataset by separating the month from the released date. We also dropped any null values within the columns and rows. Through several testing of the hidden layers the most optimized was 3 layers with 20 neurons, 8 neurons, and 1 neuron respectfully. The sigmoid function was used since the data model is predicting if a movie will gross three times the budget. This resulted in an accuracy of .5595325231552124 <br>


![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/c3be8eac-851c-4439-ae0f-51c17c7a593a)

![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/b5b16c42-4288-4436-b0ff-ec4ac01e2c13)

Following the next attempt to increase the accuracy of our data model, we began by grouping the director, and the score then dividing it by the total number of movies they were involved in. Thus, creating the 'director_number' values. We then continued the same calculations for writer and stars by grouping them with their respected score and dividing it by the total number of movies. This created two more variables 'writer_number' and 'star_number.' The data model was then built with these additional data points increasing the accuracy to .6018992066383362.<br>

![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/fc35d6bf-ea3c-4886-9004-bd466f51d18a)

After adding additional data points for building the data model we then changed the name of the movie to the quantity (length) of characters within the title using the variable 'title_char.' This change in the dataset increased the accuracy to .6435354351997375<br>



![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/63a63d00-21e3-4be5-abd7-ea64801f2945)

Next, we attempted to group sequels together by extracting movie titles with a numerical value creating the 'sequel' column. Afterward, additional filtering of data into other categories to minimize outliers within the dataset.  This increased the accuracy to 0.6990504264831543

![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/3f224900-cd67-47cc-bdf9-90e5910f7e62)

Deep diving further into the dataset we realized their were smaller indy films and some older films that may effect the accuracy, so we set the budget to greater than 15 million and greater that 1985. We also made adjustments to the cpi by dividing the budget by the cpi and the ticket price by the cpi to account for inflation. We then changed the third layer to the relu function for the deep learning model. These changes increased the accuracy to 0.7412935495376587
![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/1d84ab6e-dabf-4e4e-8e0e-1fb6b4908259)

![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/2d93b54a-a1ff-45cf-ad80-e9247380c6a4)

Finally, we altered the original filtering of director, writer, star, country, company, rating, and genre. We also changed the datamodel back to all sigmoid functions for the datamodel. This increased the accuracy of our datamodel to 0.7559153437614441.
![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/2aa3d7fc-ef47-42c0-be6a-51cbe73d61f7)


![image](https://github.com/jonyang6483/Project-4-Movie-Projections/assets/117343047/d48c5418-103f-4a58-b8ec-63aff32fe065)
  
* ##### <b>Dashboard</b><br> #####
  We used Tableau to build our Dashboard and [Story](https://public.tableau.com/app/profile/christopher.lynch8861/viz/movie_success_2/Story1)<br>

</div>

## Database<br><br>

</div>

#### <ins><b>Dataset</ins></b><br> ####
Our raw dataset contained almost 7,700 rows and 15 columns of information that included the movie title, rating, genre, year released, director, writer, budget, and etc. Then after we finished cleaning and transforming the data, our final dataset contained 3217 rows and 19 columns.<br><br>

<div align="center">

</div>


## Machine Learning Model

#### <ins><b>Question we would like to answer with our machine learning model</ins></b><br> ####
The primary question we were trying to answer with our model is what makes a successful movie, there appears to be many factors determining the success or failure of a movie ranging from the actor, director or writer to even what time of year the movie is released.<br><br>
#### <ins><b>Machine Learning Model</ins></b><br> ####
We chose a random forest model since we needed a supervised learning model. Random forest algorithms are great to use for classification or regression problems and typically produce a higher degree of accuracy. The model does a good job to avoid overfitting and it can efficiently handle large datasets like ours. The biggest downside to using this type of model is computing time. The model can take hours to fit to the training data making it very time consuming to optimize.<br><br>
#### <ins><b>Data Preprocessing</ins></b><br> ####
To preprocess the data, we pulled it off a database on render and created a data frame. We then split the release data and changed the date to a month format. We assigned the necessary datatypes to the data frame columns. Then created a character count column for the title of the movie. We extracted integer values from the movie title to look for sequels in the list. As well we created a score for each director, writer, and lead actor based on ratings. We assigned a 1 or 0 for success or failure in the success column based on gross exceeding three times the budget. We dropped the columns unnecessary for the analysis and dropped rows not meeting certain criteria budget under fifteen million or movies made prior to 1985 and dropped any columns with blank rows. We adjusted the budget and ticket prices based off the CPI and finally grouped the non-numeric categories based on representation per column.<br><br>
#### <ins><b>How the model works</ins></b><br> ####
After the data was cleaned and transformed. The data was then split using scikit-learn’s Train Test Split method into 75% training data and 25% testing data. Finally, the model was fit to the data. This was the most time-consuming part of the process.<br><br>
#### <ins><b>Model Accuracy</ins></b><br> ####
Final Model Accuracy: 75.6 <br><br>

<div align="center">
  


</div>


## Limitations & Looking Ahead

#### <ins><b>Limitations</ins></b><br> ####
Some of the limitations working with this dataset was the lack of numerical values and the significant number of unique writers, actors, and directors. Additionally there was no information about revenue recieved
outside of theaters such as streaming revenue or dvd sales. As well, there was no cost breakdown so there was no way to tell where the expenses were incurred in each movie.<br><br>
#### <ins><b>What Are Some Possible Improvements We Could Make?</ins></b><br> ####
One possible improvement that comes to mind is to look only at movie budgets in certain ranges and adjust the success or failure ratio accordingly, this could increase accuracy due to movies with diffrent budgets 
likely having significantly diffrent criteria for success.<br><br>

<div align="center">
   
   
</div>
 


