# Feature-Extraction-using-Transformer-model for sentiment analysis 

The current state-of-the art large language models require large datasets and significant computational power to train them properly, so they achieve high accuracy.
However, to solve our problems we often do not have access to large datasets to train large language models, and we may not have access to powerful computers.
So transfer learning from large-scale pre-trained models becomes popular in Natural Language Processing (NLP) field. We can still use the large pretrained language models with small datasets of our interest and run them on our not so powerful computers.
In this project, I am using a transformer model from Hugging Face depository -- DistilBERT base model. DistilBERT is a Transformer model trained by distilling BERT base. I will use this model to extract essential features from a dataset I of my interest. For feature extraction I will use the part of the model up to the last hidden state and discard the task specific head, like classification head. It is also possible to use the whole model and adjust the classification head and retrain the whole model with the new smaller datasets, but I found that approach to me computationaly more challanging. So in this project I am using only the bare bone transformer model for feature extraction. I will use this model to extract essential features about text data that the model previously learned from the large text datasets. 
I am using Emotion dataset, which is a dataset of English Twitter messages with six basic emotions: anger, fear, joy, love, sadness, and surprise. The dataset consists of 16000 tweets for training, 2000 tweets for validation, and 2000 tweets for testing. 
I have preprocessed the data before feeding it into the model using Tokenizer library from Hugging Face, Python, PyTorch, and Pandas. The model outputed a new dataset with essential features extracted from Emotion dataset. I used a classification model from scikit-learn library, logistic regression, and applied the model to the dataset of extracted features. I achieved accuracy of the whole pipeline - feature extractor and classification model -  to be about 65%, which is higher compared to 30% of the naive model. The low accuracy scores are due to the unbalanced multiclass dataset.     
