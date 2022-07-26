+++
title = "Experiment"
description = ""
tags = [
    "video",
    "frames",
    "AI",
]
date = "2022-05-16"
categories = [
    "OpenCV",
    "Python",
]
+++

## Convolutional Neural Network Data

My project idea stems from when I was creating my prototype to download data for my network.  I thought that it would be nice if I could automatically separate the type of videos I wanted from the others rather than doing it manually to gather data.  To do this, I will be using a convolutional neural network which has greater visual detection ability compared to standard dense neural networks.

With this network in mind, I had to figure out how to format frames from a video into usable data for my network. This is what my research question is addressing; “How can I format the frames from a video to train my network?”

# Formatting frames

For my experiment, I will have two models that I will train. One model will focus on detecting colors within images and comparing them to others. This model would focus on the mood of the video. In order to focus on the whole image while keeping performance up, I will take the frames from a video and condense them into one average frame. To do this, I will add each individual array’s elements together and then divide all the elements by the total number of frames taken from the video. This average frame would be the input data for the color model.

The second model would focus on content throughout the video. Since focusing on objects and what they are takes a lot of processing power and training, I instead wanted to approach the training by having it detect changes in shape through the video frames instead. By this I mean to subtract the current frame from the next frame to get a frame that is composed of the difference between the two. Then I would do this for all frames, and save the resulting difference frames to an array. This would be the input data for the content model.

![image](https://user-images.githubusercontent.com/54772966/168792599-64637ff5-1ff4-40bd-b5c0-e0f34a3c52b4.png)

After running my experiment, I was able to get the accuracy after 20 epochs to 100% for the color model and 96% for the content model using a total of around 278 different average frames and 1858 difference frames. The results are shown below:

![image](https://user-images.githubusercontent.com/54772966/168793012-d5116cd8-d99d-45b3-ad7b-16f97c378778.png)
![image](https://user-images.githubusercontent.com/54772966/168793036-c5559ec6-1804-4e46-b742-16e88d4e2d08.png)

My next step will be training and testing the models with non-generated images to see how real videos do with the models created.
