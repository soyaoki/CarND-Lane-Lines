# **Finding Lane Lines on the Road** 
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

My pipeline consisted of following 5 steps. 

(1) I converted the images to grayscale.

(2) Then I filtered the images by gaussian and detected lines by Canny.

(3) After that, I masked the images.

(4) I detected lines using by Hough for the masked images.

(5) I devided the lines to right and left lines and calcurated each average lines by liner regression.
     By srope of line, lines were devided to right and left. And I calculated each average line using by "np.polyfit" function.

Final output (Result of processing) is shonwn below.

[image2]:'test_images_output/solidYellowCurve2.jpg' "Result"


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be that ROI is defined as constant value. If road shape changes like curve (challenge.mp4),  
    constant ROI is not fit to the road shape.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to set ROI adaptively using color information. 
    For example since road is often black, area where brightness values are less than threshold is set as ROI.

