**HUMAN ACITIVITY RECOGNITION using Deep Learning**

**DESCRIPTION**

Human Activity Recognition (HAR) is a rapidly evolving field that combines the power of computer vision and machine learning 
to classify and understand human actions from visual data. 
This project focuses on leveraging deep learning techniques to automatically recognize and categorize human activities into 
predefined categories using video or image data.

With applications ranging from healthcare and surveillance to sports analytics and human-computer interaction, 
HAR systems aim to bridge the gap between human behavior and machine interpretation. 
The project employs state-of-the-art deep learning architectures, such as convolutional neural networks (CNNs) and recurrent neural networks (RNNs), 
to extract spatial and temporal features that capture the essence of various activities.

**OBJECTIVE**
Our objective is to build a robust and accurate model that can classify activities like walking, running, sitting, jumping, and more, using video datasets. 

**DATASET**

In this project we worked on a subset of **UCF-101 dataset** in which we considered only 21 classes of human activity/actions instead of the original 101.

UCF-101 dataset link: https://www.crcv.ucf.edu/research/data-sets/ucf101/

**DATA-PREPROCESSING**

A video consists of an ordered sequence of frames. Each frame contains **spatial information**, and the sequence of those frames
contains **temporal information**. To model both of these aspects, we use a hybrid architecture that consists of **convolutions** (for spatial processing) as well as **recurrent layers** (for temporal processing).

• Since a video is an ordered sequence of frames, we extracted the frames from
the video at a fixed interval until a maximum frame count (predefined) was
reached.


• Firstly, from the folder of the UCF-101 dataset we extracted the video paths and
the corresponding labels (which we further one-hot encoded) of each video
contained in the subset relevant to the project requirements.


• Then we applied the prespecified train-test split instead of a random one,
because if the videos belonging to the same group are present in both the
training and the testing datasets, then this would give a false high performance
of our models.


• For each of the videos we extracted 24 frames and also resized the frames to
224x224.


• Also while fitting the model we used data loader to load the data in batches.


• For all the considered models, loss=>‘Categorical Cross-Entropy’ ,
optimizer=> ‘Adam’, metrics=> ‘Accuracy’.


• Then we considered cases with and without transfer learning, and also
considered different pre-trained models for transfer learning. Along with this we
considered cases using different types of recurrent layers (RNN, LSTM, GRU).


**BASIC PIPELINE**

![image](https://github.com/user-attachments/assets/4673140f-2d30-4309-a348-8ae3209444e2)


**CASE 1: CNN-RNN Architecture**

![image](https://github.com/user-attachments/assets/4aafe168-6675-4e69-8b85-f1f11d2fe7b0)


**CASE 2: Transfer Learning: VGG16**

![image](https://github.com/user-attachments/assets/8796ce09-12c9-4b5d-84eb-c489a8fe986c)


**CASE 3: Transfer Learning: Resnet-50**

![image](https://github.com/user-attachments/assets/e875b192-1466-4fff-83ec-32df584dfb28)


**CASE 4: Transfer Learning: Efficient Net-B7**

![image](https://github.com/user-attachments/assets/d62dd5f4-ec9b-427d-8321-025db30eb1b6)


**Inferences Drawn**


• Using Pre-trained model for extracting meaningful features from the video
frames gives a very high accuracy score as compared to not using transfer
learning.


• Greatest validation accuracy is established when using either VGG16 or
Resnet-50 for feature extraction along with LSTM model.


