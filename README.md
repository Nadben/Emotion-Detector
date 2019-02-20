# Emotion-Detector
Deep neural network based on SimpleNet V2 to predict 8 emotions (Fear, Anger, Happiness, Disgust, Contempt, Neutral, Sadness and Surprise) using Keras and OpenCV. 

### DataSet
AffectNet is a dataset consisting of over 420k images manually annotated. The images are all different sizes, so I had to resize them to a shape of 64x64x3 before using them. Also, since I am doing this at home and with limited ressources I had to take only a fraction of the images contained in the dataset. I used a total of (roughly) 23k images for training and 5k for testing.  

### CNN Architecture
As stated the CNN architecture is based on SimpleNet V2 and here is the link to the project.
https://github.com/Coderx7/SimpNet


### Results
The Network was trained using a GTX 1070 TI for only 40 epochs, here are the results

Architecture | Number of epochs| Training accuracy (%)| Train loss | Validation acc (%) | Validation loss | Number of images trained on
| :---:      | :---:           |:---:      |:---:       |:---:               |:---:   | :---: 
SimpNetV2    | 40              | 83.32            | 0.517     | 54            | 1.187 | 23018
SimpNetV2    | 40              | 85.13            | 0.416     | 59.68            | 1.257 | 46036



The results seems to be very poor but when I tested it in real time with the camera, it was giving fairly good results. It could still be improved as I plan on the near future to train the network on antoher 25k images on 40 epochs. It has some difficulty in classifying the mood of someone who wears glasses. It could be because of the reflection on the glasses and/or the poor light condition in the room. 

![Alt Text](https://media.giphy.com/media/LwFCdpj9KIoiein3A1/giphy.gif)

All in all it was a cool little project i did for fun... Onto the next project !

