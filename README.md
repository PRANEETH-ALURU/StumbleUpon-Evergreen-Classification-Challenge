StumbleUpon Evergreen Classification Challenge

Build a classifier to categorize webpages as evergreen or non-evergreen.

<h2>Methods used:</h2>  Machine Learning and Deep Learning.

<h2>Models used:</h2>  Completed this task using 2 models i.e Used 1 Machine Learning model and 1 Deep Learning models.
(I've even used BERT Embeddings in other Deep learning Model but I didn't include in the prediction).

<h2>Description:</h2>

As the task is to predict whether the webpage is evergreen or non-evergreen, we can easily recognise this
as a binary classification task. The webpage is either evergreen or non-evergreen based upon the given
required features which are manually annotated. We have to predict the class label using those features.

<h2>Approach to solve:</h2>

<h3>1) Feature Selection:</h3>
We are given several features but we will consider the features required like: 
(url, urlid,boilerplate,alchemy_category,label)
The 'bolilerplate' feature is a json data field which has 'url','title' and 'body'. We will read the json
data and finally take 'url', 'title', 'body', 'alchemy_category' as our training data and 'label' feature
as class label to move forward with the steps of modelling predict. 
(Though I've tried using some other features, the result wasn't efficient)

<h3>2) Data Preprocessing:</h3>
I've cleaned the 'body' feature data by removing special symbols, numbers, stopwords etc., Though there
are several stemmers and lemmatizers available, I've manually removed them. 

<h3>3)Featurization (Vectorization) and Modelling:<h3>

In the machine learning model, I've used TfIdf vectorization on preprocessed body features, 
Count Vectorization on title and url features and Label Encoder on alchemy_category. After this step,
it can be trained on any ML model. I've used Logistic Regression Classifier (SGDClassifier with 
log-loss) and trained the model. After that, I've calculated the roc-auc score, precision and recall.

In the first deep learning model, I've used keras tokenizer, used texts_to_sequences and padded them with
the max length for final vectors. In the modelling part, I've fed the 'body' feature vectors to 
Bi-Directional LSTM and 'title', 'url' features to CNN1D model. After that, I've concatenated them and
fed to hidden layers. In the last layer, I used 'sigmoid' activation function with 'binary_crossentropy'
loss. Finally, fine-tuned the model many times and concluded the output.
 


The binary classification can be done using several Machine Learning and Deep Learning techniques.
