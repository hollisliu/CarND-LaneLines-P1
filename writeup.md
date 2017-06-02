# **Finding Lane Lines on the Road**

## Report

### Hanjie Liu

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 4 steps:

1. apply the canny filter to the original image for edge detection
2. mask the edge image with a manually defined mask as region of interest
3. find lines using the hough_lines function based on manually fine tuned parameters
4. blend the line image and the original image as the result

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by the following steps:

1. categorize lines based on the sign of slopes: positive for left and negative for right
2. compute the average slopes and average points for each side
3. set y value in the line equation to image height and 60% image height to compute bottom x coordinate and top x coordinate respectively.
4. draw base on top and bottom points



### 2. Identify potential shortcomings with your current pipeline


One shortcoming would be the pipeline doesn't recognize lines when the lane gets too segmented.

Another shortcoming is that the lane detected can be very shaky


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to constraint the slope for a smoother representation of lanes
