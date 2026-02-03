# -Virtual-Automotive-ECU-Cluster-CAN-UDS-
This project presents an advanced Software-in-the-Loop (SiL) simulation environment for a multi-node Automotive Electronic Control Unit (ECU). Built on Zephyr RTOS, the system integrates powertrain state-machine logic with an IoT telemetry pipeline, enabling real-time performance monitoring and remote diagnostics.
Core Technical Architecture
Deterministic Powertrain State Machine: Developed a multi-threaded execution model using the Zephyr kernel to simulate Engine and Transmission Control Units (ECU/TCU). The state machine handles non-linear gear transitions (Gears 1-6) based on dynamic load and braking events.

Real-Time OS (RTOS) Integration: Leveraged Zephyr's modular kernel for task scheduling, utilizing preemptive threading to manage high-priority powertrain calculations independently of lower-priority telemetry tasks.

In-Vehicle Networking & Diagnostics: Implemented a virtual Controller Area Network (CAN) bus using SocketCAN. Integrated a UDS (ISO-14229) compliant diagnostic server to monitor system health and report Diagnostic Trouble Codes (DTCs).

Cloud-Native IoT Pipeline: Engineered a low-latency bridge using MQTT (ISO/IEC 20922) for asynchronous data streaming to a HiveMQ broker, facilitating remote vehicle monitoring (V2X).
Feature                                                       	Implementation Detail
Operating System                                  	Zephyr RTOS (Monolithic Kernel, SMP Support)
Communication Stacks	                                CAN Bus (SocketCAN), UDS (ISO-14229), MQTT
Logic Implementation	                         Finite State Machine (FSM) for Dynamic Gear Ratios
Telemetry Interface	                                   Plotly Dash / Python 3.10 Web Dashboard
Development Workflow	                                  West Build System, Kconfig, DeviceTree

