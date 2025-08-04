\# Project Timeline - PLC Automation Portfolio Project

This timeline documents key events, decisions, and design changes during the development of the PLC Automation Project

---

\## 30/07/25

\*\* Communication setup \*\*

* Connection between CODESYS and FactotyIO setup and tested
* Modbus TCP protocol chosen for connection as FactoryIO did not support EtherNet/IP

---

\## 31/07/25

\*\* Stage 1  \*\*

* Added initial version of Stage 1 Controller
* Added controllers for Conveyer, Vision Sensor, Pusher

---

\## 02/08/25

\*\* Operator Controls \*\*

* Improved part rejection by replacing timer with diffuser sensor
* Added operator control panel functionality - Start, Stop, Emergency Stop, Reset
* Decided that an inventory buffer will be added downstream of Stage 1, before Stage 2 to handle part overflow

---

\## 03/08/25

\*\* Stage 2 \*\*

* Decided to remove inventory buffer from the design, and use state based logic to control Stage 1. Stage 2 COMPLETE state sets 'ready for part' flag, which triggers Stage 1 to RUNNING. 
	- Reason: Demonstrates different stages communicating to transition states as needed. 
* Added Stage 2 (Machining Center) to FactoryIO lscene
* Implemented control logic to automate Stage 1 and 2. Stage 2 'tells' Stage 1 when to provide material.




