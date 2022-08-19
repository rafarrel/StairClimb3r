# StairClimb3r Software Requirements Specification

## 1) Introduction
### 1.1) Purpose
This software requirements specification document describes the functional and nonfunctional requirements for software release 1.0 of StairClimb3r. This document is intended to be used by all project contributors and should serve as the central definition of project requirements. Unless otherwise noted, all requirements specified here are committed for release 1.0.


### 1.2) Document conventions
No special typographical conventions are used in this SRS.


### 1.3) Project scope
StairClimb3r will encapsulate a Lego Mindstorms EV3-based robotic system that will learn to climb up and down stairs through trial and error. Software for this project will be responsible for controlling robot hardware and training it to interact with its environment. For the full project roadmap, see *StairClimb3r Roadmap*[1].


### 1.4) References
1. Farrell, Alex. *StairClimb3r Roadmap*, [Project Roadmap](../PROJECT_VISION/ROADMAP.md).
2. Holzmann, Gerard. *The Power of Ten – Rules for Developing Safety Critical Code*, https://spinroot.com/gerard/pdf/P10.pdf.
3. Stroustrup, Sutter. *C++ Core Guidelines*, https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines
4. Rossum, Warsaw, Coghlan. *PEP 8 – Style Guide for Python Code*, https://peps.python.org/pep-0008/
5. Mermaid-js. *Mermaid*, https://mermaid-js.github.io/mermaid/#/
6. Google. *Tensorflow*, https://www.tensorflow.org/
7. ev3dev. *ev3dev*, https://www.ev3dev.org/


## 2) Overall description
### 2.1) Product perspective
StairClimb3r is a new robotic system that is intended to be used for educational purposes (i.e. demonstrating how reinforcement learning can be used in contemporary robotics). The context diagram below illustrates all external entities and system interfaces for release 1.0.

```mermaid
flowchart TD;
   %% Nodes
   user(["User"]);
   remote[("Infrared Remote")];
   device("SSH-Compliant\n Device");
   ev3dev("ev3dev");
   robot[("StairClimb3r\n Robot")];
   software(("StairClimb3r\n Software"));
   
   %% Node styles
   classDef Software fill:#be4f62;
   classDef Devices fill:#ffe5b4;
   classDef Hardware fill:#87CEEB;
   classDef Users fill:#90ee90;
   
   class software Software;
   class ev3dev,device Devices;
   class robot,remote Hardware;
   class user Users;
   
   %% Links
   user -- "input" ---> device;
   user -- "input" ---> remote;
   remote -- "operating\n mode" ---> ev3dev;
   device -- "updated software" ---> ev3dev;
   ev3dev -- "robot files\n (remote access)" ---> device;
   ev3dev -- "action for robot" ---> robot;
   robot -- "action result" ---> ev3dev;
   ev3dev -- "C++ API for\n robot hardware" ---> software;
   software -- "C++ API call" ---> ev3dev;
   ev3dev -- "C++ API call\n result" ---> software;
```


### 2.2) User classes and characteristics
| User Class | Description |
|------------|-------------|
| Project Developers (favored) | Any developers contributing to StairClimb3r. They are the primarily targeted user class as this project is intended for hands-on practice implementing reinforcement learning in a robotics context. | 
| Other Developers | Developers of other, unrelated projects. All code will be released as open-source and can be used by developers in other projects. |


### 2.3) Operating environment
*OE-1*: Project software shall operate on the Lego Mindstorms EV3 Intelligent Brick with *ev3dev*[7] version 2020-04-10 installed.

*OE-2*: Project software shall be accessed and updated through SSH communication between ev3dev and any SSH-compliant device.


### 2.4) Design and implementation constraints
*CO-1*: Project documentation shall use markdown format for quick, maintainable updates.

*CO-2*: Project documentation shall use *Mermaid*[5] for all diagrams for quick, maintainable updates.

*CO-3*: Project software shall conform to *The Power of Ten – Rules for Developing Safety Critical Code*[2] as risk of system failure should be minimized during robot training.

*CO-4*: Project software shall use *Tensorflow*[6] version 2 for all Artifical Intelligence as learning algorithms must be efficient and secure.

*CO-5*: Project software shall use C++ for robot interaction and control as development language must be supported out-of-the-box on ev3dev and provide a balance of real-time performance and scalability.

*CO-6*: Project software shall use C++ or Python for Artificial Intelligence as development language must be supported out-of-the-box on ev3dev and Tensorflow.

*CO-7*: Project software written in C++ shall conform to the *C++ Core Guidelines*[3] for standardized code development.

*CO-8*: Project software written in Python shall conform to *PEP 8 – Style Guide for Python Code*[4] for standardized code development.


### 2.5) Assumptions and dependencies
*AS-1*: Users of this software will have their own robot hardware built with *ev3dev*[7] installed.

*AS-2*: Users of this software will have a Lego Mindstorms Ev3 Infrared Remote synced to the robot hardware.

*AS-3*: Users of this software will position StairClimb3r in front of stairs so it only has to walk forward to find them.

*DE-1*: *Tensorflow*[6] version 2 must be installed on ev3dev. 


## 3) System features
### 3.1 Set operating mode
#### 3.1.1 Description
Any user of StairClimb3r should be able to set the operating mode (Learning, Active, Idle) using the Lego Mindstorms Ev3 Infrared Remote at any time while the robot is running. The user should be able to change the operating mode while the robot is in another operating mode (ex: changing from Learning to Active mode). Priority: High.

#### 3.1.2 Functional requirements
ADD HERE

### 3.2 Learning mode
#### 3.2.1 Description
While in Learning mode, StairClimb3r should continuously attempt to climb up/down the stairs in front of it, updating its learning model with each attempt. StairClimb3r should not stop this behavior until the operating mode is changed or the robot is powered off. Priority: High.

#### 3.2.2 Functional requirements
ADD HERE

### 3.3 Active mode
#### 3.3.1 Description
While in Active mode, StairClimb3r should use its learning model to walk up/down the stairs in front of it without updating the learning model. It should keep a log of all its movements for review by the user and stop when it has successfully climbed both up and down the stairs. Priority: High.

#### 3.3.2 Functional requirements
ADD HERE

### 3.4 Idle mode
#### 3.4.1 Description
While in Idle mode, StairClimb3r should stand by and do nothing while waiting for the learning mode to change. Priority: Medium.

#### 3.4.2 Functional requirements
ADD HERE


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
