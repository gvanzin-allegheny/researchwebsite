+++
title = "Activity 4 Gap Research"
description = ""
tags = [
    "research",
    "activity",
    "neural network",
]
date = "2022-03-16"
categories = [
    "Research",
    "Neural Networks",
]
+++

The knowledge gap I have identified in my topic of research is creating a way to efficiently perform the style transfer of scene lighting and color for videos in real time through the use of artificial intelligence. The main idea is to take one input image or video, and depending on the style of the lighting in the media, apply that style of lighting to another video. For example, apply the harsh shadows and black and white coloring of Sin City to a movie such as The Lord of The Rings through a neural network. I believe the specific term for this is color grading/color correction.

I know that this gap exists due to the lack of literature for this exact implementation of lighting transfer.  

For instance, the paper, https://arxiv.org/pdf/1508.06576.pdf, focuses on transferring artistic style from one image to another using deep neural networks. However, transferring artistic style removes details in the original image, and the gap I am attempting to fill will attempt to keep the original picture as detailed as possible when the lighting/coloring is changed. 

The next articles, at https://arxiv.org/pdf/1905.00824.pdf and  https://augmentedperception.github.io/total_relighting/total_relighting_paper.pdf, accomplishes the relighting of portraits with and without backgrounds, however the speed at which the algorithms run is not optimal for real time usage.

Finally, the article https://arxiv.org/pdf/1802.06474.pdf is the closest to the gap I am trying to fill. It takes two images, and transfers the coloring and lighting of the first image to the second one.  Although, like the previous algorithms, it takes quite a while to complete its task.

Therefore, based on the gap identified in the articles above, the main research question I would like to state is :

What is a feasible way to relight/recolor videos with a neural network, based on other media, that would accomplish its task in a reasonable amount of time?

I’ll attempt to accomplish crossing this gap by first gaining more insight into neural networks and machine learning by researching various algorithms made for image processing.  Also, If I come across any concepts, mathematical or otherwise, that I haven’t learned yet, I’ll attempt to teach myself how they work through online resources.  Finally, I’ll begin creating my own algorithm, train it, and then test the network. I’ll keep tweaking the algorithm and training it until I find the output good enough for a final result.
