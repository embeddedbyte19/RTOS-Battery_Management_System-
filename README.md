# RTOS-Battery_Management_System-
BATTERY PACK->STM32->FREERTOS->UART

# RTOS Battery Management System

## 🔋 Smart Battery System – STM32 (RTOS)

**Overview**

This repository presents a high-level view of a Smart Battery monitoring system developed on an STM32 microcontroller using an RTOS-based architecture. The system interfaces with a smart fuel gauge IC to observe battery behavior and provide structured diagnostic output.
This public version focuses on project concept and functionality. Detailed implementation, internal logic, and proprietary methods are intentionally kept private.

**Key Functions**

Periodic battery data monitoring
UART-based status reporting
Basic configuration via command interface
Safety and protection supervision
Lifetime data tracking

**System Flow**

Battery Pack → Fuel Gauge IC → STM32 MCU → Freertos -> UART Output
The system continuously reads essential battery parameters and transmits formatted data for monitoring and analysis.

**Project Description**

This project demonstrates a Smart Battery Monitoring System built on an STM32 microcontroller using an RTOS-based design. The system reads real-time data from a smart battery fuel gauge, converts the raw values into structured string format, and transmits them to a monitoring interface through a serial communication port.
The architecture is based on task separation, where battery data acquisition and data transmission are handled independently to ensure smooth operation and reliable performance.

**Working Concept**

When the battery provides parameter values, they are processed and formatted into readable string frames. These frames are then handled by two RTOS threads:

🔹 Thread 1 – Data Acquisition Task
Continuously reads values from the battery fuel gauge IC
Processes raw data into meaningful parameters
Converts values into structured string format
Updates shared data buffers

🔹 Thread 2 – Communication Task
Takes the formatted string data
Transfers it to the communication port (UART / COM Port)
Ensures consistent and timed data output
This separation improves system stability and ensures that communication does not interrupt real-time data sampling.

**System Flow**

Battery Pack → Fuel Gauge IC → STM32 MCU ↓ RTOS Thread 1 (Read & Format) ↓ RTOS Thread 2 (Transmit) ↓ COM Port Output
