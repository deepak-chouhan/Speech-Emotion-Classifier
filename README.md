# Speech Emotion Classifier
<img src="https://miro.medium.com/max/875/0*tqQ-x7QM2zKhJB9F.jpg"/>

## Problem
The purpose behind this project is to build a model which can classify human emotion in different categories from an Audio file.

Categories we are looking to classify:

> - **Calm**
> - **Angry**
> - **Sad**
> - **Happy**
> - **Fearful**


## Dataset

We will be using **RAVDESS** dataset from kaggle https://www.kaggle.com/dmitrybabko/speech-emotion-recognition-en

Here is the filename identifiers as per the official RAVDESS website:

> - Modality (01 = full-AV, 02 = video-only, 03 = audio-only).
>  Vocal channel (01 = speech, 02 = song).
> - Emotion (01 = neutral, 02 = calm, 03 = happy, 04 = sad, 05 = angry, 06 = fearful, 07 = disgust, 08 = surprised).
> - Emotional intensity (01 = normal, 02 = strong). NOTE: There is no strong intensity for the 'neutral' emotion.
> - Statement (01 = "Kids are talking by the door", 02 = "Dogs are sitting by the door").
> - Repetition (01 = 1st repetition, 02 = 2nd repetition).
> - Actor (01 to 24. Odd numbered actors are male, even numbered actors are female).

So, here's an example of an audio filename. `02-01-06-01-02-01-12.wav` This means the meta data for the audio file is:

> - Video-only (02)
> - Speech (01)
> - Fearful (06)
> - Normal intensity (01)
> - Statement "dogs" (02)
> - 1st Repetition (01)
> - 12th Actor (12) - Female (as the actor ID number is even)

## Proposed system
This model is created using Deep neural network, we use Sequential model API to create neural network of our model to predict emotion in audio file. The Sequential model API is a way of creating deep learning models where an instance of the Sequential class is created and model layers are created and added to it.

The emotion classifier classifies the emotion out of 5 categories
- Calm
- Happy
- Sad
- Angry
- Fearful

The steps involved for predicting the emotion from audio:-

- The Model takes audio file as an input and with the help of the python library “Librosa”. 
- We extract the features, then we reshape the features by [1, 40, 1], so that it matches with the machine learning model input type. 
- After reshaping it, we feed the data to our machine learning model. 
- In return the model gives us the array of number which we need to decode the help of “Label Encoder”. It has a function provided specifically for the task called “inverse_transform”
- Once we have decoded the array of number, we will get the exact emotion of Audio speech given by user.
