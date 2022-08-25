+++
title = "Research Proposal"
description = ""
tags = [
    "video",
    "frames",
    "opencv",
]
date = "2022-05-18"
categories = [
    "OpenCV",
    "AI",
]
+++

# Research Proposal

&nbsp;&nbsp;&nbsp;My area of research for my project falls within the field of image classification.  To be more precise, image classification with artificial intelligence.  The reason for my interest in this field is because I find it fascinating how neural networks and machine learning can solve problems that wouldn’t be possible with other algorithms normally.  For instance, writing a program that can detect numbers within an image would be impossible without the implementation of some form of artificial intelligence.  I wanted to focus on the neural network side of AI rather than machine learning for this project since I haven’t delved into the topic as much.  With the desire to work with neural networks, I came up with the idea of creating an AI that can seperate videos into categories based on similarity.  This idea came to me when I was already halfway through the project cycle.  When I was working on the prototype for my project, I thought that sorting the data I retrieved for the AI would be much better if I could use a tool rather than doing everything manually.  This is where I got the idea of a video classification network.

&nbsp;&nbsp;&nbsp;There are already many image classification networks out there that companies and individuals have made.  A few examples are Dall-E, CoCa, and CaiT-M.  Through their papers, I was able to get a better understanding of the processes behind image classification, and learned that the most widely used networks for these purposes are called convolutional neural networks.  Convolutional neural networks aim to improve speed and pattern recognition by applying filters to an image which generates an array containing which regions match the filter the best.  Since the filters condense an area of pixels into one number, the image is scaled down while still containing important information for training the network.  Throughout the network, multiple filters are applied to the image in order to identify objects with certain visual attributes.  After the filters are applied, the resulting array is passed through an algorithm usually called a ‘pooling layer’.  The purpose of the pooling layer is to go through the array in order, and find the highest number within a 2x2 area and save it to another array to condense the images information even more.  After all these steps are done, the array is then flattened and passed through a dense neural network.  The main reason for condensing the image so much is to lower the calculations the network needs to perform.  For instance, a normal HD image, at around 1280 x 720 resolution, contains 921600 pixels.  Without condensing the image, there would be 921600 input parameters, however, if we condense the image, we could reduce that to half or even lower.

&nbsp;&nbsp;&nbsp;With these ideas in mind, I had two goals for this project.  The first was to learn more about convolutional neural networks.  The knowledge I gained while working on this program wouldn’t just be used for this project alone, the field of AI has been growing at an increasing pace and I will most likely be using what I’ve learned in future projects as well.  My second goal was to develop a network that could classify videos the same way that image classifiers worked.

&nbsp;&nbsp;&nbsp;My second goal stemmed from the Gap in research that I noticed when I was first beginning my project.  There are many image classifiers, but not as many video classifiers.  One example of a video classifier that many people know about is youtube’s search recommendation algorithm.  You can type in a keyword or phrase for a video and it will find you videos with content similar to the phrase you have given.  However, there are differences between what I want to make and the recommendation algorithm youtube makes.  One difference is you can only use words with youtube to find videos, while the program I will be working on will allow you to input a video and find videos similar to what you have given.

&nbsp;&nbsp;&nbsp;The reasoning for this gap in research does make sense though.  Videos are much more complex compared to single images.  For instance, a single video can change scenes many different times while an image stays the same no matter what.  Because of this, finding similarities between videos is much more difficult.  However, I want to attempt to solve this gap by creating a program that can detect similarities in videos.

&nbsp;&nbsp;&nbsp;Since the gap I identified deals with creating a program to detect video similarities, I was able to produce two research questions for my project to help guide me.  The first question is "How can I train an AI to recognize differences between videos?"  My answer to this question will be answered later on in the paper, however, for now I’ll say that using the frames in a video will be the way I train the network later on.  This leads into the second research question which is, "How should I format frames from a video into a single piece of data to input into a neural network?"  As stated earlier, we want to reduce the amount of input data as much as possible because the more parameters, the more calculations are needed which in turn increases the time needed to train to AI.  

&nbsp;&nbsp;&nbsp;While I was figuring out these questions, I also had to worry about two things, scope and feasibility.  The scope of the project is variable since it depends on how much I want to train the neural network.  For instance, the more I train the network, the more data I will need, and the more the accuracy should go up.  However, I will be making only a basic version of my idea to keep feasibility up.  There are two reasons for making a simple version of my AI.  The first reason is due to computational issues.   While I do have an some-what fast computer, I am by no means Google or Microsoft.  Training an AI with a very large data set does make the AI much more accurate, but you in turn need a lot of powerful hardware to run the training program.  The second reason is due to time constraints with the project.  There is only one semester to finish the project, so I can’t spend weeks at a time waiting for the training of the network to finish in case I need to retrain it due to an issue.

&nbsp;&nbsp;&nbsp;To begin my project, now that I understood the feasibility and gap associated with it, I needed a prototype to generate the data I would use to train my network.  Using python, I created a tool to download youtube videos and then split the frames in the videos into separate folders.  The program is controllable through an interface in the terminal and allows for choosing which step of the process you want to start with in case you don’t want to do the whole thing.  

