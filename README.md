# Natural Language Processing (NLP) to Analyze Product Reviews for Online Shoppers

The main business objectives for the project are:
- to reduce dimensions while retaining as much information as possible using principal components for "bag-of-words"
- to predict product ratings based on explicit reviews, using ordinal logistics regression
- to recommend products to online shoppers based on similarity algorithm (Euclidean)

## Data Characteristics
- reviewerID - ID of the reviewer, e.g. A2SUAM1J3GNN3B
- asin - ID of the product, e.g. 0000013714 
- reviewerName - name of the reviewer 
- helpful - helpfulness rating of the review, e.g. 2 out of 3 people found the review to be helpful. The starter code’s dataframe would have 2 in the helpful_start column and 3 in the helpful_end column 
- reviewText - text of the review 
- overall - rating of the product 
- summary - summary of the review • unixReviewTime - time of the review
<p align="center">
<img src="https://github.com/Aijieli/Natural-Language-Processing-NLP-to-Analyze-Product-Reviews-for-Online-Shoppers/blob/master/images/data%20snap.png" width="800" height="200">
</p>

## Key Results and Findings

We ran a PCA and graphed the first two PCs for the first 100 reviews. However, after transformation, the distance between different reviews changed a lot. The graph doesn’t reflect the findings in part 5. As the first two principal components explained only 13% the overall variance, it is quite low and leads to the change.

<p align="center">
<img src="https://github.com/Aijieli/Natural-Language-Processing-NLP-to-Analyze-Product-Reviews-for-Online-Shoppers/blob/master/images/PCA.png" width="450" height="400">
</p>

So we used "bag-of-the-words" to put into the model. We used logistic regression to predict the rating of a product here. As the rating is ordinal data, we applied ordinal logistic regression to predict the overall ratings.


<p align="center">
<img src="https://github.com/Aijieli/Natural-Language-Processing-NLP-to-Analyze-Product-Reviews-for-Online-Shoppers/blob/master/images/ordinal%20logistic%20regression%20function.png" width="600" height="200">
</p>

The disadvantage to run multinomial regression model lies in that the ordering information is thrown away. However, as shown by the above equation, the logarithms in ordinal logistic regression form an arithmetic sequence, thus preserving the ordering information. 
