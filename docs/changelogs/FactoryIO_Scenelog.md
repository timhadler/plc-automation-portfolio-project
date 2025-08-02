\# FactoryIO Scene Change Log – PLC Automation Project



\## \[v1.0] – 31/07/25

\### Added

* Initial setup - Stage one (Part detection)
* Belt conveyor (4m)
* Emitter at one end
* A frame made from 3 walkway pillars right in front of emitter
* Vision sensor attached to frame, pointing down on conveyor
* Pneumatic pusher attached to side of conveyor, in front of sensor, pushes across the conveyor
* Conveyor chute opposite pusher to carry pushed parts off the conveyor
* Remover at the base of the chute remove parts



\### Configuration

* Vision sensor: All Digital output
* Emitter: Output all types of raw material parts



\### IO Mapping (Modbus TCP Client, as in FacoryIO)

Coils

* 4-bit vision sensor output -> coils 0-3
* Pusher back limit switch -> coil 4
* Pusher front limit switch -> coil 5



Inputs

* Emitter -> Input0
* Pusher -> Input1
* Belt Conveyor -> input2



TCP Config

localhost

port 502

slaveID: 0

Read digital: inputs

Read register: input registers

Scale: 100

6 Digital inputs

3 digital outputs

0 offset



---



\## \[v1.1] – 01/08/25

\### Added

* Diffuser Sensor 0 at pusher entry to trigger the pusher instead of vision sensor

 	- Reason: More reliable than using a timer alongside the vision sensor



\### Changed

* Raised the height of the vision sensor by adding a larger frame to attach it to

 	- Reason: Increases the field of view of the sensor. Original layout was occasionally missing readings

* Moved the pusher and chute further away from the vision sensor

 	- Reason: Declutters the entry area



\#### IO Mapping

* Diffuser Sensor 0 output to coil 6 in Modbus



---



\## \[v1.2] – 02/08/25

\### Added

* Electric switch board
* Start, Stop, Reset, and Emergency Stop 0 buttons
* Process On light indicator



\### Changed

* Removed Emitter from IO
* &nbsp;	- Reason: Couldn't get PLC logic to control Emitter state



\#### IO Mapping

* Emergency Stop: Coil 7
* Reset Button: Coil 8
* Start Button: Coil 9
* Stop Button: Coil 10
* Reset Button (light): Input 0
* Start Button (light): Input 3
* Stop Button (light): Input 4
* Process On light: Input 5



---



