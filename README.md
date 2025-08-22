#Traffic Light Controller in Verilog
This repository contains the Verilog code for a simple traffic light controller for an intersection between a highway and a farm road.

Project Overview
The project models a traffic light system where the highway traffic has priority. The traffic light on the highway remains green by default, while the farm road light stays red. The system only changes state when a car is detected on the farm road. The controller is designed as a finite state machine (FSM).

Features
Default State: Highway light is Green, Farm road light is Red.

Sensor-based Trigger: The light cycle is initiated when the input sensor C detects a car on the farm road (C=1).

State Sequence:

Highway Green / Farm Red: The initial and default state.

Highway Yellow / Farm Red: When a car is detected on the farm road, the highway light turns yellow for a short duration (3 seconds in simulation time).

Highway Red / Farm Green: After the yellow light phase, the highway light turns red, and the farm road light turns green for a fixed duration (10 seconds in simulation time).

Highway Red / Farm Yellow: The farm road light turns yellow for a short duration (3 seconds in simulation time).

The system then returns to the default state (Highway Green / Farm Red).

Active-low Reset: The system can be reset to its initial state.

File Descriptions
traffic_light.v: This file contains the main Verilog module for the traffic light controller FSM.

tb_traffic.v: This is the testbench file used to simulate and verify the functionality of the traffic_light module.

How to Use
To run this project, you will need a Verilog simulator (e.g., ModelSim, Vivado, Icarus Verilog).

Compile both traffic_light.v and tb_traffic.v files.

Run the simulation with tb_traffic as the top module.

Observe the waveform and the console output to verify the behavior. The testbench is set up to trigger the sensor and test the state transitions.

Simulation Waveform
The following waveform shows the behavior of the signals during simulation when the sensor C is triggered.

Simulation Objects
This screenshot shows the state of various signals and registers at a specific point during the simulation.
