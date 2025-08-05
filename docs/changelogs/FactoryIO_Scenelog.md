# FactoryIO Scene Change Log – PLC Automation Project

---

## \[v1.0] – 31/07/25

### Added

* Initial setup - Stage one (Part detection)
* Belt conveyor (4m)
* Emitter 0 at one end
* A frame made from 3 walkway pillars right in front of emitter
* Vision sensor attached to frame, pointing down on conveyor
* Pneumatic pusher attached to side of conveyor, in front of sensor, pushes across the conveyor
* Conveyor chute opposite pusher to carry pushed parts off the conveyor
* Remover at the base of the chute removes parts

### Configuration

* Vision sensor: All Digital output
* Emitter 0: Output all types of raw material parts

### IO Mapping

Coils

* 4-bit vision sensor output -> coils 0-3
* Pusher back limit switch -> coil 4
* Pusher front limit switch -> coil 5

Inputs

* Emitter 0 -> Input0
* Pusher -> Input1
* Belt Conveyor -> input2

---

## \[v1.1] – 01/08/25

### Added

* Diffuser Sensor 0 at pusher entry to trigger the pusher instead of vision sensor

 	- Reason: More reliable than using a timer alongside the vision sensor


### Changed

* Raised the height of the vision sensor by adding a larger frame to attach it to

 	- Reason: Increases the field of view of the sensor. Original layout was occasionally missing readings

* Moved the pusher and chute further away from the vision sensor

 	- Reason: Declutters the entry area

#### IO Mapping

* Diffuser Sensor 0 output -> coil 6

---

## \[v1.2] – 02/08/25

### Added

* Electric switch board
* Start, Stop, Reset, and Emergency Stop buttons
* Process On light indicator

### Changed

* Removed Emitter from IO

 	- Reason: Couldn't get CODESYS to control Emitter state

#### IO Mapping

Coils

* Emergency Stop -> Coil 7
* Reset Button -> Coil 8
* Start Button -> Coil 9
* Stop Button -> Coil 10

Inputs

* Reset Button (light) -> Input 0
* Start Button (light) -> Input 3
* Stop Button (light) -> Input 4
* Process On light -> Input 5

---

## \[v2.0] – 03/08/25

### Added

* Stage 2 - Machining Center
* CNC Machining centre
* Diffuser sensor at the entrance of machining centre

#### IO Mapping

Coils

* Machining center (is busy) -> coil 11
* Machining center (has error) -> coil 12
* Diffuse sensor 1 -> coil 13
* Machining center (Opened) -> coil 14
* Machining center (Progress) -> Holding register 0

Inputs

* Machining center (Start) -> Input 6
* Machining center (Stop) -> Input 7
* Machining center (Reset) -> Input 8
* Machining center (Produce lids) -> Input 9

---

## \[v3.0] – 04/08/25

### Added

* Stage 3 - Assembley Station
* Two-Axis Pick and Place (Digital Configuration)
* Belt Conveyor 1 - Picks up Bases from Stage 2
* Belt Conveyor 2 - Carries Lids from Emitter 1
* Emitter 1 (COnfigured to emit only Blue Lids)
* Left Positioner 0 - On base conveyor
* Left Positioner 1 - On lids conveyor
* Diffuser sensor 2 - Lid at Positioner 1 detection
* Diffuser Sensor 3 - Base at Positioner 0 detection
* Diffuser sensor 4 for assembled product exit detection

### Changed
* Removed diffuser sensor 1
	- Reason: Replaced with flag in software
* Emiiter 0 only emits Metal and Blue raw material (removed green material)
	- Reason: End Container product will be completley blue

#### IO Mapping

Coils

* Diffuser Sensor 2 (Lid conveyor) -> Coil 13
* Diffuser Sensor 3 (Base conveyor) -> Coil 15
* Diffuser Sensor 4 (Product exit) -> Coil 16
* Left Positioner 0 (Limit) -> Coil 17
* Left Positioner 1 (Limit) -> Coil 18
* Two-Axis Pick & Place (Detected) -> Coil 19
* Two-Axis Pick & Place (Moving X) -> Coil 20
* Two-Axis Pick & Place (Moving Z) -> Coil 21
* Left Positioner 0 (Clamped) -> Coil 22
* Left Positioner 1 (Clamped) -> Coil 23

Inputs

* Belt Conveyor 1 -> Input 10
* Belt Conveyor 2 -> Input 11
* Left Positioner 0 (Clamp) -> Input 12
* Left Positioner 0 (Raise) -> Input 13
* Left Positioner 1 (Clamp) -> Input 14
* Left Positioner 1 (Raise) -> Input 15
* Two-Axis Pick & Place X -> Input 16
* Two-Axis Pick & Place Z -> Input 17
* Two-Axis Pick & Place (Grab) -> Input 18

---
