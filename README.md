# Image Classification In Jetson Nano

Welcome to **Image Classification** using **Jetson Nano**.
This repo will walk you through how i collected datasets,trained model and classified images.I have collected Cucumber,Mango images and trained my model.

I have used **ResNet-18** image recognition model. ResNet is a residual network, made with building blocks that incorporate "shortcut connections" that skip one or more layers.The ResNet architectures presented range from 18-layers deep, all the way to 152-layers deep. In our project we will be using ResNet-18. ResNet-18 is a convolutional neural network that is 18 layers deep. We can load a pretrained version of the network trained on more than a million images from the ImageNet database.


![0](https://user-images.githubusercontent.com/73685642/167367605-fc5eb4ad-251b-4ee4-b87a-37d7dc0ca433.jpg)
![1](https://user-images.githubusercontent.com/73685642/167367693-01b14a4e-9ad8-46e7-a64a-d990cfbd7737.jpg)

The code is in the classification directory named train.py.I have downloaded required models,modules by referring [HELLO AI WORLD](https://github.com/dusty-nv/jetson-inference). And for datasets you can refer this [method](https://github.com/dusty-nv/jetson-inference/blob/master/docs/pytorch-collect.md).
## Locating  to the directory

>**$ cd NvidiaProject/classification**

For disabling the desktop GUI.

>**$ sudo init 3**

login in back and after training exit it by using the following command:

>**$ sudo init 5**
>
## Training the model
> **$ python3 train.py --model-dir=models/mydatasets --batch-size=8 --workers=2 --epochs=30 data/mydatasets**
> 
## Converting model to onnx
> **$ python3 onnx_export.py --model-dir=models/mydatasets**
> 
## Run on live camera

* MIPI CSI cameras (csi://0)
* V4L2 cameras (/dev/video0)
* RTP/RTSP streams (rtsp://username:password@ip:port)

> **$ imagenet.py --model=models/mydatasets/resnet18.onnx --labels=data/mydatasets/mylabels.txt --input_blob=input_0 output_blob=output_0 /dev/video0**
> 
## Saving the live camera feed in .mp4 fromat
> **$ imagenet.py --model=models/mydatasets/resnet18.onnx --labels=data/mydatasets/mylabels.txt --input_blob=input_0 output_blob=output_0 /dev/video0 test.mp4**

## Video Walk through Terminal Sessions

### Training the model for image classification
[![asciicast](https://asciinema.org/a/MMeGSu4bne00HSnHDHfP1lkOi.svg)](https://asciinema.org/a/MMeGSu4bne00HSnHDHfP1lkOi)

## Output Video
👉 https://youtu.be/AuB8RWOY17U)

[![Image Classification on Jetson Nano](http://img.youtube.com/vi/AuB8RWOY17U/0.jpg)](https://youtu.be/AuB8RWOY17U)
