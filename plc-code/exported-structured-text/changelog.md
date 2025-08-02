# CODESYS Change Log – PLC Automation Project

## \[v1.0.0] – 31/07/25

Compatable with FactoryIO scene: ContainerManufacturing.facoryio v1.0 (see changelog)

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

Compatable with FactoryIO scene: ContainerManufacturing.facoryio v1.1 (see changelog)

### Changed

* Control logic now relies on a diffuser sensor to initiate the Pusher to reject materials
  -- Reason: More reliable than using a timer
