# Hidden correlations in Steam Game reviews
 Steam is an online platform that many people use to purchase video games. <br>
 Users can leave reviews on games so that other users can make informed purchases.<br>
 I have 3 questions that I will use the metrics of said reviews to answer

## Questions
1) Do newer games tend to have more positive reviews?
2) Are certain operating systems more likely to have games that are rated higher?
3) Is price correlated to a higher or lower rating?

## Data set
The data set is "Game Recommendations on Steam", uploaded to Kaggle by Anton Kozyriev.<br> 
This is an extremely up-to-date data set, with the last update being 20 days ago. <br>
https://www.kaggle.com/datasets/antonkozyriev/game-recommendations-on-steam <br>
Thankfully the data provided by Anton is excellent, it comes extremely usable with no editing required to begin this project. 

## Methodology
Similar to the group project I will be using Numpy, Pandas, and Matplotlib to interact with and visualize the data. <br>
Below are all of the imports regarding this project, we can see Numpy, Pandas, and matplotlib, as well as Seaborn.
![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/f60a03a3-e883-4f9d-bffa-31d05741c1b2) <br>

## Results
Question 1: Do newer games tend to have more positive reviews? <br>
This question is highly relevant, however, the data provided has ratings stored not on a scale from 1-10, but rather on a verbose scoring method ranging from 'Overwhelmingly Negative' to 'Overwhelmingly Positive'. This rating scale was frustrating to use because not only is it difficult to visualize but the terms have no real meaning beyond conversational use. Thankfully, Steam uses 9 of these terms, so I mapped each of these inputs to a value 1-9. Mapping these values allows me to attribute a numeric value to the ratings and thus graph them on a scale. <br>
<br>
### First Attempt
<br>
My first approach to answering this was to simply take the means of each year and graph them, which is what the following chart does. <br>

![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/479df234-c175-48f4-b590-25ed85317622) <br>
At first glance at this chart, a viewer would immediately see that newer games have a significantly lower mean score.
<br>
<br>

### Second Attempt
<br>
The second approach to finding useful data from this was to implement not only a different numerical strategy but a different form of graph. During my work on the group project, I began to enjoy using boxplots and boxenplots, I think that they give a digestible view of the present data. Knowing this, I made the next chart using one and decided that graphing means was only so useful and included all of the data instead of the mean for each year. <br>

![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/05b75ac4-0c75-46a8-82c1-75e998762f86)

