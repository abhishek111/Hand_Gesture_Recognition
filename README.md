# Hand_Gesture_Recognition
Hand Gesture Recognition using Deep Learning

<h3><b>1. Problem Statement:</b></h3></br>
This project is about developing a model which can recognize the five User’s Hand Gesture that will help user to control the Video player in the Television without Remote. The Gesture is continuously monitored by the webcam mounted on the TV:</br>
•	Thumbs up: Increase the Volume</br>
•	Thumbs Down: Decrease the Volume</br>
•	Left Swipe: Jump Backwards 10 sec</br>
•	Right Swipe: Jump Forward  10 sec</br>
•	Stop: Pause the Movie</br>

<h3><b>2.  Training Data and Validation Data</b></h3></br>
The Training and Validation data consist of 663 and 100 videos respectively. Each videos is further divided into 30 frames each capturing the hand movements. The video frames images consists of two size (120, 160, 3) and (360, 360, 3). Three representing the RGB channels and rest two dimensions denoting the number of rows and columns.

<h3><b>3. Data Generators</b></h3></br>
In most of the Deep Learning projects, the data is feed into the model in batches. This is done using the concept of Data Generators to set up the data ingestion pipeline. Creating Data Generators is probably the most important part of building a training pipeline. Although libraries like Keras provide built-in generator functionalities, but they are often limited in scope and you have to write your own generators from scratch. For example, in this problem, you need to feed Batches of videos, not images. 

The data generator yield batch of data at each iteration of shape (nFrames, nRows, nColumns, Channels). We have two image size, 120x160 and 360x360. While processing the image in the generators we cropped the image having 120x160 into 120x120 and then passed it to resize function to make it 80x80 image. The image with 360x360 shape is directly passed to resize function.

<h3><b>4. Model Architecture:</b></h3>
For Analysis videos using Neural Network, two types of architecture used commonly:
•	3D Convolution Network or Convo3D<br>
3D convolutions are the natural extension to the 2D convolutions. Just like 2D conv, you move the filter in two directions (x and y), in 3D Conv, you move the filter in three directions (x, y and z).

•	Convolutions + RNN <br>
The Convo 2D network will extract a feature vector for each image and a sequence of these feature vectors is then fed to an RNN-based network. The output of the RNN is a regular softmax.

Note: For all the models we have used Image Size of (80, 80, 3) and 15 frames for each video.
