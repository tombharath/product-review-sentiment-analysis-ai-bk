# Product Review Sentiment Analysis


**Executive Summary**

The project's goal is to predict customer sentiment based on the review of the products the customer provides. 
By analyzing these reviews, we can identify the intent of why the customer has given the reviews. These insights can contribute to what companies can do to improve their negative review product and what they can continue 
to do based on the positive comments for their product development and marketing strategies to increase overall sales. This analysis involves efficiently processing large text data using Natural Language Processing 
to identify the sentiments of the customer review comments. Implementing this model can significantly contribute to increased trust and loyalty with the customer.

**Code**

- Refer to [Product-Reviews-Sentiment-Analysis.ipynb](https://github.com/tombharath/product-review-sentiment-analysis-ai-bk/blob/main/Product-Reviews-Sentiment-Analysis.ipynb) jupyter notebook for the code.
- The code uses Plotly express libraries. As GitHub doesn't display plotly chart correctly. The renderer is used to show it as a picture.
- You can change the fig.show("png") to fig.show() in the jupyter notebook python code to have the hover functionality while running it.

**Business Objective**

The business objective is to find a model that predicts customer sentiment based on the review comments. Identifying the intent (feature weight of the words) can provide insights that can contribute to product development, marketing strategies, 
and improvement of customer services. This type of model can help to increase trust and loyalty with the customer thereby increasing Sales and Customer Satisfaction

**Data Understanding**

- The Dataset used in this project is sourced from Kaggle https://www.kaggle.com/datasets/datafiniti/consumer-reviews-of-amazon-products/data
- This is a list of over 67,000 consumer reviews for Amazon products like the Kindle, Fire TV Stick, and more provided by Datafiniti's Product Database.
- The dataset includes basic product information, rating, review text, and more for each product.

![Screenshot 2024-07-05 at 10 32 16 AM](https://github.com/tombharath/product-review-sentiment-analysis-ai-bk/assets/37302704/5577f88b-a084-471f-89b7-f49d78937960)

**Exploratory Data Analysis**
- There are 641 duplicates which got removed as the dataset has 67K records
- The missing values of the name are filled with the name from the categories field
- Standardized the naming for the Product Name
- Distribution of Rating Scores
  
![Screenshot 2024-07-05 at 10 45 01 AM](https://github.com/tombharath/product-review-sentiment-analysis-ai-bk/assets/37302704/3f331a6b-2f97-49a1-99b8-7ed9684442cc)

- Distribution of Review done by date

![Screenshot 2024-07-27 at 6 34 56 PM](https://github.com/user-attachments/assets/761a9507-83c0-4cb6-97f4-735abfc86cb0)

- Number of users given ratings for the products

![Screenshot 2024-07-27 at 6 38 04 PM](https://github.com/user-attachments/assets/37a442c4-ace0-418b-9d95-f859b4cf17b4)

- Distribution of Ratings by Product

![Screenshot 2024-07-05 at 10 45 50 AM](https://github.com/tombharath/product-review-sentiment-analysis-ai-bk/assets/37302704/7474697b-3f2c-4d6f-aea0-da9414e9db73)

- Distribution of Ratings by Manufacturer

![Screenshot 2024-07-27 at 6 40 04 PM](https://github.com/user-attachments/assets/f0c658b7-d77a-4a51-abb5-4caae6c6c07a)

- Users recommended the product

![Screenshot 2024-07-27 at 6 40 35 PM](https://github.com/user-attachments/assets/1fc079fb-6aa8-46c7-b31b-f24365937f37)

- Character Count in the Review Text

![Screenshot 2024-07-05 at 10 46 44 AM](https://github.com/tombharath/product-review-sentiment-analysis-ai-bk/assets/37302704/7f01e5f6-58d8-4f04-a116-fef49cc826ab)

- Distribution of Sentiment
  
![Screenshot 2024-07-05 at 10 47 11 AM](https://github.com/tombharath/product-review-sentiment-analysis-ai-bk/assets/37302704/117314f9-070d-4c34-8908-6208a946ecec)

**Data Preprocessing**

- Mapped the Sentiment based on the review rating fields to positive or negative 
- Sentiment and review text fields are used for the Analysis.
- Split the dataset for the train and test set with a 75 % ratio.
- Changed to text lowercase
- Punctuations, Numbers and Stop words removal
- Stemmed the review text.
- TDIDF is used for Feature Extraction
  
**Modelling**

The following models have been evaluated to compare the performance

- Logistic Regression
- Decision Tree
- Naive Bayes
- Support Vector Classifier
- Random Forests
- XGBoost

**Baseline Model**

- The accuracy of the Baseline classifier for train dataset is 92.09%
- The accuracy of the Baseline classifier for test dataset is 91.87%


**Model Comparision**

Below is the performance of each model with the default settings of the model.

![Screenshot 2024-07-27 at 6 43 42 PM](https://github.com/user-attachments/assets/c66feaa6-2d37-4771-93eb-8283c0818c69)


**Model Tuning**

- Hyperparameter tuning and grid search. All of our models have additional hyperparameters to tune and explore
- Below are the tuning parameters used for each of the models
  - Logistic Regression
    - penalty : ['l1', 'l2', 'none']
    - solver : ['liblinear', 'newton-cg', 'lbfgs']
    - C : [0.1,0.01,0.001]
  - Decision Tree
    - min_samples_split : range(2,10,2)
    - criterion : ['gini','entropy']
    - min_samples_leaf : range(1,10)
  - Naive Bayes
    - alpha : [1, 0.1, 0.01, 0.001, 0] 
  - Support Vector Classifier
    - C : [0.1] 
  - Random Forests
    - n_estimators : [1, 10, 100, 500, 1000]
    - max_depth : [1, 2, 3, 4, 5, None]
  - XGBoost
    - n_estimators : [1, 10, 100, 500, 1000]
    - max_depth : [1, 2, 3]
- As Dataset is imbalanced we will calculate the F1 score and Recall score to evaluate the model
- Recall and F1 score calculation for each model
- Below is the summary of the performance of models after tuning
  
![Screenshot 2024-07-27 at 6 52 03 PM](https://github.com/user-attachments/assets/1db9cdab-4da0-4c4d-8ba2-0744f79c8e30)

- Below is the ROC Curve of each Model

![Screenshot 2024-07-27 at 6 53 35 PM](https://github.com/user-attachments/assets/abe0e3ee-fe51-47f0-a86d-87461777c866)

- Below is the Confusion Matrix of the Models

![Screenshot 2024-07-27 at 6 54 30 PM](https://github.com/user-attachments/assets/b4644b0b-fe27-4353-b37b-4a4c9f5142cc)

**Model Evaluation**

- The dataset is imbalanced hence Recall score and F1 score are considered in addition to the best score.
- Used recall as missing out the potential negative review comments from the customer will impact the business goal
- Naive Bayes seems to be better for the given dataset in the case of the performance parameters.
- Based on the Model Analysis all the models have a Recall score of greater than 97 % and SVC has the highest Recall score.
- The F1 score and best score of Random Forests is better than the SVC.
- The ROC Curve shows the Random Forests has a better trade-off between the Precision and Recall.
- The Random Forests seem to be the best model based on the above findings


**Next Steps and Recommendations**

- The Feature weights show the high weightage words in the review comments are return,don't, great, slow, last, love, ok and batteri.
- The Positive word cloud shows easi, use, great and work. It shows the Positive comments are ease of use and work of the product to continue to focus on.
- The Negative word cloud shows the batteri, use, tablet, replace and price. It shows most of the negative comments are based on Battery usage on tablet and price.
- The Product team can focus on improving the battery usage of tablet and continue the ease of use of products.
- The Marketing team can focus on the pricing options to act on the negative feedback
- The models can be executed after 6 months of new release to see if addressing the feedback on the product helped the customer sentiment or not.
- The Future work on developing the Deep Neural Network model to train and check the performance and improvement of the models.
