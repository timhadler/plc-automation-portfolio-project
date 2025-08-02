# CODESYS Change Log – PLC Automation Project

For details about FactoryIO Scene see FactoryIO\_Scenelog.md

## \[v1.0.0] – 31/07/25

FactoryIO scene: v1.0

### Added

* Initial version of 'Stage1\_PartDetection' function block for stage one
* 'BitsToByte' Function, 'FB\_ConveyorController', 'FB\_PusherController', 'FB\_VisionSensorAD' Function Blocks
* Stage 1 State machine implemented (IDLE, RUNNING)
* Metal and unknown parts are rejected based on vision sensor bits



### Notes

* System currently runs in continuous loop for testing (RUNNING state is default after startup)
* No Start/Stop control implemented yet
* Pusher logic tested in RUNNING state only



## \[v1.0.1] – 2/08/2025

FactoryIO scene: v1.1

### Changed

* Control logic now relies on a diffuser sensor to initiate the Pusher to reject materials
  -- Reason: More reliable than using a timer



## \[v1.1.0] – 02/08/25

FactoryIO scene: v1.2

### Added

* 'FB\_OperatorPanel' Ladder Logic POU controlling operator input (Start, Stop, Reset, Emergency Stop)
* Output signals for button lights



### Changed

* Stage 1 state machine transitions using Operator Start/Stop triggers (including eStop)



### Notes

* Safety interlocking for individual FBs not implemented yet



