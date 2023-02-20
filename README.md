# Amazon Reviewer Behavior Analysis and Prediction

## Overview:
In this project, the objective is to analyze Amazon reviewer behavior, using a large dataset of Amazon reviews spanning from 1998 to 2018. The initial phases of this project revolved around map-reducing the Amazon reviews, in order to aggregate reviewer information. During the EDA stages, I mainly looked at how reviewer behavior changed, based on how active they were. In the later stages of this project, the main goal was to predict the average rating of a reviewer, given a 1-star review given by them.

## Motivation:
Amazon products generally have uniqitous 4 and 5* reviews, and often times it is hard to know how good a product really is. Personally, I tend to look at the 1* reviews, to get a better understanding of what issues other customers had with the product. One thing I worry about though is that some users may just give 1* reviews across the board. I believe that 1* reviews from reviewers who generally give high ratings would be more informative.

## Data Pre-Processing (Map Reduce)
The biggest initial hurdle of this project was just processing the data, given it's sheer size (~230 million rows). This was all run locally on my computer, so I had to make sure to write code that would run in a reasonable timeframe.

[Initial Mapping](./Data_Processing/Process_Full_Dataset)
![InitialMap](./Readme_Images/initial_map.png)

<!-- ![Screenshot](./Readme_Images/reviewer_proportions.png) -->

<!-- https://cseweb.ucsd.edu/~jmcauley/datasets/amazon_v2/ -->