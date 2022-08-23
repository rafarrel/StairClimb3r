# Planned Features
High-level descriptions of future/planned features. This list is dynamic and will frequently change. If a feature listed here is selected to be included in a development cycle, it will be removed from this list and labeled as a "current requirement" [issue](https://github.com/rafarrel/StairClimb3r/labels).

## Set operating mode
Any user of StairClimb3r should be able to set the operating mode (Learning, Active, Idle) using the Lego Mindstorms Ev3 Infrared Remote at any time while the robot is running. The user should be able to change the operating mode while the robot is in another operating mode (ex: changing from Learning to Active mode). Priority: High.

## Learning mode
While in Learning mode, StairClimb3r should continuously attempt to climb up/down the stairs in front of it, updating its learning model with each attempt. StairClimb3r should not stop this behavior until the operating mode is changed or the robot is powered off. Priority: High.

## Active mode
While in Active mode, StairClimb3r should use its learning model to walk up/down the stairs in front of it without updating the learning model. It should keep a log of all its movements for review by the user and stop when it has successfully climbed both up and down the stairs. Priority: High.

## Idle mode
While in Idle mode, StairClimb3r should stand by and do nothing while waiting for the learning mode to change. Priority: Medium.
