# CODESYS Change Log – PLC Automation Project

For details about FactoryIO Scene changes, see FactoryIO\_Scenelog.md

Versioning follows the format: vA.B.C

A = Major project phase (e.g., PLC - Simulation Integration, HMI/SCADA Integration)

B = Major feature changes (e.g, adding stations/features)

C = Minor changes (e.g, bug fixes, code-only changes, sensor change/reconfigure)

---

## \[v1.0.0] – 31/07/25

**FactoryIO Scene**: v1.0  
**Status**: Complete

### Added

* Initial version of 'Stage1\_PartDetection' function block for stage one
* 'BitsToByte' Function, 'FB\_ConveyorController', 'FB\_PusherController', 'FB\_VisionSensorAD' Function Blocks
* Stage 1 State machine implemented (IDLE, RUNNING)
* Metal and unknown parts are rejected based on vision sensor bits

### Notes

* System currently runs in continuous loop for testing (RUNNING state is default after startup)
* No Start/Stop control implemented yet
* Pusher logic tested in RUNNING state only

---

## \[v1.0.1] – 2/08/2025

**FactoryIO Scene**: v1.1  
**Status**: Complete

### Changed

* Control logic now relies on a diffuser sensor to initiate the Pusher to reject materials
  -- Reason: More reliable than using a timer

---

## \[v1.1.0] – 02/08/25

**FactoryIO Scene**: v1.2  
**Status**: Complete

### Added

* 'FB\_OperatorPanel' Ladder Logic POU controlling operator input (Start, Stop, Reset, Emergency Stop)
* Output signals for button lights

### Changed

* Stage 1 state machine transitions using Operator Start/Stop triggers (including eStop)

### Notes

* Safety interlocking for individual FBs not implemented yet
* There is a delay when connecting to FactoryIO that causes NC switch inputs to be FALSE before they are set by the simulation. This delay activates the Emergency Stop latch logic in the Operator Panel FB. After a new download, the simulation will begin in Emergency Stop state, the reset button must be pressed to reset to a normal start.

---

## \[v1.2.0] - 03/08/25

**FactoryIO Scene**: v2.0  
**Status**: Completed

### Added

* 'Stage2\_MC' Machining Center Controller operates the machining center using internal state machine (IDLE, WAITING, RUNNING, COMPLETE)
* 'ReadyForMaterial' Flag communicated between Stage 1 and Stage 2 to transition states within Stage 1

### Changed

* Stages start signal is now a global 'SystemEnable' flag set by 'FB\_OperatorPanel'  
  -- Reason: Easier to access to enable multiple FB controllers
* Stage 1 now transitions between IDLE and RUNNING when Stage 2 is ready for material (local 'ReadyForMaterial' flag). Supplies material as needed (not continuous anymore)  
  -- Reason: Prevents part overflow of Stage 2. Demonstrates inter-stage communication to transition states.

---

## \[v1.2.1] - 05/08/25
**FactoryIO Scene:** v2.0  
** tatus:** Complete

### Changed
* Updated 'Stage1_PartDetection' and 'Stage2_MC' comments

---

## \[v1.2.2] - 05/08/25
**FactoryIO Scene:** v2.0  
**Status:** Completed

### Added
* 'FB_MachineCenter' Controller with Enabled, IsBusy, Progress, ProduceLids, Error Properties

### Changed
* Implemented FB controller for Machine Center instead of directly in 'Stage2_MC'  
 -- Reason: Modularises Machine Center control, clear I/O flow
* 'ReadyForPart' Property is used to pass flag to Stage 1 (instead of local FB output)  
 -- Reason: Seperates external hardware outputs from internal software flags for FB

---

## \[v1.2.3] - 05/08/25
**FactorIO Scene:** v2.0  
**Status:** Completed

### Added
* 'FB_Positioner' Controller for FactoryIO clamp positioners with methods; Clamp, Release, Lift, Lower (preparation for adding Stage 3 later)

### Notes
* Current FactoryIO Scene does not have positioners
* Tested on a test scene with test variables (clamp, raise etc)

---

## \[v1.2.4] - 11/08/25
**FactorIO Scene:** v2.0  
**Status:** Complete

### Added
* 'E_Command' Enum type for Pick and Place Station commands
* 'FB_CircularQueue_Command' Implements circular queue with methods; Enqueue, Dequeue, Clear, Peek. To managing commands for the Pick and Place
* 'FB_TwoAxisPaP' Contoller for FactoryIOs 2-axis Pick and Place - implements circular queue to manage sequenced commands  
  -- Methods: PickUp, PutDown, MoveXPos, MoveXNeg, ProcessCommand, IsMoving  
  -- Implements state machine to wait for station to stop moving before executing the next one. Only one command executed at a time. 

### Notes
* Have not added the Stage 3 function block yet. Tested new FBs using test script and scene. 

---

## \[v1.3.0] - 12/08/25
**FactorIO Scene:** v3.1
**Status:** Complete

### Added
* 'Stage3_Assembly' FB utilises internal state machine to assemble bases and lids into containers  
  - Waits for parts to be ready at the positioners, clamps them, then assembles them together, allowing the finished product to continue through

### Changed
* 'FB_Positioner' now utilises internal state machine and command queue to handle commands
  - Reason: Prevents multiple commands executing at once, and allows simple transition of states for the controller state machine (waits for command to be completed)

### Notes
* Bases can be allwed through without being assembled if they are too close to the preceding base product. 

---

## \[v1.3.1] - 12/08/25
**FactorIO Scene:** v3.1
**Status:** Complete

### Changed
* All function blocks that control outputs now implmented safety interlocking using 'GV_Flags.SystemEnabled'
  - Reason: Meets safety standards

---
