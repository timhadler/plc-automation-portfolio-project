\# FactoryIO Scene Change Log – PLC Automation Project



\## \[1] – 31/07/25

\### Initial setup - Stage one

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

salveID: 0

Read digital: inputs

Read register: input registers

Scale: 100

6 Digital inputs

3 digital outputs

0 offset





\### Author

\- T. Hadler



\### Notes

\-

