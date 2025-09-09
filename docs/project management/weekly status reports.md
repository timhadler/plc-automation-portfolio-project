# Weekly Status Reports

**Project**: PLC Automation Portfolio - Smart Manufacturing Line

## Week 1 (ending 03/08/25)

**Current Phase:** 2 - PLC Simulation Integration

### Progress:

* Completed Phase 1 - setup and tested connection between CODESYS and FactoryIO
* Complete setup and testing of Stage 1 and 2 of the manufacturing line
* Integrated Operator controls - Start, Stop, Reset, Emergency Stop
* Implemented inter-state communication to transition between states

### Challenges

* FactoryIO sensor input values delayed after fresh downloads, causing incorrect Emergency Stop latching - Solution: Operator Reset after connection completed
* Falling edge detection did not behave consistently with digital sensor output - replaced with flag signal
* Initial confusion around FactoryIO Modbus roles clarified. Current setup: Client: FactoryIO, Server: CODESYS

### Plans for next week

* Begin development of Stage 3 - Assembly
* Implement Safety interlocking for individual controllers
* Consider adding unit test cases using simulation triggers
* Implement part counting, production rate calculations, and fault detection

**Status:** On track

**Next Deadline:** Complete Phase 2 by 12/08/25

## Week 2 (ending 10/08/25)

**Current Phase:** 2 - PLC Simulation Integration

### Progress

* Created and tested function blocks for Stage 3 - Assembly (Positioners, Two-Axis Pick and Place)
* Isolated existing function blocks I/O from internal signals using Properties and Methods

### Challenges

* Delay in FactoryIO setting 'IsMoving' variables for the pick and place made it difficult to ensure only one action was being commanded at a time. A robust control system needed to be implemented - Solution: Circular buffer and internal state machine to control sequences of commands. 

### Plans for next week

* Finish Phase 2
  - Finish Stage 3 control, implementing FBs prepared last week
  - Implement Safety Interlocking
  - Introduce fault handling
  - Finish Phase 2
* Start Phase 2 - HMI Integration

**Status:** Behind

**Next Deadline:** Complete Phase 2 by 12/08/25

## Week 3 (ending 17/08/25)

**Current Phase:** 2 - PLC Simulation Integration

### Progress

* Completed Phase 2 - PLC Simulation Integration
* Implemented circular buffer to queue commands for stations (Pick and Place station, Positioners)
* Added eStop interlocks for each output controlling FB
* Added fault handling (Stage 2)
* Added part counting and time tracking

### Challenges

* Getting the Pick and Place station and Positioners to execute one command at a time - Solution: Circular buffer and internal state machine to control sequences of commands. 

### Plans for next week

* Setup GitHub repo for project demonstration of Phase 2
* Plan timeline for Phase 3 - HMI Integration

**Status:** Complete

**Next Deadline:** TBD
