# **Finding Lane Lines on the Road** 


**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

The main part of the pipeline consisted of following steps:
* Take the image
* use opencv to create a gray scaled image
* apply gaussian smoothing on it using Gaussian Blur of opencv. 
* then it uses a canny filter to detect edges in the image using the color gradient. The parameters are hardcoded.
* then the algo ignores areas which are not of interest. Mainly in the center, were the camera recorded the lane lines of our lane. 
* On that image, we apply the Hough transformation to find lines. We recieve for every detected line its location.
* To decide, which lines are relevant or not relevant, only certain slopes are alowed for the left and the right lane line. Other lines are ignored. 
* The slope of the relevant lines are then avaraged for the right and left side.
* Using this avaraged slope and coordinates of the detected lines, we draw the linear function on top of the image with wich we started at the beginning. 
* The result is that the linear function lies mostly directly on the correctly detected line. 

Using the functionality mentioned above, we apply it on video which are a collection of images. 
 

### 2. Identify potential shortcomings with your current pipeline


Shortcomings:
* Hardcoded parameters are used. 
* Ansatz is heuristic! No machine learning is used to fine tune the parameters. 
* Calibration of camera and coordinate system of the vehicle is missing.
* Linear function is not the best model for lane lines used.


### 3. Suggest possible improvements to your pipeline

* A possible improvement would be to write better python code. Since it is my first time with python, it is acceptable.
* Devide code in more functions. 
* Use classes and objects.



