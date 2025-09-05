# Industry 4.0 Manufacturing Automation Portfolio Project
Complete 3-stage manufacturing and assembly process automation using structured PLC programming with industrial communication protocols, emergency stop, and fault handling.

## Key Technologies
- CODESYS PLC Programming (structured text, function blocks, ladder logic)
- Emergency stop and fault handling logic
- Multi-stage process automation with state machine logic
- Factory IO Simulation
- Modbus TCP communication (Client: FactoryIO, Server: CODESYS)

## Manufacturing Steps
Stage 1: Material Sorting & Quality Control

- Conveyor system supplies mixed raw materials (blue plastic and metal components)
- Vision sensor identifies material type with pneumatic pusher rejecting metal parts via off-chute
- Only approved plastic materials advance to manufacturing

Stage 2: Base Manufacturing

- Processes accepted raw materials into product bases using automated manufacturing equipment
- Implements intelligent stage control - signals Stage 1 (idle→running) when ready to receive parts
- Automatically transitions to "busy" state during active manufacturing cycle
- Transfers finished bases via conveyor to final assembly

Stage 3: Assembly & Packaging

- Dual-conveyor input system: manufactured bases + product lids (spawned for demonstration)
- 2-axis pick-and-place robot with pneumatic positioning systems
- Automated assembly of lids onto bases creating finished containers
- IR sensors provide precise part detection and positioning feedback throughout process

Sensor Integration: IR sensors strategically positioned to monitor part presence at critical stations (pusher zone, assembly positions, transfer points) enabling real-time process control.

## Video Demonstration
Full process [ 1:45 ]
Demonstrates the full 3-stage process. 

https://drive.google.com/file/d/1jgmJhKKk6puQMtF79jDqM2R668uc4EmO/view?usp=sharing

Fault and E-Stop Handling [ 1:42 ]
Injected a fault (part gets stuck at entry to the manufacturing center). After 20 seconds the controller recognises there is a fault, causing the entire process to halt and requires operator intervention to restart. 
Initiated an emergency stop [ 1:05 ] and restart. 

https://drive.google.com/file/d/1Wlif4s2rBeTBHrgsaJoMtnuUYSDvpSE7/view?usp=sharing

## Planned Development Stages
- [x] Phase 1: Core PLC automation and process control *(Current)*
- [ ] Phase 2: SCADA system integration and data logging *(In Progress)*
- [ ] Phase 3: IoT connectivity and cloud data analytics
- [ ] Phase 4: Machine learning for predictive maintenance
- [ ] Phase 5: Digital twin implementation
