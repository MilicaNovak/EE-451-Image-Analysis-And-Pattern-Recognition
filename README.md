# EE-451-Image-Analysis-And-Pattern-Recognition

Materials from EPFL's course, solution of assignments and project

In the repo, there are two homeworks and project.
Below we will give description of project:

## Introduction
In this special project, your task is to use your image analysis skills to
control a [LEGO<sup>&copy;</sup> MINDSTORMS EV3][mindstorms] robot
(see figure below) in a specific environment.
The environment is a flat arena of approximately 3 meters by 3 meters
containing visual elements such as different geometric shapes and handwritten
digits with different colors (see figure below).
The exact disposition of these elements may vary.
The robot uses the live view of the environment by a camera mounted above
the arena and pointed directly at the arena, such that the plane of the arena
is parallel to the image plane of the camera.

![](/project/fig_lego_mindstorms.jpg)

![](/project/fig_environment.jpg)


Different tasks to be implemented are defined in the following section,
each of them allowing you to collect a given number of points.
During the last session on Friday, June 1, each team will run its code
on the robot and try to collect as many points as possible.
You will also present your approach to the problem and explain briefly
how you implemented your solution.

[mindstorms]: https://www.lego.com/en-us/mindstorms/products/mindstorms-ev3-31313

## Task: Solve the puzzle
Your main task is to control the robot and make it solve the puzzle!
The detailed scenario is defined as follows:
* Several shapes with different colors and sizes are placed on the arena.
Some of them have a handwritten digit (zero to eight) printed on them,
we call them “Pieces”.
The “Holes” are the ones without anything printed on them.
* The robot should fit all “pieces” to their corresponding “holes”,
one by one, in the right order.
* The order of “pieces” are defined by their labels:
the piece with the smallest value on top of it should be taken care of at first,
the one with the second smallest digit should be next, and so on to the last piece.
* The robot starts from a random position.
A black arrow on the top side of the robot will allow you to localize it
and detect its orientation.
Please note that this arrow is the only black object in the arena.
* Once all pieces are successfully fit, the robot has to go back to the home plate.
The home plate is the only circle in the arena.
* Each piece successfully fit to its right hole by the robot brings 3 points
and each mistake costs you 1 point.

### Notes
1. We call a “hole” a fit for a “piece” when they have similar shapes.
Please note **that they can have different sizes, colors and orientations!**

1. All digits are oriented vertically regarding frames orientation.

1. The pieces and holes are virtual and printed on the table.
They will not be physically picked up and dropped off by the robot.
By going on top of a shape and “beeping” once, we consider it as “taken”.
By “beeping” twice we consider it as “released”.

### Bonus
There is 6 extra points if the robot could still respect the right order
even in case where digits are not oriented vertically.



### Data
In order to get started, we provide a sequence of images taken in conditions
similar to the conditions in which you will run your algorithm:
[data/project-data.tar.gz][project-data] contains images of a smaller arena
containing shapes and digits and showing the robot following the path that
it is supposed to follow.
The final arena might be up to two times bigger but the distance of the camera
should not vary too much and the resolution of the image is not expected
to change drastically.
These frames also contain images of different elements
(namely different kinds of geometrical shapes and other related objects).
You are free to crop and use them to train classifiers, if needed.

For digits classification, you are free to use the MNIST dataset that you have
seen in [Lab 3][l03].

You are free to acquire more images by yourself if you think that it is necessary.
This can be done during the scheduled sessions.

[project-data]: /data/project-data.tar.gz
[l03]: /assignments/lab_03_classification.ipynb
