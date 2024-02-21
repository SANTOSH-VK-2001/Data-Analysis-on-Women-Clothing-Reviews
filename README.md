
# Data Analysis on Women Clothing Reviews

Data Analysis on Women Clothing Reviews in sentiment analysis


## Project Description and Objectives
For our project, we are going to use the dataset of women’s e-commerce clothing reviews to perform analytics. Our research can be split into three parts. First, we are looking into the relationship between classes / departments and recommendations to see what kind of classes / departments got relatively positive or negative reviews. Second, we are going to conduct sentiment analysis and produce word clouds to look into positive and negative words. Lastly, we are going to build different predictive models and see how the models perform.
## Challenges
During the journey of working on our projects, we overcame two main challenges below. Firstly, we found that the dataset was imbalanced between the recommended and not recommended comments. In order to solve the problem, we used SMOTE to oversample the data in the “negative” class. After the oversampling, we were able to build further different models, and compared and evaluated their performances.

Second, we also encountered the challenge of how we evaluate different models as a consistent benchmark. Due to the advantages of the ROC curve, we decide to use it as a criterion to indicate the performance of multiple models at all classification thresholds. With higher AUC scores, which compound score is higher than 0.5, we are able to measure the better performances of the models.

Second, to optimize the model Decision Tree, we used Grid Search and Randomized Search for the optimal parameters for the model. However, the accuracy rate and auc was lower than the result from the default parameters. The reason may be related to the range of the value of parameters we chose for the process of Grid Search and Randomized Search.

## Data Descriptions


 - [Kaggle](https://www.kaggle.com/datasets/nicapotato/womens-ecommerce-clothing-reviews?select=Womens+Clothing+E-Commerce+Reviews.csv)

 This dataset is real commercial data, it includes 11 feature columns and 23486 rows. Every row represents a customer review.


 
## Data Preprocessing
We then drop unnecessary columns and rename the rest of the columns for further analysis.
## Text Processing
For text processing, first we remove all the punctuation and special characters in the reviews. By doing so, we can preclude those buzz words, which is a preparation for further classifying. Next, we convert all the uppercase words into lowercase words. Finally, we remove the stopwords, which are also considered buzz characters in this case.


## Data Exploration
By performing exploratory data analysis, we examine the distribution of positive and negative reviews by different types of clothes, division, ratings, and so on. The way we tell if this review is positive or not is based on whether a customer would recommend the product. “Recommended_IND” is a binary variable stating where the customer recommends the product where 1 is recommended, while 0 is not recommended.

Below are the bar charts of “Division_Name”, “Class_Name”, “Department_Name”, and “Rating’’ by “Recommended_IND”.

## Sentiment Analysis
Next, we apply VADER for our sentiment analysis. We use compound score as the main scoring for our text.
Then we set 0.05 and -0.05 as our thresholds to categorize the texts. We assign text with compound score larger than 0.05 as positive text, compound score smaller than -0.05 as negative text, others as neutral text.
Next, we drop the neutral text and get a new dataframe with only the Review_Text and Label.
Lastly, we update stopwords with some frequently appeared words, and then produce word clouds for the positive and negative reviews.




## Predictive Modeling
Because there are 15152 positive rows and 485 negative rows, the dataset is imbalanced. To solve this problem, we used SMOTE to oversample the data in the “negative” class. After the process, the amount of both two classes are 15152 rows.
Then, we built 4 models and made predictions. The 4 models are: Logistic Regression, Naive Bayes, Decision Tree and Random Forest.
To compare the performance of prediction of the models, we calculated Accuracy, Recall, F1-Score, Confusion Matrix, ROC and AUC for every model.


## Conclusion
Compared to the different performance of each model we used, the model using Logistic Regression performs the best. Because its AUC score and F1-Score are the highest, 0.82 and 0.96 among all.
From those charts and tables presented above, we conclude the following points. Firstly, the women’s e-commerce platform can expand the amount of product by producing larger sizes of apparels. Moreover, customers do value the importance of product quality, which reflects on higher ratings and more positive reviews. The platform should make more efforts to improve and maintain its consistent product quality so that the platform can attract new potential customers.
Hopefully, as long as the platform is willing to adjust and adapt to the trends nowadays, it leads to higher profits, better reputation and loyalty to the platform.
## Documentation

[Documentation](https://santosh2001.notion.site/Women-s-E-Commerce-Clothing-Reviews-f74baf323d0249e9becb3706377f89d4?pvs=4)

