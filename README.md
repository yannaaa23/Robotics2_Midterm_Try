<h1 align="center"> SPHERICAL MANIPULATOR </h1>
<hr> 
<br>

## Table of Contents
  - [I. Abstract](#i.-abstract-)
  - [II. Introduction](#-ii.-introduction-)
  - [III. Degrees of Freedom](#-iii.-degrees-of-freedom-)
  - [IV. Kinematic Diagram and D-H Frame](#-iv.-kinematic-diagram-and-d-h-frame-)
  - [V. D-H Parametric Table](#-v.-d-h-parametric-table-)
  - [VI. Homogeneous Transformation Matrix](#-vi.-homogeneous-transformation-matrix-)
  - [VII. Inverse Kinematics](#-vii.-inverse-kinematics-)
  - [VIII. Forward and Inverse Kinematics (GUI calculator)](#-viii.-forward-and-inverse-kinematics-(gui-calculator)-)
  - [IX. References](#-ix.-references-)
  - [X. Members](#-x.-members)
<hr> 
<br>

## I. Abstract
    (description)
<hr> 
<br>


## II. Introduction

  <p align="center">
  <img src=https://github.com/MEXECardenas/SPHERICAL_G7_Assignment_2024/blob/0b0c965065028159e971cf92570e9344e1e41f4b/Kinematic%20Diagrams%20with%20D-H%20Parametric%20Tables/Spherical%20Manipulator%20-%20Modern%20Variant.png alt=Spherical-Manipulator-Modern-Variant style="height: 300px; float: left;">
  <img src=https://github.com/MEXECardenas/SPHERICAL_G7_Assignment_2024/blob/a9a0b089f3911adfcc915ab37b061117838ae024/Kinematic%20Diagrams%20with%20D-H%20Parametric%20Tables/Spherical%20Manipulator%20(Modern%20Variant).gif alt=Spherical-Manipulator-(Modern-Variant) style="height: 300px; float: right;">
  </p>
</div>
<br>

<span style="font-family: Arial, sans-serif; font-size: 18px;">
    Spherical Manipulator is a stationary manipulator featuring two rotational joints, one prismatic joint, an arm attached to a robotic base, and a twisting joint. The spherical manipulator, also known as the polar manipulator, has three mutually perpendicular axes and is well known in the history of robotics. This is because the first industrial robot, Unimate, was a spherical robot developed in the 1950s. The zero z0 z1 and z2, this configuration facilitates the movement in spherical coordinates, while the spherical manipulator once held its ground, it has relinquished practice practicality in the workplace yielding to the versatility of six axes articulated manipulators.</span>
<hr> 
<br>



## III. Degrees of Freedom

<span style="font-family: Arial, sans-serif; font-size: 18px;">
    In robotics, degrees of freedom (DOF) refer to the number of independent parameters that define the configuration or motion of a robot. Essentially, it indicates how many different ways a robot can move within its environment.The more the degree of freedom, the more flexible and adaptable the robot. A robot with high DoF can make more complex movements and perform a variety of tasks. </span>
  
<p class="blank-line">&nbsp;</p>

#### The Ideal Degrees of Freedom:
  - A <b>point</b> in 2D: 2-DOF; in 3D space: 3-DOF
  - A <b>rigid body</b> in 3D: 6-DOF
  - <b>Planar Manipulator</b>: 3-DOF
  - <b>Spatial manipulator</b>: 6-DOF
<br>

#### Types of Manipulator based on the number of Degrees of Freedom:
  - <b>Under-Actuated Manipulator</b>
      - Spatial Manipulator with less than 6-DOF
      - Planar Manipulator with less than 3-DOF
  - <b>Ideal manipulator</b>
      - Spatial Manipulator with exactly 6-DOF
      - Planar Manipulator with exactly 3-DOF
  - <b>Redundant manipulator</b>
      - Spatial Manipulator with more than 6-DOF
      - Planar Manipulator with more than 3-DOF
<br>

#### Grubler's Criterion for Mobility
  - Formula for the Mobility of Spatial Manipulator
    $$M = 6n - \sum_{i=1}^m (6-Ci)$$
  - Formula for the Mobility of Planar Manipulator
    $$M = 3n - \sum_{i=1}^m (3-Ci)$$

#### Mechanical Manipulator Anatomy

|  Joint type  | DOF *f* | Constraints *c* between two planar rigid bodies | Constraints *c* between two spatial rigid bodies |
|         ---: |     :---:      |     :---:     |     :---:    |
|  Revolute (R)  |  1  |  2  |  5  |
|  Prismatic (P)  |  1  |  2  |  5  |
|  Helical (H)  |  1  |  N/A  |  5  |
|  Cylindrical (C)  |  2  |  N/A  |  4  |
|  Universal (U)  |  2  |  N/A  |  4  |
|  Spherical (S)  |  3  |  N/A  |  3  |
<br>

#### Degrees of Freedom (DOF) Computation
  $$M = 6n - \sum_{i=1}^m (6-Ci)$$
  
<hr> 
<br>


## IV. Kinematic Diagram and D-H Frame
    (description)
<br>
<span style="font-family: Arial, sans-serif; font-size: 18px;">Computation:</span>
<p align="center">
  <img src=(paste-link-here) alt=(Name) width="700"/>
</p>
<hr> 
<br>


## V. D-H Parametric Table
    (description)
<br>
<span style="font-family: Arial, sans-serif; font-size: 18px;">Computation:</span>
<p align="center">
  <img src=(paste-link-here) alt=(Name) width="700"/>
</p>
<hr> 
<br>


## VI. Homogeneous Transformation Matrix
    (description)
<br>
<span style="font-family: Arial, sans-serif; font-size: 18px;">Computation:</span>
<p align="center">
  <img src=(paste-link-here) alt=(Name) width="700"/>
</p>
<hr> 
<br>


## VII. Inverse Kinematics
    (description)
<br>
<span style="font-family: Arial, sans-serif; font-size: 18px;">Computation:</span>
<p align="center">
  <img src=(paste-link-here) alt=(Name) width="700"/>
</p>
<hr> 
<br>


## VIII. Forward and Inverse Kinematics (GUI calculator)
    (description)
<br>
<span style="font-family: Arial, sans-serif; font-size: 18px;">Computation:</span>
<p align="center">
  <img src=(paste-link-here) alt=(Name) width="700"/>
</p>
<hr> 
<br>


### IX. References
-
-
-
-
-
<hr> 
<br>


## X. Members:
  - Alojado, Stephen Gabriel S.
  - Apostol, Jan Benedict D.
  - Cardenas, Sofia Bianca J.
  - Catapang, Jamil Darrius S.
  - Umali, Ariane Mae D.<br>
