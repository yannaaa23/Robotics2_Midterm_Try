<h1 align="center"> Robotics 2 - Forward and Inverse Kinematics of Spherical Manipulator </h1>
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

<p align="justify"> 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><i>Spherical Manipulator</i></b> is a stationary manipulator featuring two revolute joints and one prismatic joint, with an arm attached to a robotic base, and a twisting joint. The spherical manipulator was also known as the <b><i>Polar Manipulator</i></b>. It has three mutually perpendicular axes and is well known in the history of robotics, because the first industrial robot, <b><i>Unimate</i></b>, was a spherical robot developed in the 1950s. It is also a type of robotic manipulator that operates with a spherical working envelope. Unlike traditional robotic arms that typically move in a planar or linear fashion, spherical manipulators can move in any direction within a three-dimensional space. These robots often consist of multiple joints arranged in a spherical configuration, allowing for movement along multiple axes simultaneously. This configuration enables them to reach points in 3D space with greater flexibility compared to traditional robotic arms.</p>

<p align="justify">
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Knowing that spherical manipulators have an arm which forms a spherical coordinate system. In mathematics, a spherical coordinate system is a three-dimensional coordinate system in which the position of a point is specified by three numbers: the radial distance from a fixed origin, the polar angle measured from a fixed zenith direction, and the azimuth angle of its orthogonal projection on a reference plane that passes through the origin and is orthogonal to the zenith, measured from a fixed reference direction. The radial distance is also known as the radius or radial coordinate. The polar angle is also known as the zenith angle, normal angle, colatitude, or inclination angle.</p>

  <p align="justify">
  &nbsp;&nbsp;&nbsp;&nbsp;Spherical Manipulators perform three distinct movements: rotation, elevation, and extension from a stationary base–giving them a spherical/polar working envelope. This configuration allows the robot to move freely and with great flexibility, making it ideal for a variety of jobs. Here is a breakdown of the movements:</p>

- **Rotation**: The robot can rotate around a vertical axis, which forms the base of the robot. This allows the robot to cover a wide horizontal range around its base.
- **Elevation**: The robot's arm can move up and down in a vertical plane, enabling it to reach different heights.
- **Extension**: The robot's arm can extend or retract, moving closer to or farther from the base.

<br>



## III. Degrees of Freedom

  <p align="justify"> 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In robotics, <b><i>Degrees of Freedom</i></b> (DOF) refer to the number of independent parameters that define the configuration or motion of a robot. Essentially, it indicates how many different ways a robot can move within its environment.The more the degree of freedom, the more flexible and adaptable the robot. A robot with high DOF can make more complex movements and perform a variety of tasks.</p>
  
<p class="blank-line">&nbsp;</p>

#### The Ideal Degrees of Freedom:
  - A <b>point</b> in 2D: 2-DOF; in 3D space: 3-DOF
  - A <b>rigid body</b> in 3D: 6-DOF
  - <b>Planar Manipulator</b>: 3-DOF
  - <b>Spatial manipulator</b>: 6-DOF
<br>

#### Types of Manipulator based on the number of Degrees of Freedom:
  - <b>Under-Actuated Manipulator</b>
      - _Spatial Manipulator_ with less than 6-DOF
      - _Planar Manipulator_ with less than 3-DOF
  - <b>Ideal manipulator</b>
      - _Spatial Manipulator_ with exactly 6-DOF
      - _Planar Manipulator_ with exactly 3-DOF
  - <b>Redundant manipulator</b>
      - _Spatial Manipulator_ with more than 6-DOF
      - _Planar Manipulator_ with more than 3-DOF
<br>

#### Grubler's Criterion for Mobility
  - Formula for the Mobility of _Spatial Manipulator_
    $$M = 6n - \sum_{i=1}^m (6-Ci)$$
  - Formula for the Mobility of _Planar Manipulator_
    $$M = 3n - \sum_{i=1}^m (3-Ci)$$

#### Grubler's Criterion for Mobility
<div align="center">
  
|  Formula for the Mobility of _Spatial Manipulator_  | Formula for the Mobility of _Planar Manipulator_ |
|         :---: |     :-----:      |
| $$M = 6n - \sum_{i=1}^m (6-Ci)$$ |  $$M = 3n - \sum_{i=1}^m (3-Ci)$$ |

