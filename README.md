# UVC Cabinet Enhancement for MAPUA Laboratory with Gizduino

## Table of Contents
- [Introduction](#introduction)
- [Design Procedure](#design-procedure)
  - [Hardware Implementation](#hardware-implementation)
  - [Software Implementation](#software-implementation)
  - [Prototype Development](#prototype-development)
- [Conclusion and Recommendations](#conclusion-and-recommendations)

## Introduction
The UVC Cabinet project aims to enhance the bag cabinets at MAPUA University by integrating a deep-UV disinfection system to sanitize objects against microorganisms, including the novel coronavirus. The cabinet utilizes UVC light (200-280nm) to disinfect common items used by students in the laboratory, such as school bags, documents, gadgets, pens, and calculators. The system uses UV sensors and reed switches to monitor the cabinet’s state, ensuring that the objects are disinfected thoroughly.

### Objectives:
1. Build a UVC disinfection cabinet emitting UV-C light (200-280nm).
2. Determine the optimal location and exposure time for disinfection.
3. Evaluate the effectiveness of the disinfection on five common objects.

## Design Procedure

### Hardware Implementation
The system consists of several key components, including a UV sensor, reed switch, UVC lamps, and a microcontroller (Gizduino). The system is fully autonomous, with user input to set exposure time and start/stop disinfection. The output is a disinfected object and a buzzer sound sequence indicating the system's current state.

| **Input**              | **Process**                                                                 | **Output**                      |
|------------------------|-----------------------------------------------------------------------------|---------------------------------|
| Object for disinfection | Set exposure time based on button press                                       | UVC disinfected object          |
| Push button state       | Initiate UVC exposure based on cabinet door state                            | Buzzer sound sequence           |
| Cabinet door state      | Terminate UVC exposure based on UV sensor reading and cabinet door state     | System ready for next cycle     |
| UVC light detection     | Ensure UVC exposure for a predetermined time                                  |                                 |

#### System Component Connections
The system components are connected via a printed circuit board (PCB) with a 5V relay, UV sensor, UVC lamps, and Gizduino. The UV sensor sends analog data to the microcontroller, which controls the UVC lamps and buzzer.

![System Component Connections](/System_Component_Connections.png)

### Software Implementation
The software controls the UVC disinfection process, including setting exposure time and monitoring the cabinet door state. The program allows the user to select the exposure time (30 or 60 minutes) and start/stop the UVC exposure with a button press. The system outputs different buzzer sounds to indicate the status and progress of disinfection.

#### System Flowchart (Code Logic)
The flowchart below illustrates the actual code logic, showing the process when the system is powered on, performs disinfection, and is then turned off.

![System Flowchart](/System_Flowchart.jpg)

### Prototype Development
The prototype was developed using a PCB designed for this project. The components were soldered onto the PCB and connected to the Gizduino microcontroller. The cabinet was built from metal sheets and angle bars, with a transparent acrylic casing to house the electronics and UVC lamps.

![Prototype](/Prototype.jpg)

## Conclusion and Recommendations
The UVC disinfection cabinet successfully disinfected the five common laboratory objects, with the optimal location for disinfection found to be at the center of the cabinet, approximately 18 cm from the UVC lamp. A 60-minute exposure time was recommended to ensure complete disinfection, although 30 minutes was also effective when the objects were placed at the center. Further improvements could involve adding a temperature sensor to monitor heat buildup during disinfection and testing with actual UV meters or bacteria cultures to measure disinfection effectiveness more accurately.
