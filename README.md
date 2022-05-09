# Image Classification In Jetson Nano

Welcome to image classification using Jetson Nano.
This repo will walk you through how i collected datasets,trained model and classified images.I have collected Cucumber,Mango images and trained my model.
The code is in the classification directory named train.py.

## Locating  to the directory

>**$cd/NvidiaProject/classification**

For disabling the desktop GUI 

>**$sudo init 3**

login in back and after training exit it by using the following command:

>**$sudo init 5**
## Training the model
> **$python3 train.py --model-dir=models/mydatasets --batch-size=8 --workers=2 --epochs=30 data/mydatasets**
## Exporting to onnx
> **$python3 onnx_export.py --model-dir=models/mydatasets**
## Run on live camera
> **$imagenet.py --model=models/mydatasets/resnet18.onnx --labels=data/mydatasets/mylabels.txt --input_blob=input_0 output_blob=output_0 /dev/video0**
