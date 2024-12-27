# Bluetooth-Based Surveillance System

This project implements a surveillance system using an Arduino microcontroller, the HC-05 Bluetooth module, an IR sensor, and a buzzer. The system monitors for unauthorized access and sends alerts via Bluetooth while triggering an audible alarm.

## Features
- **Motion Detection**: Utilizes an IR sensor to detect movement or unauthorized access.
- **Bluetooth Communication**: Uses the HC-05 module to notify the user via a paired Bluetooth device.
- **Audible Alert**: Activates a buzzer upon motion detection.
- **Remote Control**: Enables or disables monitoring remotely via Bluetooth commands (`E` to enable, `D` to disable).

## Components Used
1. **Arduino Board**: Microcontroller to process signals and control components.
2. **HC-05 Bluetooth Module**: Wireless communication with a paired device.
3. **IR Sensor**: Detects motion or intrusion.
4. **Buzzer**: Sounds an alarm upon detection.
5. **Power Supply**: Provides power to the system.

## How It Works
1. The IR sensor detects motion by monitoring infrared signals.
2. When motion is detected, the system:
   - Activates the buzzer to alert nearby users.
   - Sends a notification via Bluetooth to the paired device.
3. Bluetooth commands (`E` or `D`) allow the user to enable or disable monitoring remotely.

## Code Overview
### Main Application
- **Monitoring Logic**: Continuously monitors the IR sensor and activates/deactivates the buzzer based on the detection status.
- **Bluetooth Commands**:
  - `E`: Enables monitoring.
  - `D`: Disables monitoring.

### UART Communication
- Handles serial communication with the Bluetooth module.
- Supports data transmission for single characters and strings.

### Bluetooth Configuration
- Configures the HC-05 module's name using the `set_bluetooth_name` function.

### Interrupt Handling
- Utilizes the USART RX Complete Interrupt to process incoming Bluetooth commands in real time.

## Getting Started
### Prerequisites
- **Software**: Arduino IDE for uploading the code.
- **Hardware**: The components listed above.

### Steps
1. Assemble the circuit as per the schematic.
2. Upload the provided code to the Arduino board using the Arduino IDE.
3. Pair the HC-05 module with your Bluetooth device.
4. Send commands (`E` or `D`) via a Bluetooth terminal app to control the system.

## Files in the Repository
- `main.c`: Core surveillance system logic.
- `UART.h` and `UART.c`: UART communication implementation.
- `bluetooth.h` and `bluetooth.c`: Bluetooth module configuration.
- `schematics/`: Circuit diagrams and wiring details.

## Example Commands
| Command | Description            |
|---------|------------------------|
| `E`     | Enable monitoring      |
| `D`     | Disable monitoring     |

