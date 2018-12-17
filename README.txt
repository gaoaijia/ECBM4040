ECBM4040 

Multi-digit Number Recognition from Street View Imagery

using Deep Convolutional Neural Network



Team: Aijia Gao ag4023, Mert Ketenci  mk4139, Shimeng Feng sf2911



There are five jupyter notebook files within this zip folder:

1. Load_Image_Train.ipynb: preprocess training images and conver to pickle file

2. Load_Image_Test.ipynb: preprocess test images and conver to pickle file

3. Model_SVHN.ipynb: Build model, perform training and testing

4.100 Class Classification: implementation of alternative model beyond original paper

5.RegressionClassifier: implementation of alternative model beyond original paper




Description of each file:



Load_Image_Train:

This jupyter notebook is used to read and process each image from the training dataset

downloaded from the source website. The dataset from the source website contains images

with variable size. Within each image, there are blue bounding box created to circle out the

individual digit within the street number. The coordinates of those bounding box are

provided in digitStruct.mat file. 


First, we read the individual png image and store the full pixel values. 

Following the same preprocessing steps outlined in the paper, we then find the

blue box enclosing all the digits of the street number and enlarge it by 30% on all direction.

Finally, we crop the image to the size of the blue box and resize all images to 54 by 54.


The last task performed in this notebook is to output the pixle values of the resized images

to a pickle file. This way, we can save time by loading data directly from this pickle file 
instead 
of reading directly from png images.



Load_Image_Test:

This jupyter notebook performs the same tasks as the Load_Image_Train file. 

It reads and process each image from the test dataset downloaded

from the source website.



Model_SVHN:

This is the main file that perform the following tasks:


(1) Read image data from processed pickle file and perform image preprocessing


(2) Build full model and define the functions for prediction and accuracy evaluation


(3) Initaite tensorflow session to train the model with train set and perform cross validation


(4) Load the trained model and perform tesing using test set



Detailed description of each tasks are included in the jupyter notebook.



In the last two files (100 Class Classification and RegressionClassifier),

we implemented to two alternative model 

to approach the problem of multi-digit sequence recognition.

The structure of the notebook is similar to Model_SVHN.

Dataset.

There are two data files that are needed to run the last three model files
if users do not want to extract image from the original PNG files:

1. trainpkl.gz: pickle file storing pixle values and labels of training images, 
to be used in training

2. testpkl.gz: pickle file storing pixle values and labels of training images, 
to be used in testing

We uploaded the pickle files of data on bitbucket.

Therefore, users can directly load image data from pickle file 

and run the Model_SVHN.ipynb.



If users want to test the Load_Image_Train and Load_Image_Test, 

the train.tar.gz and test.tar.gz need to be downloaded 
from
 the source website (Format 1):

http://ufldl.stanford.edu/housenumbers/


Then, the zip files need to be extracted and saved in the same directory.

The jupyter notebook will then read each png image and generate pickle files.



