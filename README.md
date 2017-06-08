# Seld_driving_car

<a href="https://youtu.be/Y1x5i54oqhU" target="_blank"><img src="http://img.youtube.com/vi/Y1x5i54oqhU/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="720" height="480" border="10" /></a>

## The goals:  

The goal of this project was to teach the car to autonomously navigate on road using the CNN.

## CODE

`model.py` - The script used to create and train the model.

`drive.py` - The script to drive the car. You can feel free to resubmit the original drive.py or make modifications and submit your modified version.

`model.h5` - The saved model. Here is the documentation explaining how to create this file.

`video.mp4` - A video recording of your vehicle driving autonomously at least one lap around the track.

## Launch in Autonomous Mode

To get started with autonomous driving in the simulator:
1) run simulator
2) `python drive.py model.h5`


## Network Architecture

![Alt text](readme_image/image1.png?raw=true "Optional Title")

## Data

[Load data](https://d17h27t6h515a5.cloudfront.net/topher/2016/December/584f6edd_data/data.zip)

![Alt text](readme_image/image2.png?raw=true "Optional Title")

1) To train the network, we feed her images from three cameras. To read more about this approach, see this paper by our friends at NVIDIA that makes use of this technique.

![Alt text](readme_image/image3.png?raw=true "Optional Title")

2) A effective technique for helping with the left turn bias involves flipping images and taking the opposite sign of the steering measurement. 

![Alt text](readme_image/image4.png?raw=true "Optional Title")


3) Also, before training, I crop images and normalize them

![Alt text](readme_image/image5.png?raw=true "Optional Title")

```python 
x = Lambda(lambda x: x / 255.0 - 0.5, input_shape = input_shape)(inputs)
x = keras.layers.convolutional.Cropping2D(cropping=((50,20),(0,0)),input_shape = input_shape)(x)
```
