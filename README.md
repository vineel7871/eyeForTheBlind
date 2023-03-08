# Eye For The Blind
In this project I am attempting to create a deep learning model which can explain the contents of an image in the form of speech through caption generation with an attention mechanism on Flickr8K dataset. This kind of model is a use-case for blind people so that they can understand any image with the help of speech. The caption generated through a CNN-RNN model will be converted to speech using a text to speech library. 
<br><br>
This problem statement is an application of both deep learning and natural language processing. The features of an image will be extracted by a CNN-based encoder and this will be decoded by an RNN model.
<br><br>
The project is an extended application of the research paper [Show, Attend and Tell: Neural Image Caption Generation with Visual Attention paper](https://arxiv.org/abs/1502.03044).
<br><br>
The dataset is taken from the [Kaggle website](https://www.kaggle.com/datasets/adityajn105/flickr8k) and it consists of sentence-based image descriptions having a list of 8,000 images that are each paired with five different captions which provide clear descriptions of the salient entities and events of the image.

## Setting up the Project
- Install dependencies from requirements file
```pip install -r requirements.txt```
<br>
- Install nltk tokenizer
<br>
```import nltk; nltk.download('punkt'); nltk.download('stopwords')```
<br>
- Download the dataset to the data folder from [here](https://www.kaggle.com/datasets/adityajn105/flickr8k)
<br>
- The folder structure should be like
  - root
    - data
      - flikr8k
        - images
        - captions.txt
    - models
    - notebooks
      - preprocessing
      - training
      - evaluation

## Data Understanding
1. Import the dataset and read image & captions into two seperate variables
2. Visualise both the images & text present in the dataset
3. Create a dataframe which summarizes the image, path & captions as a dataframe
4. Create a list which contains all the captions & path
5. Visualise the top 30 occurring words in the captions

## Pre-Processing the captions
1.Create the tokenized vectors by tokenizing the captions fore ex :split them using spaces & other filters. 
This gives us a vocabulary of all of the unique words in the data. Keep the total vocaublary to top 5,000 words for saving memory.

2.Replace all other words with the unknown token "UNK" .

3.Create word-to-index and index-to-word mappings.

4.Pad all sequences to be the same length as the longest one.

## Pre-processing the images

1.Resize them into the shape of (299, 299)

3.Normalize the image within the range of -1 to 1, such that it is in correct format for InceptionV3. 










