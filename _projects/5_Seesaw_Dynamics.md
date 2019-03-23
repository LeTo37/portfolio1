---
layout: project
title: Spring-Loaded Seesaw Dynamics
date: December, 2018
image: public/images/seesaw.png
permalink: "Spring-Loaded Seesaw Dynamics.html"
---

## Overview
For my final project for a Machine Dynamics course I took, I mathematically modeled and simulated the basic dynamincs the plastic impacts involved in the system. The system was setup such that a mass will fall on one end of the seesaw and this plastic impact will prescribe the resulting trajectory of the mass on the other end of the seesaw. This simulation was done in Mathematica using Euler-Lagrange principles.

## Simulation Video

<div align="center">
  <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/QAdnnNdbUMs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

## Code
The Wolfram Mathematica code used to develop this simuation can be found [here](public/Spring_Loaded_Seesaw_Code.pdf)

## Code Explained
The first part of the code defines a few useful functions that are used later in the program.

The next part of the code sets up all of the transformation matrices - with reference to a ground frame - of all of the necessary points used to model the dynamics.

The next section defines a few parameters that can be adjusted such as the mass of the seesaw and the 'weights', the spring coefficients, the gravitational acceleration, etc.

The code then uses these parameters and transformation matrices to setup the Lagrangian equation used to describe the system dynamics. i.e. the difference in kinetic and potential energies of the system. 

The pre-impact conditions and constraints are set up such that the system follows its expected pre-impact behaviour. Next the impacts are evaluated. This section defines the impact update laws and evaluates the plastic collisions that occur bewtween the masses and the seesaw while maintaining constraints such as the springs still being attached to the seesaw and ground. 

The evaluation of these laws and constraints then give the post-impact intial conditions and behaviour which is then simulated.

The last section of the code is used to plot the results of this simulation and then animate those results. This animation is shown above.