&nbsp;&nbsp;&nbsp;There are 4 different steps to the tool, and the first searches for youtube videos with titles similar to what is specified in the program.  It then saves these searches to a text file for the next part of the process.  Once that has been completed, you are given the chance to manually remove videos that don’t match what you actually wanted to download.  For instance, you may be looking for sunrise timelapse videos, but a house building timelapse snuck its way into the text file.  This is what this step is used for; the manual checking of content within the videos.  The third step downloads the videos from youtube that are located within the text file and then saves those videos to their own folder.  Finally, the program then gets each video, splits the video into 10 equal frames (or however many frames are specified), and saves those 10 frames to their own folder as well.

&nbsp;&nbsp;&nbsp;To create my prototype I had to use a couple of libraries provided on github.  The first is called ‘youtubesearchpython’, and it allows you to perform a youtube search from within a python project.  This library was used for finding videos that match the keywords specified in the program and then saving them to a text file.  The second dependency is called ‘opencv-python’.  OpenCV is a really handy library that offers functions to modify and create both images and videos within python.  This was used to split the videos into frames in the last part of the program.  Finally, ‘youtube-dl’ and ‘yt-dlp’ were used to download the videos that ‘youtubesearchpython’ found online and save them to a local folder.

&nbsp;&nbsp;&nbsp;All of these steps and dependencies allowed me to retrieve data efficiently and organize it in a way that would make training my neural network possible.  Without the prototype I made, getting video data would be much more difficult and organizing the frames would be quite tedious.

&nbsp;&nbsp;&nbsp;Now that I had a working prototype to gather data, I moved onto formulating an experiment to confront a previous research question I had stated earlier, "How should I format frames from a video into a single piece of data to input into a neural network?"  A better way to phrase this would be "What type of image processing algorithm should I create to use on the frames from my prototype in order to train my network correctly?"

&nbsp;&nbsp;&nbsp;I had two main ideas for solving this problem.  The first was to average all the frames of each video together into one average frame per video.  This would condense a whole video into a single image and massively increase training speed.  The other motivation for averaging the frames was to detect color similarities within videos.  For example, if one video’s average frame was more on the blue side, then a video with an average frame on the red side is not similar to the other.  The second idea was to get the difference between elements in a frame’s array from the next frame in the video sequence.  This would hopefully allow the network to detect changes in shapes based on time and also spot the speed the video is playing at.  If a video is shot with a quick pace, the difference between the frames will be much greater compared to a video that is still.  A diagram is provided below to give a better understanding of the two frame functions:

![Diagram](https://user-images.githubusercontent.com/54772966/169022253-53f2f16a-8ea5-4a9e-8c29-8afb0d5c3123.png)

&nbsp;&nbsp;&nbsp;Since they both sounded like good ideas to me, I decided instead of just using one, I would use both.  The algorithm to average colors would have its own network and the function to find the difference in frames would have one too.

&nbsp;&nbsp;&nbsp;To run the experiment, I generated data on the fly rather than using images from my prototype first.  The reason for this was to allow me to better understand any issues that may arise when training the two models.  The generated data was a 256 x 144 resolution image with random colored pixels and one single colored circle randomly placed within the image.  Each circle’s color corresponded with the category the image should be in.  An example of a generated image is as follows: 

![Example Image](https://user-images.githubusercontent.com/54772966/169022412-1f414d1a-4abc-406e-af81-fa3503a35adb.PNG)

&nbsp;&nbsp;&nbsp;After running the experiment, I was able to achieve 100% accuracy with the color detecting network and 96% accuracy with the content detecting network (this was after 20 training stages).  While this is good and showed me that the methods I used to format my data worked, I still needed to test the training with actual videos gathered online.

&nbsp;&nbsp;&nbsp;To complete my project, I put together a dataset of frog, dog, and cat videos using my prototype.  Then, I trained each model on all of the videos and was able to achieve an accuracy of around 83% for the color model and 100% for the content model.  While this is an okay accuracy, there is still definitely room for improvement.  The accuracy is show below : 

![ContentEpochFinal](https://user-images.githubusercontent.com/54772966/169021856-12a741cc-a74b-44d1-82c6-dac44366b281.PNG)
![ColorEpochFinal](https://user-images.githubusercontent.com/54772966/169021858-ac640f41-52d1-4a58-bfb4-f677258e3638.PNG)

&nbsp;&nbsp;&nbsp;Future work on the project could add these improvements.  For instance, converting the difference frames for the content model into black and white could prevent the network from focusing on differences in color rather than focusing on the movement in the video.  Another potential improvement could be to average the difference frames similar to what is done for the frames used by the color model.  This way the network can find patterns within the average movement in a video rather than in segments.  Finally, training the model with more videos and frames would improve its accuracy as well.

&nbsp;&nbsp;&nbsp;While the current project focuses on a basic version of the idea I originally proposed, a more advanced version could pose significant ethical concerns.  One concern, which isn’t as serious as the other, would be using data from youtube that is not owned by the developer working on training the model.  This is an issue with permission not being granted by those who made the videos, however, this problem could be solved by filming original videos for training instead.  The second concern is the use of a tool like this to find videos for censorship and misinformation.  For instance, if a group was wanting to delete videos with a certain message, a more powerful version of video classification could point them to where the videos are located.  This issue is a tricky one since most preventative measures could be reversed with enough knowledge of the program and therefore there aren’t any good permanent solutions.

&nbsp;&nbsp;&nbsp;However, although there are ethical concerns associated with this type of program, there are also many benefits as well.  Finding similar creators to you if you are a videographer for instance.  While this program was just a beginning stage of video classification, I believe that further research and improvements into the program in the future could improve it significantly.