# U-NET-Image-Segmentation
Practical use case of U-NET model for Segmentation of Images to detect Oil leakage or Seep detection.
This is very famous problem statement in Induatrial and Manufacturing sector where Machine Learning especially 
Computer Vision concept can be used to detect faults which are very hard to detect by normal human beings.



# Dataset and model
Analysing the training dataset, It is found that there are 790 SAR images along with their respective mask.
In order to train a Deep Convolutional Neural Network to detect Oil Seeps, I selected U-NET Image segmentation
model. In order to do segmentation of an image, It is very important to understand labels at pixel-level.


![Screenshot 2022-12-10 at 20-25-21 Google Colaboratory](https://user-images.githubusercontent.com/26542431/215565844-81598d12-6cf3-4592-9ba4-c9637e67b4db.png)


# Overview of Model

The U-NET model consists of Encoder-Decoder channel which includes:
  1. Fully Convolutional Layer with MaxPooling for Down Sampling operation to learn features
     for prediction of Seeps in the image
  2. Later using ConvolutionTranspose for Up Sampling and further Uses concatenation 
     with Encoder Convolution layer to preserve Locatization information of pixels. 

Code is divided into two parts:

Part 1 (Binary CLasses): To detect and segment seeps of images irrespective of type of seeps.

Part 2 (Multi Classes) : To detect and segment seeps of images along with type of seeps. 

Codes along with their step by step explaination is provided for both part.

# Limitations and Further Improvements
There is limitation of using class_weight for Keras model.fit() in case of 3D inputs.
But class_weights can be incorporated for using custom loss function which considers class_weights for each pixels for
calculating loss and learn.

Further improvement that can be considered:
1. Reduce the balance of classes for pixels in a image by cropping image part containing seeps. But it may 
   cause information loss too.
2. Using class_weights for while calculating loss function to give more importance for less occuring labels.
3. More loss functions like focal loss etc. with different learning parameters can be tried out to see better results.

Thanks.
If you want to go through more contents related with Machine Learning / Data Science, Do visit : https://medium.com/@raushanjoshi199
Thanks for reading.
Your inputs are also welcomed :)
