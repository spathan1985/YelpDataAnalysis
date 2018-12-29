# Sentiment Analysis of Yelp Restaurant Reviews 

The goal of this project was to provide qualitative feedback to restaurant owners in order to improve their business using the Yelp Dataset Challenge. The Yelp challenge dataset contains information about local businesses, reviews and users in 10 cities across 4 countries. This dataset contains:

* 4.1M reviews and 947K tips by 1M users for 144K businesses
* 1.1M business attributes, e.g., hours, parking availability, ambience.
* Aggregated check-ins over time for each of the 125K businesses
* 200,000 pictures from the included businesses

For the purposes of this project we were only interested in the restaurant review text, hence we utilized only the yelp academic dataset business.json and yelp academic dataset review.json files from the dataset. 

The following Python libraries were utilized:

* Python's pandas for data filtering and analysis
* matplotlib and seaborn libraries for visualization/ EDA
* NLTK/ Chunker for text-preprocessing 
* Python's Pattern package for polarity determination
* Chunker package for sentiment analysis
* Sklearn for machine learning algorithms like SVM, Naive Bayes for classification of reviews

## System requirements:
 - Jupyter notebook
 - Python version 2.7
 - Packages needed: Pattern, NLTK

## Steps for running the code:
1) Download Yelp Academic Dataset from the [website](https://www.yelp.com/dataset/download). Feed files yelp_academic_dataset_business.json and yelp_academic_dataset_review.json to filter_data.ipynb. Filter data file is used to extract restaurants in a particular city and reviews related to that restaurant. The output of this code is Phoenix_restaurants.json and Phoenix_restaurant_reviews.json.

2) The next step is to summarize all the reviews to meaningful phrases, determine the polarity of filtered phrases and give a score to each of the words in the phrases. We feed the file Phoenix_restaurant_reviews.json to review_summarization.ipynb for this purpose and output file Phoenix_restaurant_review_Results.csv is generated. The output file contains extracted phrases and their respective polarities.

3) We now have the phrases extracted and the polarity calculated from the reviews, hence using Phoenix_restaurant_review_Results.csv from step2, we can now execute the jupyter notebook 'yelp_project_classify.ipynb' step by step to verify the following:
- correlation
- classification
- phrase categorization
- visualization
- restaurant evaluation. 

4) For restaurant evaluation, we changed the categories to 'Pizza' in filter_data.ipynb and reran the same code to generate restaurant_reviews_Pizza.json. This json file was used by review_summarization.py to generate the phrases only for Pizza restaurants.The following lines of code were modified in filter_data.py to extract Pizza only restaurants:

* 'Pizza' in each_business['categories']
* fileName=city + '_restaurant_reviews_Pizza.json'
