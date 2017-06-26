# Finding-Lane-Lines
This is a project which is part of the Udacity's self driving car nano degree.

# Overview

In this project we find Lane lines from a given video of a road, frame by frame. This is done using Python and OpenCV.

# Pipeline

-> Convert each frame into HSV colorspace, because in well lit environments it's easy to separate different colors but in case of low lit    conditions such as in the part of the challenge video where there is shadow it is difficult to separate white and yellow lines which      are generally the colors used for lanes. Hence transforming them to HSV makes it easier to separate them as lane lines. This is then      converted   to grayscale for edge detection purposes.

-> Choose an appropriate kernel size.(Here i have used 5) and apply gaussian filter to smooth the image.

-> Apply canny edge detection algorithm. From the result obtain the region of interest.

-> Apply hough transform to this region of interest to detect lines.

-> Iterate over the set of lines obtained and separate them to left and right lane lines using the slope of the lines as the deciding        parameter. 

-> Using the set of right and left lane lines, obtain minimum and maximum (x,y) co-ordinates and draw lane lines between these points.

# Reflection

The short coming of this project is that while it's quite decent in recognizing lane lines, it works only in bright light conditions. As you can see from the results of my project on the challenge video, it only recognises parts of the left lane when there is a shadow. Also this project does not work on very curvy roads such as the ones you find while driving up/down the hill.

There is definitely lot of room for improvement for this project. One main improvement would be to obtain region of interest for all kinds of roads dynamically which makes it quite applicable to many situations. Once I am familiar with more advanced concepts in computer vision I will definitely get back to this project and modify it for the better. 
