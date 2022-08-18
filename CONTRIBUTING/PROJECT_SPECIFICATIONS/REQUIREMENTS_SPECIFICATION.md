# Project Codename Stair-Climbing-Robot 
### Software Requirements Specification
<br>


## 1) Introduction
### 1.1) Purpose
This software requirements specification document describes the functional
and nonfunctional requirements for software release 1.0 of project codename
"Stair-Climbing-Robot". This document is intended to be used by all project
contributors and should serve as the central definition of project 
requirements. Unless otherwise noted, all requirements specified are 
committed for release 1.0.

### 1.2) Document conventions
No special typographical conventions are used in this SRS.
<br>

### 1.3) Project scope
Project codename "Stair-Climbing-Robot" will encapsulate a Lego Mindstorms
EV3-based robotic system that will learn to climb up and down stairs through
trial and error. Software for this project will be responsible for 
controlling robot hardware and training it to interact with its surrounding
environment. For the full project roadmap, see [INSERT PROJECT ROADMAP
REFERENCE CITATION HERE].

### 1.4) References
1. Contribution Team. *Project Codename 
"Stair-Climbing-Robot" Roadmap*,
[Project Roadmap](../PROJECT_VISION/ROADMAP.md)
<br>
2. [CITE AND ADD NASA THE POWER OF TEN REFERENCE HERE]


## 2) Overall description
### 2.1) Product perspective
Project codename "Stair-Climbing-Robot" is a new robotic system that is 
intended to be used for educational purposes (i.e. demonstrating how 
reinforcement learning can be used in contemporary robotics). The context
diagram below illustrates all external entities and system interfaces for 
release 1.0.
<br>
[ADD CONTEXT DIAGRAM HERE]

### 2.2) User classes and characteristics
| User Class | Description |
|------------|-------------|
| Project Developers (favored) | Any developers contributing to Project Codename "Stair-Climbing-Robot". They are the primarily targeted user class as this project is intended for hands-on practice implementing reinforcement learning in a robotics context. | 
| Other Developers | Developers of other, unrelated projects. All code will be released as open-source and can be used by developers in other projects. |

### 2.3) Operating environment
*OE-1*: Project software shall operate on the Lego Mindstorms EV3 
Intelligent Brick.

*OE-2*: Project software shall operate correctly with ev3dev, an embedded 
Linux distribution based on Debian, version 2020-04-10.

*OE-3*: Project software shall be accessed and updated through SSH 
communication between ev3dev and any SSH-compliant device.

### 2.4) Design and implementation constraints
*CO-1*: Project software shall use Google Tensorflow version 2 for
reinforcement learning as learning algorithms must be efficient and secure.

*CO-2*: Project software shall use C++ for robot interaction and control as 
development language must be supported out-of-the-box on ev3dev and provide a 
balance of real-time performance and scalability.

*CO-3*: Project software shall conform to [INSERT NASA THE POWER OF TEN 
REFERENCE HERE] as chances of system failure should be minimized during 
robot training.

### 2.5) Assumptions and dependencies

## 3) System features
### 3.x System feature X
#### 3.x.1 Description
#### 3.x.2 Functional requirements


## 4) Data requirements
### 4.1) Logical data model

### 4.2) Data dictionary

### 4.3) Reports

### 4.4) Data acquisition, integrity, retention, and disposal


## 5) External interface requirements
### 5.1) User interfaces

### 5.2) Software interfaces

### 5.3) Hardware interfaces

### 5.4) Communications interfaces


## 6) Quality attributes
### 6.1) Usability

### 6.2) Performance

### 6.3) Security

### 6.4) Safety

### 6.x [others]


## 7) Internationalization and localization requirements


## 8) Other requirements


## Appendix A: Glossary


## Appendix B: Analysis models
