---
layout: project
title: Isolating Moving Objects
date: November, 2017
image: public/images/Isolating_obj.png
permalink: "Isolating Moving Objects"
---

## Overview
For final thesis for my undergradute degree (B.Sc Mechatronics), I set out to develop a computer vision software system investigate different methods with the eventual goal of isolating an object of interest undergoing motion from a scene that exhibits background motion.

### Specifications
The development of the system was done:
* Using C++ programming language
* Using the open source computer vision library, OpenCV
* Within the frameworks of the CodeBlocks IDE.
* On a frame-by-frame basis, each frame had the necessary image processing and vision techniques applied to it.

### System Development
The code developed and investigated for this project can be split into three main tasks:

* **Preprocessing:** These are the image processing techniques applied before any background subtraction was applied, such as blurring and edge detection.

* **Background Subtraction:** These are statistically based pixel level algorithms the seperate each frame into foreground objects and background objects.

* **Object of Interest Identification:** These are methods for matching a template image of a predetermined object of interest to any foreground objects found in the binary image produced by the background subtraction stage.

### Results and Conclusions

The images below show the two best performing combination of methods. In both images, the top left block shows the raw frame, the top right block shows the binary image produced by background subtraction, the bottom left block shows the process of the template matching method being used and the bottom right block shows the raw frame with a bounding box surrounding the object of interest.


| <img src="public/images/cont_match.png" width="35%"> <img src="public/images/feat_hom.png" width="35%">| 
|:--:| 
| *These are screenshots of the contour matching(left) and feature homography(right) methods being used for object of interest identification.* |



After running numerous tests - with a testing environment set up to reward accuracy, performance and false positive/negative response - the final best performing system used **Gaussian blurring** and **Sobel edge detection** for _preprocessing_, a **mixture of Gaussians** method for _background subtraction_ and a method that finds and matches the
maximum length contour in the template image and the current frame (**contour matching**) for _object of interest
identification_.




### Video
This video shows the best performing combination of methods in action:

**To be added soon**
<div align="center">
  <iframe width="560" height="315" src="" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

### Further Reading

If you would like access to the full thesis or would like to find out more about it, please don't hesitate to [contact](/portfolio/contact/) me.
