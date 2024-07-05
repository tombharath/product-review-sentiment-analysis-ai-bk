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

- Distribution of Ratings by Product

![Screenshot 2024-07-05 at 10 45 50 AM](https://github.com/tombharath/product-review-sentiment-analysis-ai-bk/assets/37302704/7474697b-3f2c-4d6f-aea0-da9414e9db73)

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


**Model Comparision**

Below is the performance of each model with the default settings of the model.

![Screenshot 2024-07-05 at 10 59 13 AM](https://github.com/tombharath/product-review-sentiment-analysis-ai-bk/assets/37302704/89b3b48d-8ecb-4166-8e49-276a57a80c38)



**Next Steps**

- Hyperparameters Tuning
- Model Evaluation
- Feature Weight Extraction
- Visualize the most representative words for positive and negative comments
