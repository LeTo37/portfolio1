---
layout: project
title: DC Motor Control
date: March, 2019
image: public/images/DC_Motor_Control.jpg
permalink: "DC Motor Control.html"
---

## Overview
This project was to build and code an intelligent motor controller. The structure of the controller is such that it receives inputs from the client using a MATLAB user interface, which in return receives the results of the motor which is then plotted and displayed to the client.

The system is able to follow a reference trajectory, velocity or torque by spinning a brushed DC motor's shaft with an inertial load attached. This is achieved using two feedback control loops, implemented as a digital PID controllers which use values obtained from the encoder built in to the motor as well as from a current sensor.

## Video
Below is a video showcasing the DC Motor being controlled:
<div align="center">
  <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/FJjh2uwLuLQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


## Software
All of the software can be be found [here](https://github.com/LeTo37/DC-Motor-Control)

The two parts of this project are split into the DC motor control and the client interface.

* C code was used to program the PIC32MX795F512H microcontroller with an [NU32](http://hades.mech.northwestern.edu/index.php/NU32) breakout board.
* MATLAB code was used tot develop the client interface.

The interface looks like this:
<p align="center">
  <img src="public/images/DCMotorClient.png" width="500">
</p>

The above options presented to the client represent the capabilities of the controller.

## Hardware
The hardware used in this project include:

* Brushed DC Motor with a plastic bar attached to the shaft as an inertial load.
* An Encoder attached to the motor.
* A PIC32MX795F512H microcontroller with an NU32 breakout board.
* A dsPIC33FJ64MC802 micontroller used with a breakout board, programmed as a decoder.
* A breakout board for the DRV8835 H-Bridge.
* A breakout board for the MAX9918 current-sense amplifier.
* An [NScope](https://www.nscope.org/) digital oscilloscope was used for debugging.

The circuitry was connected as follows:
<p align="center">
  <img src="public/images/DCMotorCircuit.png" width="500">
</p>

## Result
The image below shows how the motor was able to track a cubic trajectory with an average error of only 1.1 degrees:
<p align="center">
  <img src="public/images/DCMotorTrack.jpg" width="500">
</p>