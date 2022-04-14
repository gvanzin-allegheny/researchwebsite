+++
title = "Prototype"
description = ""
tags = [
    "video",
    "frames",
    "opencv",
]
date = "2022-04-14"
categories = [
    "OpenCV",
]
+++

## Video Frame Splitter

My prototype is a tool that I will be using to gather data for my neural network to train it with.  Since I 
am working on image manipulation, I need image data.  My project has to do with changing the mood of a photo
using a neural network, so the data gathered is snippets of timelapse videos with the same scene but different
lighting in each picture.

In the frames folder for each video, there is a control image and 9 frames with different lighting.  When 
training the network, I'll generate a histogram of the control image and use the histograms of the other 
frames to have the algorithm predict how a change in the histogram would affect an images mood and coloring. 
I can also use other image information such as average colors and more.

**The prototype comes with these features included:**

- Search for timelapse videos on youtube
- Download videos
- Sort videos in text file
- Split frames in video
- Save frames in organized directories
- Easy to use terminal interface
- Compatable with both linux and windows? (only tested on linux)

**To run the program you must follow these steps:**

Run the command in the prototype src `poetry run python data_collection_main.py` in your terminal.

You will be greeted with a screen that asks what task you want the program to complete.

The tasks are sorted in the order they must be completed. 

**In order to get the prototype to work, I used these API's and documentation as well :**

https://pytube.io/en/latest/

https://github.com/alexmercerind/youtube-search-python

https://docs.opencv.org/3.4/dd/de7/group__videoio.html

