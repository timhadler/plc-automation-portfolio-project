\# Weekly Status Reports

\*\*Project\*\*: PLC Automation Portfolio - Smart Manufacturing Line



\## Week 1 (ending 03/08/25)

\*\*Current Phase:\*\* 2 - PLC Simulation Integration



\### Progress:

* Completed Phase 1 - setup and tested connection between CODESYS and FactoryIO
* Complete setup and testing of Stage 1 and 2 of the manufacturing line
* Integrated Operator controls - Start, Stop, Reset, Emergency Stop
* Implemented inter-state communication to transition between states



\### Challenges

* FactoryIO sensor input values delayed after fresh downloads, causing incorrect Emergency Stop latching - Solution: Operator Reset after connection completed
* Falling edge detection did not behave consistently with digital sensor output - replaced with flag signal
* Initial confusion around FactoryIO Modbus roles clarified. Current setup: Client: FactoryIO, Server: CODESYS



\*\*\* Plans for next week

* Begin development of Stage 3 - Assembly
* Implement Safety interlocking for individual controllers
* Consider adding unit test cases using simulation triggers
* Implement part counting, production rate calculations, and fault detection



\*\*Status\*\*: On track

\*\*Next Deadline\*\*: Complete Phase 2 by 12/08/25

