\# FactoryIO Scene Change Log – PLC Automation Project



\## \[v1.0] – 31/07/25

\### Added

* Initial setup - Stage one (Part detection)
* Belt conveyor (4m)
* Emitter at one end, configured to emit all types of raw materials
* A frame made from 3 walkway pillars right in front of emitter
* Vision sensor attached to frame, pointing down on conveyor, config to all digital output
* Pneumatic pusher attached to side of conveyor, in front of sensor, pushes across the conveyor
* Conveyor chute opposite pusher to carry pushed parts off the conveyor
* Remover at the base of the chute remove parts



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







\## \[v1.1] – 1/08/25

\### Added

* Diffuser sensor at pusher entry to trigger the pusher instead of vision sensor

 	- Reason: More reliable than using a timer alongside the vision sensor



\### Changed

* Raised the height of the vision sensor by adding a larger frame to attach it to

 	- Reason: Increases the field of view of the sensor. Original layout was occasionally missing readings

* Moved the pusher and chute further away from the vision sensor

 	- Reason: Declutters the entry area



\#### IO Mapping

&nbsp;	- Mapped diffuser sensor output to coil 6 in Modbus



