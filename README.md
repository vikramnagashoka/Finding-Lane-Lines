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
