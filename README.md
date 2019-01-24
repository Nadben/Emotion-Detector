# Emotion-Detector
Deep neural network based on SimpleNet V2 to predict 8 emotions (Fear, Anger, Happiness, Disgust, Contempt, Neutral, Sadness and Surprise) using Keras and OpenCV. 

### DataSet
AffectNet is a dataset consisting of over 420k images manually annotated. The images are all different sizes, so I had to resize them to a shape of 64x64x3 before using them. Also, since I am doing this at home and with limited ressources I had to take only a fraction of the images contained in the dataset. I used a total of (roughly) 20k images for training and 5k for testing.  

### CNN Architecture
As stated the CNN architecture is based on SimpleNet V2 and here is the model summary.

Layer (type)                | Output Shape       |      Param #   
| :---                      |:---                |:---
conv2d_1 (Conv2D)           | (None, 64, 64, 66) |       1848                           
batch_normalization_1       | (None, 64, 64, 66) |       264       
activation_1 (Activation)   | (None, 64, 64, 66) |       0         
dropout_1 (Dropout)         | (None, 64, 64, 66) |       0         
conv2d_2 (Conv2D)           | (None, 64, 64, 128)|       76160     
batch_normalization_2       | (None, 64, 64, 128)|       512       
activation_2 (Activation)   | (None, 64, 64, 128)|       0         
dropout_2 (Dropout)         | (None, 64, 64, 128)|       0         
conv2d_3 (Conv2D)           | (None, 62, 62, 128)|       147584    
batch_normalization_3       | (None, 62, 62, 128)|       512       
activation_3 (Activation)   | (None, 62, 62, 128)|       0         
dropout_3 (Dropout)         | (None, 62, 62, 128)|       0         
conv2d_4 (Conv2D)           | (None, 60, 60, 128)|       147584    
batch_normalization_4       | (None, 60, 60, 128)|       512       
activation_4 (Activation)   | (None, 60, 60, 128)|       0         
dropout_4 (Dropout)         | (None, 60, 60, 128)|       0         
conv2d_5 (Conv2D)           | (None, 58, 58, 192)|       221376    
batch_normalization_5       | (None, 58, 58, 192)|       768       
max_pooling2d_1             | (None, 29, 29, 192)|       0         
activation_5 (Activation)   | (None, 29, 29, 192)|       0         
dropout_5 (Dropout)         | (None, 29, 29, 192)|       0         
conv2d_6 (Conv2D)           | (None, 29, 29, 192)|       331968    
batch_normalization_6       | (None, 29, 29, 192)|       768       
activation_6 (Activation)   | (None, 29, 29, 192)|       0         
dropout_6 (Dropout)         | (None, 29, 29, 192)|       0         
conv2d_7 (Conv2D)           | (None, 29, 29, 192)|       331968    
batch_normalization_7       | (None, 29, 29, 192)|       768       
activation_7 (Activation)   | (None, 29, 29, 192)|       0         
dropout_7 (Dropout)         | (None, 29, 29, 192)|       0         
conv2d_8 (Conv2D)           | (None, 29, 29, 192)|       331968    
batch_normalization_8       | (None, 29, 29, 192)|       768       
activation_8 (Activation)   | (None, 29, 29, 192)|       0         
dropout_8 (Dropout)         | (None, 29, 29, 192)|       0         
conv2d_9 (Conv2D)           | (None, 29, 29, 192)|       331968    
batch_normalization_9       | (None, 29, 29, 192)|       768       
activation_9 (Activation)   | (None, 29, 29, 192)|       0         
dropout_9 (Dropout)         | (None, 29, 29, 192)|       0         
conv2d_10 (Conv2D)          | (None, 29, 29, 288)|       497952    
batch_normalization_10      | (None, 29, 29, 288)|       1152      
activation_10 (Activation)  | (None, 29, 29, 288)|       0         
dropout_10 (Dropout)        | (None, 29, 29, 288)|       0         
max_pooling2d_2             | (None, 14, 14, 288)|       0         
conv2d_11 (Conv2D)          | (None, 14, 14, 288)|       746784    
batch_normalization_11      | (None, 14, 14, 288)|       1152      
activation_11 (Activation)  | (None, 14, 14, 288)|       0         
dropout_11 (Dropout)        | (None, 14, 14, 288)|       0         
conv2d_12 (Conv2D)          | (None, 12, 12, 355)|       920515    
batch_normalization_12      | (None, 12, 12, 355)|       1420      
activation_12 (Activation)  | (None, 12, 12, 355)|       0         
dropout_12 (Dropout)        | (None, 12, 12, 355)|       0         
conv2d_13 (Conv2D)          | (None, 10, 10, 432)|       1380672   
batch_normalization_13      | (None, 10, 10, 432)|       1728      
activation_13 (Activation)  | (None, 10, 10, 432)|       0         
dropout_13 (Dropout)        | (None, 10, 10, 432)|       0         
global_max_pooling2d_1      | (None, 432)        |       0         
dropout_14 (Dropout)        | (None, 432)        |       0         
dense_1 (Dense)             | (None, 8)          |       3464      
----------------------------|--------------------|--------------
Total params: 5,482,903
Trainable params: 5,477,357
Non-trainable params: 5,546


### Results
The Network was trained using a GTX 1070 TI for only 40 epochs, here are the results

Architecture | Number of epochs| Training accuracy | Validation acc (%) | Validation err
| :---:      | :---:           |:---:             |:---:               |:---:   
SimpNetV2    | 40              | 83.3 %           | 54 %               | 1.187


The results seems to be very poor but when I tested it in real time with the camera, it was giving fairly good results. It could still be improved as I plan on the near future to train the network on antoher 25k images on 40 epochs. It has some difficulty in classifying the mood of someone who wears glasses. It could be because of the reflection on the glasses and/or the poor light condition in the room. 

All in all it was a cool little project i did for fun... Onto the next project !

