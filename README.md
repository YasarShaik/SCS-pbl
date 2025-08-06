# Smart Helmet for Mining Safety 

This project aims to enhance underground mining safety through a smart helmet that integrates sensors, signal modeling, and embedded communication systems. It monitors:

- Toxic gas concentration  
- Sudden impacts or falls  
- Motion and movement of miners

To ensure real-time safety alerts and reliable data transmission from deep underground to the surface, the project merges two core domains:

- **Signals and Communication Systems (SCS)** – for modeling, analyzing, and simulating the behavior of signals and communication channels using MATLAB
- **Processors and Controllers (P&C)** – for real-world implementation through embedded systems using ARM microcontrollers, sensors, and UART-based data transmission

The overall goal is to simulate the signal behavior under underground conditions and prepare for hardware implementation in the future. This system bridges the gap between communication theory and real-world mining safety technology.

## Embedded System Implementation
This repository focuses on the embedded implementation using the **ARM Cortex-M microcontroller** (e.g., STM32/ATmega). The smart helmet system includes:

### Microcontroller Configuration
- Configured UART for serial communication
- Timers and interrupts for real-time monitoring
- GPIO interfaces for sensors and actuators

### Sensor Integration
- **MQ-135** for toxic gas detection (analog input)
- **Accelerometer (e.g., MPU6050)** for fall detection and motion tracking (I2C/SPI)
- **PIR/Ultrasonic** sensors for movement detection

### Signal Flow
1. Sensors collect physical data (gas, motion, impact)
2. Microcontroller digitizes data using ADC/Digital Input
3. Logic triggers alerts when thresholds are crossed
4. Encoded binary data is transmitted via UART
5. Data is sent to a communication module (e.g., LoRa, Zigbee) for wireless transmission

## Warning & Response System
- Buzzer or LED for local real-time alerts
- Optionally connected display (e.g., OLED/LCD) to show status
- Data sent to a central base station for supervisor monitoring

## Power Supply System
- Designed for portability and underground resilience
- Battery-operated (Li-Ion/3.7V with Boost Converter)
- Voltage regulation using LM7805 or AMS1117
- Capacitor filtering to eliminate ripples

## Future Add-ons
- Integration with cloud servers via Wi-Fi/Bluetooth gateways
- GPS tracking for surface positioning
- Energy-efficient sleep modes

## Outcome
This implementation provides the foundation for a reliable, real-time, embedded safety system in mines. Combined with the SCS simulations, it offers a practical solution ready for deployment and scalability.
