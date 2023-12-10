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
Below are all of the imports regarding this project, we can see Numpy, Pandas, and Matplotlib, as well as Seaborn.
![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/f60a03a3-e883-4f9d-bffa-31d05741c1b2) <br>

## Results

# Question 1: Do newer games tend to have more positive reviews? <br>
This question is highly relevant, however, the data provided has ratings stored not on a scale from 1-10, but rather on a verbose scoring method ranging from 'Overwhelmingly Negative' to 'Overwhelmingly Positive'. This rating scale was frustrating to use because not only is it difficult to visualize but the terms have no real meaning beyond conversational use. Thankfully, Steam uses 9 of these terms, so I mapped each of these inputs to a value 1-9. Mapping these values allows me to attribute a numeric value to the ratings and thus graph them on a scale. <br>
![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/b5207ff1-908e-46a9-9e0b-079b09f6ec0e)

<br>

### First Attempt
My first approach to answering this was to simply take the means of each year and graph them, which is what the following chart does. <br>

![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/479df234-c175-48f4-b590-25ed85317622) <br>
At first glance at this chart, a viewer would immediately see that newer games have a significantly lower mean score.
<br>
<br>

### Second Attempt
<br>
The second approach to finding useful data from this was to implement not only a different numerical strategy but a different form of graph. During my work on the group project, I began to enjoy using boxplots and boxenplots, I think that they give a digestible view of the present data. Knowing this, I made the next chart using one and decided that graphing means was only so useful and included all of the data instead of the mean for each year. <br>

![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/05b75ac4-0c75-46a8-82c1-75e998762f86)

### Final Attempt
<br>
This data set not only has the 9 levels of rating but also a 'positive_ratio' column, which denotes specifically what percentage of the reviews for this game are positive. Positive ratio could be a useful metric for measuring how well-liked a game is, it certainly provides more detail than a 1-9 scoring system. <br> 
I graphed this using release year as X and Positive Ratio as Y and was given the following graph:

![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/ab5ea648-1ba4-4450-b5e6-80f27841d031)


## Question 1 Conclusion
The reasonable conclusion for question one seems to be that there is a slight preference for older games. The first graph shows this intensely, however, that graph shows very little information; using only the mean for each year and not giving a range for the values. <br>
The second and third graphs show a much smaller difference between older and newer games. I attempted to use a graph that employed a line of best fit, but unfortunately due to the sheer volume of newer games, it failed to truly account for the weight of older games.

# Question 2: Are certain operating systems more likely to have games that are rated higher? <br>
This question is straightforward, and the provided data set works amazingly to answer it. The dataset has 3 columns, 'win', 'mac', and 'linux' to cover the 3 Operating Systems that are supported by Steam. These columns have one of two values, TRUE or FALSE, denoting wether or not said game can be run on the Operating System. <br>
By simply only taking input from rows where the value was TRUE for only one of the Operating Systems we can determine which one runs the highest-rated games.

This first graph uses the numeric scoring that we created for question one and then takes games that can run on Windows. We see that most of these games score somewhere from 5-7 with some outliers present. 
![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/fd60cc76-ebc2-413c-88a1-80d21b1f1ba9)

The second graph is for Linux machines. 

![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/b6b9669a-ce9d-41a7-9272-4b2b3dfe53a4)

There are so few games that run on only Linux that the score was exactly 5

Finally, we have Mac, unfortunately there were no games that ran exclusively on Mac that are available on the Steam store. 

## Question 2 Conclusion
Unfortunately for those who decide to game on either a Linux or Mac machine, the data seems to support that Windows based machines not only have the highest scores but also the most games available. <br>
Thankfully, that graph was showing games that only supported one of the listed operating systems. There are thousands of games that support 2 or more of the available operating systems. <br>
![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/96cda953-556f-4cc4-aee4-b734a9e50389)
However, the conclusion is still the same: For Steam-based gaming, Windows offers the most high-scoring games. 

# Question 3: Is price correlated to a higher or lower rating?
I again used the numeric rating system from the first question to answer this question. However, there were some pieces of software available on steam that had listed prices up to $300, which I will show in the first graph. <br> 
In later attempts, I set a hard limit on the max price to $100 as most games are at or below this threshold. This action has minimal changes to the final result, but it does improve the legibility of the graph by quite a bit

### Attempt 1
![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/6b3823e2-5ebe-4c50-9d74-f7b9d8c21742)

As we can see in this graph, we have some values that range from $150 to $300. I believe that this is due to software being listed on Steam that is intended for Industry-scale use, and as a result, I removed it from my graphs.

### Attempt 2
![image](https://github.com/Alaskanwildman/DataScienceFundProjVernonn/assets/31549358/b7318973-a450-468e-b515-9586163e8947)

In the second attempt, I set the maximum cost to $100, removing many of the outliers. <br>
Interestingly we can see a spike in price from a rating of 3-4, jumping all the way up to $100. Additionally the rating of 1 caps off at $30. Many of the other ratings tapper off around $60, which is to be expected as that is the industry standard price for a newly released game. <br>

## Question 3 Conclusion
This question I found to be the most informative and surprising. The spike around 3-4 was not an outcome that I would have predicted before this project. 





