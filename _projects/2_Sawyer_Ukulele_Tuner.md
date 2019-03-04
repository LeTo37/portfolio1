---
layout: project
title: Sawyer Ukulele Tuner
date: December, 2018
image: public/images/sawyerUku.png
permalink: "Sawyer Ukulele Tuner.html"
---

## Overview
For my final project for an Embedded Systems course I took, focusing on ROS, my group and I used a Rethink Robotics' Sawyer to tune a Ukulele.

### Explanation and Strategy
The goal of this project was to have a Rethink Robotics Sawyer robot autonomously tune a ukulele. The ukulele, a custom pick, and a custom tuning peg were all placed in pre-designated locations on a platform along with an alvar tag. Using the built-in head camera, Sawyer sensed the alvar tag and knew the relative locations of each of the aforemetnioned tools, it tuned the ukulele. The tuning process can be broken down into the following pattern:

1. Pick up the pick
2. Pluck the designated ukulele string
3. Listen to the produced pitch and find error from expected pitch
4. Set down the pick
5. Pick up the tuning block
6. Move to the designated tuning peg on the ukulele
7. Turn the peg by an ammount proportional to the pitch error
8. Set down the tuning block
9. Repeat steps 1-8 until pitch error is below a specified tolerance
10. Repeat steps 1-9 until on each of the 4 ukulele strings

After completing all of these steps, the expectation was to have a tuned ukulele, fit for use by the great man himself, Israel Kamakawiwoʻole.
### Result
We were successful in getting Sawyer to tune 1 string of the Ukulele but unfortunately did not have time to calibrate the system for the rest of the strings. The video below demonstrates this, tuning the Ukulele's A string to an A4 note, within 15 cents.

### Video
<div align="center">
  <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/4mWf8OjD35Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

### Code
The code used for this project, as well as further documentation on the project can be found in [this](https://github.com/zigzaugg/rosukulele) github repository.
