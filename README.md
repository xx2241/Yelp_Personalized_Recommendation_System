# Yelp_Personalized_Recommendation_System
Group 201612-73 Final Project  
Xun Xue(xx2241) Zhangyu Liu(zl2513), Lingyu Zhang(lz2494)


## How to use this project
The source code contains three part: main, data_preprocessing and train_model. Here is the basic step to use this project.  
1. Set up environment  
Apache Spark, FLask, NLTK, gensim, stop_words  
2. Download dataset from Yelp dataset Challenge https://www.yelp.com/dataset_challenge  
3. In data_preprocessing folder Use final_data.py to generate necessary datasets, which will be explained in detail in the following part "data_preprocessing".  
4. In train_model folder, modify the path in train_model.py to locate your dataset "yelp_reviews.csv" generated by part 3. Use Apache Spark to run train_model.py to train a collaborative filtering model, save it in your repository.  
5. In main folder, modify the path in preprocess.py to locate your dataset "business_num_name" and "business_num_review" generated by part 2. You also need to modify the path in main.py to locate the folder "myCollaborativeFilter", which is the model trained in part 3.  
6. Use Apache Spark command "bin/spark-submit" to run the program main.py. If you are a python3 user, you need to use this command "export PYSPARK_PYTHON=python3" before running the program.

## main
This folder is the main part of this demo.

1.main.py  
Main procedure of this small app, implemented by Flask.

2.preprocess.py  
Define functions to prepare the dataset for topic modeling.

3.topic_modeling.py  
Define functions to perform topic modeling.

4.buildmodel.py  
Perform data preprocessing and topic modeling.

5.utils.py  
Save file

6.templates  
html file for the front end of this demo.

## data_preprocessing
The dataset we use is Yelp dataset Challenge https://www.yelp.com/dataset_challenge. Source code in this folder is mainly for the preprocessing of Yelp dataset.

1.final_data.py  
All dataset used in this demo can be generated by this file.  
Generate a csv file "yelp_reviews.csv" {'index', 'name', 'rating'}  
Generate a pickle file containing a dictionary "business_num_review" {'index', 'review'}  
Generate a pickle file containing a dictionary "business_num_name" {'index', 'name'}

2.data_extr.py  
No need for this demo, for the purpose of further research.  
Generate a csv file "yelp_businesses.csv" {'bid', 'bname', 'stars', 'review_count', 'latitude', 'longitude'}  
Generate a csv file "yelp_reviews.csv" {'uid', 'bid', 'reviews', 'stars'}  
Generate a csv file "yelp_users.csv" {'uid', 'name', 'total_counts', 'total_stars', 'average_stars'}

## train_model
train_model.py  
Train a collaborative filtering model and save it. When we run this app, we will use the model generated by train_model.py
