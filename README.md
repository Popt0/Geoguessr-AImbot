# Geoguessr AImbot
## Overview
This project is implemented for AI Camp Summer Computer Vision. The **minimum viable product (MVP)** is to detect bollards, electricity poles in the images using YOLOv5. Geoguessr is a geographical website game where players guess the locations of Google street view images. We decided to make a Geoguessr AImbot because Geoguessr is very popular and there aren’t that many ways to cheat it. Our AI also has real-world applications. For example, it can be used to find a possible country where random images were taken if someone is curious.

## Dataset
We downloaded Youtube videos of people playing Geogussr and extracted image frames once every thirty seconds. The images that contain signs, electricity poles, or bollards were kept and labeled using [roboflow](https://roboflow.com/) by everyone on the team. Our country specific datasets were created using Google street view API, where we gathered random urban and suburban location street view images and went through the same process on Roboflow. 
You could find the data used for training, validation and testing in data directory. Our dataset contains roughly 5000 images. 

## Model Training
We used Kaggle notebooks accelerated with GPUs to train each of our models. The base model was trained with YOLOv5 while the three accessory models were trained in Resnet18. The primary augmentations we used were brightness, saturation, contrast, and hue.

## Web Deploy

The web deploying part is refered to the [web templates of AI Camp](https://github.com/organization-x/omni), the CV branch specifically. You could find relative codes and files in [deploy](deploy). To test the deployed web, after installing all the dependencies in [requirements.txt](deploy/app/requirements.txt) (using `pip install -r requirements.txt`), run the [main.py](deploy/app/main.py) (`python3 -m main`). Then you should have a link like https://cocalc4.ai-camp.dev/49d42078-2ad9-44c6-bf76-70f193709a84/port/12345/. 

## Roadblocks and Finalization
One of our challenges was overfitting the ResNets. This was mostly due to time limitations-- gathering and labeling a large amount of data was very time consuming.

**Possible Solutions:** 
1. Increase the number of images in the data;

## Reference
1. YOLOv5 Document: https://github.com/ultralytics/yolov5
2. AI Camp Web Templates: https://github.com/organization-x/omni/tree/main/app
3. Roboflow: https://roboflow.com/
4. Google Street View API: https://developers.google.com/maps

## Demo
https://www.youtube.com/watch?v=mY_FjQqvUBw
