+++
title = "OpenCV Intro Tutorial"
description = ""
tags = [
    "opencv",
    "open-cv",
    "tutorial",
    "graphics",
]
date = "2022-03-02"
categories = [
    "OpenCV",
    "Python",
]
+++

### About: 

[OpenCV](https://www.python.org/) is a library that includes artificial intelligence, image processing, and computer vision tools to make setting up projects simpler.  It contains different neural network and machine learning algorithms which you can fine-tune on your own.  It also has many different functions to allow easy image modification and reading.  OpenCV can be found at it's website under it's releases tab here: https://opencv.org/releases/

---

### Features: 

**Artifical Intelligence** : Since my project deals with neural networks, it is good to have a starting point where I can begin rather than coding a neural network from scratch.  OpenCV comes with it's own functions for creating neural networks, and it has an open source repository so I can view or modify the algorithms myself if needed.


**Image Processing** : The main idea of my project was image upscaling and/or style transfer.  For this, I would need a way to read in and modify an image, then save the new image back to my device.  OpenCV comes with many tools that make this process quite simple.  It also contains many masks for machine learning training that you can apply to images as well.

---

### Obtaining the resource: 

 OpenCV can be found on it's main page or on it's github repository.  It runs on a variety of different operating systems such as linux, windows, and mac.  There are also python versions available, which is the version this tutorial will be based on.  Not only can you run it locally, but you can also run it on your browser through a javascript version allowing you to make AI programs for a website.
 
	
 The needed libraries are just [Numpy](https://numpy.org/) and [Python](https://www.python.org/) for the Python version.  Numpy is a library that adds many mathematical functions such as large multi-dimensional arrays, fourier transformations, and more.  OpenCV's website also suggest installing the [Matplotlib](https://matplotlib.org/) library as well, but this is only a recommendation and isn't actually needed for the program to work and run.  Pip is also recommended for installing the dependencies needed much easier and will be used in this tutorial.  Luckily it comes installed with Python.

---

### Setup: 

First you must install python, and the version must be either 3.4+ or 2.7.  Python and its releases can be found here https://www.python.org/downloads/.  After installation, you can check if it has been installed correctly by opening the console and typing 'python --version'.  If this shows up:

![image](https://user-images.githubusercontent.com/54772966/157458103-f3ccc6b7-a508-4786-98d6-1917e864ab95.png)

Python is working correctly, for now.  This image was taken at a different time though, yours will probably say a much more recent version than mine.

Next is using pip to install Numpy and Matplotlib.  To do so, you must open your console and type `pip install numpy`.  Once Numpy is installed, you can do the same thing for Matplotlib with `pip install matplotlib`.

After the dependencies are installed, you can install OpenCV with pip as well using `pip install opencv-python`.  If pip does not work for the installation, you can instead download the latest release from the OpenCV website.  From there, extract the file and then locate the builds folder.  Select the OpenCV build you would like to use, and copy the file named 'cv2.pyd' to your python packages directory at :  C:/Python34/lib/site-packages.  If everything goes well, this will allow you to use OpenCV in Python also.

To test if OpenCV has been installed correctly, you can run this command :

![image](https://user-images.githubusercontent.com/54772966/157461071-5d759033-82bf-4425-b947-5c77a46fd52f.png)

If the command runs without error, OpenCV has been successfully installed.

---

### Execution: 

Since OpenCV has now been installed, you can add it to your python projects as an import like so:

![image](https://user-images.githubusercontent.com/54772966/157461771-cd7d16e3-d9f1-40d4-9c07-8f98bc492493.png)

Now that cv2 has been imported, we will want to read a image into the program in order to modify it.  We can accomplish this through the function 'imread'.  This function reads a file from the selected path and returns a value you can set to a variable for the image.  The code for this step would look like this : 

![image](https://user-images.githubusercontent.com/54772966/157462162-0d402dbc-3191-41e9-84e2-a02b1fcbd4ad.png)

Now lets perform a basic conversion on the image and change it to grayscale.  Using the function `cvtColor` we can perform different operations on an image for different purposes.  

![image](https://user-images.githubusercontent.com/54772966/157462855-3bb76a05-4b82-4e4e-8c5f-10615e42dbe1.png)

First, we read in the image using imread, then we convert the image variable using cvtColor.  Finally, we save the new image returned from cvtColor into a new variable.

'cv2.COLOR_' has many different values it can be, and for a list of more operations, you can find the Enum values here: https://docs.opencv.org/3.4/d8/d01/group__imgproc__color__conversions.html

After we have turned the image into a grayscale one, we can modify the image's pixels by calling the image variable as an array with Numpy.  The basic syntax for this is `image.item(<row>, <col>, <array_index>)`.  For instance :
	
![image](https://user-images.githubusercontent.com/54772966/157465296-7ebd879c-201b-4dee-af1b-d2001f973734.png)

Now, we can use `itemset` to modify the array, or change a pixel's color.  Let's change the pixel from before to be just red :
	
![image](https://user-images.githubusercontent.com/54772966/157465830-0161bc2e-ae50-45f3-8c3a-02f2cb5809e8.png)

Finally, we'll save our new image to a location using `imwrite`.  The basic syntax for imwrite is `imwrite(args["<file_path/file_name>"], <image_variable>)`.  The below is code saving the grayscale image to a file named, "file".
	
![image](https://user-images.githubusercontent.com/54772966/157466656-814a9310-4dbd-484c-8074-52aaebaed97b.png)

As you can see, OpenCV makes image modification and saving very easy and with Numpy, it is very efficient as well.  Although I've only covered the basics, there are many other functions that are more complicated than what was shown here so experimentation is key.

---

### Helpful resources: 

Some resources used in this tutorial are as follows:
	
	- https://docs.opencv.org/3.4/d5/de5/tutorial_py_setup_in_windows.html
	- https://docs.opencv.org/3.4/d3/df2/tutorial_py_basic_ops.html
	- https://numpy.org/doc/stable/reference/generated/numpy.ndarray.item.html
	- https://docs.opencv.org/3.4/d8/d01/group__imgproc__color__conversions.html
	- https://opencv.org/
	- https://pypi.org/project/opencv-python/
	- https://www.geeksforgeeks.org/opencv-python-tutorial/

---

