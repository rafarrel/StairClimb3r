# StairClimb3r Software Requirements Specification

## 1) Introduction
### 1.1) Purpose
This software requirements specification document describes the functional and nonfunctional requirements for software release 0.1 of StairClimb3r. It is intended to be used by all project contributors as the central definition of project requirements. This document will be updated at the beginning of each new development cycle with any requirements defined for that cycle. Unless otherwise noted, all requirements specified here are committed for release 0.1.


### 1.2) Document conventions
No special typographical conventions are used in this SRS.


### 1.3) Project scope
StairClimb3r will encapsulate a Lego Mindstorms EV3-based robotic system that will learn to climb up and down stairs through trial and error. Software for this project will be responsible for controlling robot hardware and training it to interact with its environment. 


## 2) Overall description
### 2.1) Product perspective
StairClimb3r is a new robotic system that is intended to be used for educational purposes (i.e. demonstrating how reinforcement learning can be used in contemporary robotics). The context diagram below illustrates all external entities and system interfaces for release 0.1.

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
*OE-1*: Project software shall operate on the Lego Mindstorms EV3 Intelligent Brick with [ev3dev](https://www.ev3dev.org/) version 2020-04-10 installed.

*OE-2*: Project software shall be accessed and updated through SSH communication between ev3dev and any SSH-compliant device.


### 2.4) Design and implementation constraints
*CO-1*: Project documentation shall use [Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github) format for quick, maintainable updates.

*CO-2*: Project documentation shall use [Mermaid](https://mermaid-js.github.io/mermaid/#/) for all diagrams for quick, maintainable updates.

*CO-3*: Project software shall conform to [The Power of Ten – Rules for Developing Safety Critical Code](https://spinroot.com/gerard/pdf/P10.pdf) as risk of system failure should be minimized during robot training.

*CO-4*: Project software shall use C++ for robot interaction and control as development language must be supported out-of-the-box on ev3dev and provide a balance of real-time performance and scalability.

*CO-5*: Project software shall use C++ or Python for Artificial Intelligence as development language must be supported out-of-the-box on ev3dev.

*CO-6*: Project software written in C++ shall conform to the [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines) for standardized code development.

*CO-7*: Project software written in Python shall conform to [PEP 8 – Style Guide for Python Code](https://peps.python.org/pep-0008/) for standardized code development.


### 2.5) Assumptions and dependencies
*AS-1*: Users of this software will have their own robot hardware built with ev3dev installed.

*AS-2*: Users of this software will have a Lego Mindstorms EV3 Infrared Remote synced to the robot hardware.

*AS-3*: Users of this software will position their StairClimb3r robot in front of stairs so it only has to walk forward to find them. 


## 3) System features
See "current requirement" labeled [issues](https://github.com/rafarrel/StairClimb3r/issues) for all system features selected for the current development cycle. 

See [planned features](../PROJECT_PLANNING/PLANNED_FEATURES.md) for planned/future features that are not selected for the current development cycle.


## 4) Data requirements
### 4.1) Logical data model
TBD


### 4.2) Data dictionary
TBD


### 4.3) Reports
TBD


### 4.4) Data acquisition, integrity, retention, and disposal
TBD


## 5) External interface requirements
### 5.1) User interfaces
TBD


### 5.2) Software interfaces
TBD


### 5.3) Hardware interfaces
TBD


### 5.4) Communications interfaces
TBD


## 6) Quality attributes
### 6.1) Usability
TBD


### 6.2) Performance
TBD


### 6.3) Security
TBD


### 6.4) Safety
TBD


### 6.x [others]
TBD


## 7) Internationalization and localization requirements
TBD


## 8) Other requirements
TBD
