Initially the code imports required classes from scipy, sklearn, pandas, nltk, numpy, re.

In the next step the code retrieves train, validation and test sets as dataframe from their respective locations into variables train_data, val_data and test_data respectively. Similarly, the train_labels, val_labels require respective locations of train_labels and validation_labels. The test_data_final also requires test set from its respective location which is used for 'movieId' generating csv file of test predictions. 

After importing the files the code removes columns 'movieId','YTId' and 'year'. In the next step unwanted numbers and characters are removed from text features tag and title. Next train and validation labels are assigned with genres from train and validation set respectively.

In the next step, TF-IDF vectorizer converts text features to vectors, by implementing the lemmatization function. The lemmatization function inputs each text feature as a list and tokenize them to meaningful base form. The resultant vectors are appended to the dataframe as features. Next the code removes initial 'title' and 'tag' columns from the dataframes. 

Later, the machine learning model implementation uses following classifiers :

1) MultinomialNB - This model is considers default parameters and it performs multi-class classification. This model estimates the baseline performance. It is one of the probabilistic-based algorithms. It estimates each category’s probabilities by applying Bayes theorem. The resulting output will be the category with the highest probability. 

2)Support Vector Machine - This model uses linear kernel. This model implements one-vs-one strategy by using decision function shape. The model linearly separates the datapoint and estimates an optimal hyperplane with maximum margin.

3)Gradient Boosting Classifier - This model implements the one-vs-rest strategy for multi class classification. This classifier is an ensemble of weaker models, which learns from the mistakes of previous predictor. 

4)Decision Tree - This model implements multilevel classification. The decision tree consists of a network that uses a tree-like graph. In this classifier each leaf node represents a class label, whereas each branch represents the outcome of the previous node.

After each model the predictions on validation features is compared with actual validation labels to evaluate the metrics. The code also stores test set predictions in corresponding variables.

Finally, the code uses corresponding variables of test set from different models and convert them to csv file consisting of 'movieId' and 'genre' as columns.

