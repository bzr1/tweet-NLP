## Open Jupiter notebook for the statistical result

At the beginning of the notebook, I read in and separated the data. For embedding format, I split the training data into “train_emb_features” and “train_emb_labels”. Same for development data “dev_emb_features” and “dev_emb_labels”, and test “test_emb_features”.

For tfidf, I followed the same format only replacing the middle word with tfidf.

Then I start using algorithms to predict labels. Most algorithms are running using the library sklearn.

In the multi-layer neural network section, I first performed an iterative process to test out performance under different configurations. Then below I chose the best parameter generated to predict the labels. 

For the stacking classifier, I combined 3 models: Gaussian Naive Bayes, logistic regression and multi-layer perception. And use logistic regression again to finalise the result. 


Then below is a sub-summary of the result produced by the models above.


After this part is the feature selection section.

I first used the select percentile function from sklearn to select the top 25%,50%,75% features using the training set, then I used logistic regression to perform prediction only using these features. The reason I choose to use logistic regression is that it has the highest accuracy at the time.

Below is a summary section about the feature selection result


Then I tried boosting, which is a concept from a more recent lecture. But it uses a tree structure which I am not familiar with.

Then below is the section about semi-supervised learning. I first put unlabelled emb features under the labelled features then I used the logistic regression model as the supervised learning model and do the semi-supervised learning with different confidence level 0.75,0.9,0.65. 
Then I did the same with naive Bayes to see if there is a difference.

There is a summary section about semi model as well.


Then I performed feature engineering to see if that can improve my accuracy, I was using a sentiment intensity analyser function from the library Vader sentiment. I can produce a negative score, neutral score, positive score and compound score for sentence sentiment. Then I add the newly generated feature to the embedding training dataset and predict the label using logistic regression. 

In the end, is the code to produce an excel file for the Kaggle.