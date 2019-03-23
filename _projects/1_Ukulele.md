---
layout: project
title: Human-Robot Ukulele Player (H-RUP)
date: March, 2019
image: public/images/H_RUP.jpg
permalink: "Human-Robot Ukulele Player.html"
---

## Overview
This Project was to design, build, program and eventually play a Human-Robot Ukulele Player or H-RUP! The inspiration for this project came from a love of music, a will to learn the Ukulele and lack of being able to do so, so why not build a robot to help!
<div align="center">
  <iframe width="560" height="315" src="" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

This Robot is designed to help someone play a song on a Ukulele without pressing any chords, H-RUP presses the chords for you and has an LED giving you a 3 flash count down and telling you when to strum!

### Approach
The basic approach I followed was to develop a 4x4 bank of solenoids to be housed above a small section of the ukkulele neck, placed above a part of the ukulele whereby this bank of solenoids will be able to press a pretty comprehensive combination of notes/chords, enough to be able to play most, if not all songs.

These solenoids are controlled using a PIC32MX795F512H microcontroller and a driver circuit. The Ukulele and Solenoid housing were designed and constructed by 3D printing and Laser Cutting. Coding was done C and Python.


### Mechanical Design
The mechanical design of this project can be boiled down to 4 main objectives, it had to securely house the Ukulele, it had to place the solenoid bank in the correct position so as to be able to hit the right chords, it had to be stable and it had to be able to handle any heat dissapation from the solenoids. The final result of these objectives can be seen in both ".stl" format and in real life below:

<p align="center">
<script src="https://embed.github.com/view/3d/LeTo37/Ukulele_Player/master/Mechanical_Designs/Full_Assembly.stl"></script>
</p>

<p align="center">
  <img src="public/images/MechFullAssembly.png" height="25%" width="25%">
</p>

The design can be further broken down into **3D printed parts** and **Laser Cut Parts.**
The 3D printed parts were responsible for housing the Ukulele as well as providing stability to the design. As such a wide based structure shaped around the Ukulele was designed. This design is shown the stl file below.

<p align="center">
<script src="https://embed.github.com/view/3d/LeTo37/Ukulele_Player/master/Mechanical_Designs/3D_Prints/Base_and_Uke_Housing.stl"></script>
</p>


The laser cut parts were responsible for housing the solenoids above the right part of the Ukulele such that they are able to press chords. Three layers were designed such that the solenoids would be compressed from the bottom and top as well as aligned in the middle. This three layer design was chosen so that the solenoids can receive airflow to prevent overheating. Each layer fits around the threadbars as can be seen in the full assembly above and the layers are seperated by nuts on the threadbars. The three layers shown from left to right are a birds eye view of the top, middle and bottom layer respectively.

<p align="center">
  <img src="public/images/TopLayer.png" width="300" />
  <img src="public/images/MiddleLayer.png" width="300" /> 
  <img src="public/images/BottomLayer.png" width="300" />
</p>

## Electronics
<p align="center">
  <img src="public/images/Electronics.png" height ='300' width="300" />
</p>

### MicroController
The microcontroller being used to control this project is the PIC32MX795F512H with use of the [NU32](http://hades.mech.northwestern.edu/index.php/NU32) breakout board.

### Circuitry

The circuitry that is used to drive each solenoid consists of a Digital I/O pin from the microcontroller going through a 1 kilo Ohm resistor to the base of an NPN Darlington transistor. The collector of which is connected to a 7.5V power supply (32W, 4.32A AC/DC wall adapter) through a parallel combination of the solenoid being activated and a flyback diode. The emmitter of the transistor is connected to ground. The datasheets for the components used can be found [here](https://github.com/LeTo37/Ukulele_Player/tree/master/Docs)

A simple connection from the PIC32 Digital I/O to an LED with a 330 Ohm pulldown resistor. This LED is used as the Start and Strum Light to indicate to the user when to strum.

Both circuit designs shown below, from left to right is the solenoid driver and LED circuit:

<p align="center">
  <img src="public/images/SolenoidDriver.png" width="300" />
  <img src="public/images/LED.png" width="300" /> 
</p>

### Code

The [code](https://github.com/LeTo37/Ukulele_Player/tree/master/Code) for this project was split into microcontroller code - done in C - and user code - done in Python   

The purpose of the **Microcontroller Code** is to read a song sent into the microcontroller by the user code and convert that into digital highs or lows such that the solenoids actuate at the correct time. This allows the H-RUP to press chords on the Ukulele in the correct sequence and timing, producing a song.

The **User Code** is a python executable called **Ukelele Jukebox**, it gives the user a choice, the user can either write their own song to be played with H-RUP or the user can choose from a list of preset songs and play that.


### Future Work
Further work on this project could include:

* Redesigning the mechanical structure a bit to make it smaller, perhaps small enough to be able to hold it like a normal Ukulele.
* The design and printing of a dedicated PCB for the H-RUP as opposed to leaving everything on a breadboard.
* Adding a scoring system, that listens to the user's strumming and compares it to the timing of the Strum LED
* Adding more songs to the repertoire

### Further Reading
For more detailed descriptions of how this all came together, please visit the project's Github repository found [here!](https://github.com/LeTo37/Ukulele_Player)


<p align="center">
  <img src="public/images/H_RUP_All.png" />
</p>