# Amazon Reviewer Behavior Analysis and Prediction

## Overview:
In this project, the objective is to analyze Amazon reviewer behavior, using a large dataset of Amazon reviews spanning from 1998 to 2018. The initial phases of this project revolved around map-reducing the Amazon reviews, in order to aggregate reviewer information. During the EDA stages, I mainly looked at how reviewer behavior changed, based on how active they were. In the later stages of this project, the main goal was to predict the average rating of a reviewer, given a 1-star review given by them.

## Motivation:
Amazon products generally have uniqitous 4 and 5* reviews, and often times it is hard to know how good a product really is. Personally, I tend to look at the 1* reviews, to get a better understanding of what issues other customers had with the product. One thing I worry about though is that some users may just give 1* reviews across the board. I believe that 1* reviews from reviewers who generally give high ratings would be more informative.

# Data Pre-Processing (Map Reduce)
The biggest initial hurdle of this project was just processing the data, given it's sheer size (~230 million rows). This was all run locally on my computer, so I had to make sure to write code that would run in a reasonable timeframe.

## [Initial Mapping](./Data_Processing/Review_Mapping.ipynb)

This initial mapping converted the numerical rating into a count column format, which would be easier to reduce in later stages.

![InitialMap](./Readme_Images/initial_map.png)

## [Reducing by ReviewerID](./Data_Processing/Reduce_Reviewer_Data.ipynb)
In this stage, the mapped review information was reduced by reviewerID, resulting in a table with reviewerIDs, and the numbers of each ratings that they gave.

![ReviewerReducing](./Readme_Images/reviewer_reducing.png)

## [Reviewer Stat Generation](./Data_Processing/Reviewer_Feature_Engineering.ipynb)
At this point, the ~230m reviews have been condensed into ~43m rows, each representing a reviewer, and the number of each rating they have given. It is now possible to calculate some reviewer metrics: such as the number of reviews they have given, as well as the average rating they have given.

![ReviewerStatGeneration](./Readme_Images/reviewer_stat_generation.png)

## Reviewer EDA
I was very curious to see how Reviewer behavior changed, based on how many reviews they have given.

It seems like almost half of the reviewers gave only 1 review.
![ReviewerProportions](./Readme_Images/reviewer_proportions.png)

This was perhaps the most interesting finding of the EDA. It seems like the average review steadily increases with the number of reviews given. It is likely that there are a lot of users who generally don't post reviews, but encountering a product that they really don't like can sway them into leaving a negative review. Reviewers that post more reviews tend to give higher ratings on average.
![AvgRatingVsNumReviews](./Readme_Images/avg_rating_by_num_reviews.png)

## Active Reviewer EDA

I'm specifically interested in where the 1* ratings are coming from, whether it is from a small proportion primarily giving low ratings, or a large proportion on average giving higher ratings -- but sometimes giving lower ratings. Because I'm looking at average ratings per reviewers, I want to focus on reviewers who gave between 5 and 15 reviews. These will be called "active reviewers". Looking at the average rating of a reviewer who has only given 1 or 2 reviews might not produce a meaningful average rating, and looking at reviewers who gave dozens of reviews might not be representation of the reviewer population.

![1StarReviewSources](./Readme_Images/1_star_source.png)

<!-- https://cseweb.ucsd.edu/~jmcauley/datasets/amazon_v2/ -->