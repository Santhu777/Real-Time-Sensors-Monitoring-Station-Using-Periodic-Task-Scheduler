# Real-Time Sensors Monitoring Station Using Periodic Task Scheduler

## Project Overview

The **Real-Time Sensors Monitoring Station Using Periodic Task Scheduler** is an embedded systems project developed using the LPC2129 ARM7 microcontroller.

The main objective of this project is to monitor multiple sensors at different time intervals using a periodic task scheduling technique.

A hardware timer interrupt is used to generate periodic timing events. The Interrupt Service Routine (ISR) sets task flags, while the main program executes the corresponding sensor-reading and data-transmission operations.

This approach reduces the workload inside the ISR and ensures efficient execution of multiple periodic tasks.

## Hardware Requirements

- LPC2129 ARM7 Microcontroller
- Temperature Sensor
- Potentiometer
- LDR (Light Dependent Resistor)
- UART-to-USB Converter
- Power Supply

## Software Requirements

- Embedded C
- Keil µVision IDE
- Flash Magic
- UART Communication
- ADC (Analog-to-Digital Converter)
- Timer Interrupt Programming

## System Architecture

The system uses a single hardware timer interrupt to schedule multiple periodic tasks.
 Task 1  300 ms  Read Sensor 1 
 Task 2  500 ms  Read Sensor 2 
 Task 3  1000 ms  Transmit sensor data through UART 

**Execution flow:**

1. Initialize GPIO, ADC, UART, and Timer.
2. Configure the timer interrupt.
3. Timer interrupt generates periodic events.
4. ISR sets the corresponding task flags.
5. Main loop checks the task flags.
6. Sensor readings are acquired using ADC.
7. Sensor values are transmitted through UART.

## Periodic Task Scheduling

The project uses a flag-based scheduling mechanism.

- Timer interrupt is responsible only for updating timing events and setting flags.
- Main loop executes the actual sensor-reading functions.
- Each task runs according to its configured time interval.
- UART transmits the collected sensor information periodically.

This architecture separates time management from task execution.

## Key Features

- Multiple sensor monitoring.
- Periodic task scheduling.
- Timer interrupt-based timing.
- ADC-based sensor data acquisition.
- UART-based serial communication.
- Flag-based task execution.
- Efficient ISR implementation.

## Concepts Implemented

- ARM7 LPC2129 Architecture
- Embedded C Programming
- Interrupt Service Routine (ISR)
- Timer0 Configuration
- Analog-to-Digital Conversion (ADC)
- UART Communication
- Periodic Task Scheduling
- Embedded System Design

## Applications

- Environmental monitoring systems
- Industrial sensor monitoring
- Real-time data acquisition
- Embedded monitoring stations
- IoT-based monitoring systems

## Future Improvements

- Implement task priority management.
- Add CAN communication for sensor data transmission.
- Interface an LCD for real-time display.
- Implement an RTOS-based version.
- Add additional sensors for environmental monitoring.

## Learning Outcomes

Through this project, I gained practical experience in:

- Configuring and programming LPC2129 peripherals.
- Handling timer interrupts.
- Implementing periodic task scheduling without an RTOS.
- Acquiring sensor data through ADC.
- Transmitting sensor readings through UART.
- Designing efficient embedded applications using Embedded C.