</div>

<br>

#### Mechanical Manipulator Anatomy

<div align="center">
  
|  Joint type  | DOF *f* | Constraints *c* between two planar rigid bodies | Constraints *c* between two spatial rigid bodies |
|         ---: |     :-----:      |     :---:     |     :---:    |
|  Revolute (R)  |  1  |  2  |  5  |
|  Prismatic (P)  |  1  |  2  |  5  |
|  Helical (H)  |  1  |  N/A  |  5  |
|  Cylindrical (C)  |  2  |  N/A  |  4  |
|  Universal (U)  |  2  |  N/A  |  4  |
|  Spherical (S)  |  3  |  N/A  |  3  |

</div>

<br>

#### Degrees of Freedom (DOF) Computation:

<div align="center">
  
|  RRP Spherical Manipulator  | Solution |
|         :---: |     :-----:      |
| <img src=https://github.com/yannaaa23/Robotics2_Midterm_Try/blob/47e17d1beba12200080123f1b98170126aadcb39/First%20Page/DOF%20Fig.png alt=DOF-Fig style="height: 200px; float: left;"> |  $$M = 6n - \sum_{i=1}^m (6-Ci)$$  $$M = 6(3) - [(6-1) + (6-1) + (6-1)]$$  $$M = 18 - (5 + 5 + 5)$$  $$M = 18 - 15$$  $$M = 3$$  <p>&#8756; This is an Under-Actuated Spatial Manipulator with 3-DOF.</p> |

</div>

<hr> 
<br>


## IV. Kinematic Diagram and D-H Frame

  <p align="justify"> 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A <b><i>Kinematic Diagram</i></b> is a simplified representation of a mechanism that illustrates the motion of all the components without showing the forces or the physical dimensions that cause the motion. It is an important tool used in mechanical engineering to examine the motion of mechanisms. Typically, the diagram shows the mechanism's joints and links in schematic form. It is also a diagram that shows how the links and joints are connected together when all of the joint variables have a value of 0.
</p>
<br>

<div align="center">
  
<table border="1">
  <tr>
    <th colspan="2">Joint Variables</th>
  </tr>
  <tr>
    <td> <p align="center">Twisting or Revolute Joint</p> </td>
    <td> <p align="center">Prismatic Linear or Orthogonal Joints</p> </td>
  </tr>
  <tr>
    <td><img src=https://github.com/yannaaa23/Robotics2_Midterm_Try/blob/af546ee69ca1e190b12295380745505086c36d6b/First%20Page/Twisting%20or%20Revolute%20Joint.png alt=Twisting-or-Revolute-Joint style="height: 230px; float: left;"></td>
    <td><img src=https://github.com/yannaaa23/Robotics2_Midterm_Try/blob/af546ee69ca1e190b12295380745505086c36d6b/First%20Page/Prismatic%20Linear%20or%20Orthoganal%20Joint.png alt=Prismatic-Linear-or-Orthogonal-Joints style="height: 200px; float: left;"></td></td>
  </tr>
</table>
</div>
<br>

  <p align="justify"> 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <b><i>Links</i></b> are the rigid parts of the mechanical manipulator. A link is defined as a single part that can be a resistant body or a composite of resistant bodies with inflexible connections and relative motion in relation to other machine components. Also, joints are considered links and the values are constant:</p>
    
  - If it is revolute or twisting, links are drawn from the center of the rotation. </p>
  - If it is prismatic, either linear or orthogonal, links are drawn from the center of translation.
  - If it is from base, links are drawn from the center of gravity.
    
<br>

 <p align="justify"> 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <b><i>Joint Variables,</i></b> are the values that change when the joint moves. It is a connection between two or more links that allows for some motion, or potential motion, between them.  Joints are sometimes known as <b><i>kinematic pairs</i></b>.A joint variable has a two indicator which is the rotation of a counterclockwise arrow &#8634; and the arrow with the flat line at the tail &#8614;. We use this symbol &#8634; for the twisting and revolute joint and we label it as <b><i>theta</i></b> (&Theta;), theta is the rotation angle of the circle. While in a prismatic joint we use this symbol &#8614; and label it as <b><i>d,</i></b> <b><i>d</i></b> is the translation length. Remember that in joint variables, the numbering of joints will be based on their consecutive order.</p>
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


