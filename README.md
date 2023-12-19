# Actuator Control GPIO 🎛️

This project demonstrates actuator control using GPIO pins on a microcontroller, controlling valves, lights, and pumps. Additionally, it utilizes a SONAR sensor to perform actions based on proximity detection.

## Project Overview 📝

### Actuator Control
The code initializes and manages the state of three actuators:

- **Valve (ID: 0x0)** - Connected to GPIO pin 0x5
- **Light (ID: 0x1)** - Connected to GPIO pin 0x4
- **Pump (ID: 0x2)** - Connected to GPIO pin 0x3

The `actuate` function allows you to control the state of these actuators by specifying the actuator index and the desired state (HIGH/LOW).

### SONAR Sensor
The project also involves a SONAR sensor for proximity sensing:

- **SONAR Sensor GPIO Configuration**
  - **Echo Pin (ECHO_GPIO):** 0xa
  - **Ping Pin (PING_GPIO):** 0x9
  - **Proximity Threshold (SENSE_PROXIMITY):** 50

The `driveSonar` function triggers the SONAR sensor to measure distance, while `getProximity` converts the sensor's response to proximity in centimeters.

## How It Works ℹ️

1. **Initialization:** The code initializes GPIO pins and sets actuators to their default states.
2. **Sensor Reading:** The program continuously senses proximity using the SONAR sensor.
3. **Sanitization Procedure:** If proximity is greater than a threshold, it executes a predefined sanitization procedure by manipulating the actuators.
