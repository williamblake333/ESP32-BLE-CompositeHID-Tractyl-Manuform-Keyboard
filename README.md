# BLE Gamepad for BPI Leaf S3

This project implements a Bluetooth Low Energy (BLE) gamepad using the BPI Leaf S3 development board based on the ESP32-S3 microcontroller. The gamepad features:

- A 5x5 matrix keyboard with 21 buttons
- An analog joystick
- An ADNS5050 optical mouse sensor

The implementation uses the ESP32-BLE-CompositeHID library to create a composite device that functions as both a gamepad and mouse.

## Hardware Requirements

- BPI Leaf S3 (ESP32-S3) development board
- 5x5 matrix keyboard (utilizing 21 buttons)
- Analog joystick with X and Y axes
- ADNS5050 optical mouse sensor
- Wires and connecting hardware

## Wiring Configuration

### Matrix Keyboard
The keyboard is arranged in a 5x5 matrix with 21 buttons:
- Rows: 5 pins (default: GPIO 10, 11, 12, 13, 14)
- Columns: 5 pins (default: GPIO 15, 16, 17, 18, 19)

### Analog Joystick
- X-axis: Connected to GPIO 1
- Y-axis: Connected to GPIO 2

### ADNS5050 Mouse Sensor
- SCLK: Connected to GPIO 7
- SDIO: Connected to GPIO 6
- NCS: Connected to GPIO 5
- NRESET: Connected to GPIO 4

## Software Dependencies

This project requires the following libraries:
- ESP32-BLE-CompositeHID (forked from ESP32-BLE-Gamepad)
- Keypad
- Arduino core for ESP32

## Code Structure

The project is structured with the following classes:

1. `ADNS5050`: Handles communication with the optical mouse sensor
2. `MatrixKeyboard`: Manages the keyboard matrix and button mapping
3. `AnalogJoystick`: Reads and calibrates the analog joystick

The main file initializes all components and manages the Bluetooth connection.

## Installation and Setup

1. Install the required libraries using the Arduino Library Manager
2. Connect the hardware as described in the wiring configuration
3. Upload the code to your BPI Leaf S3 board
4. Pair the device with your computer or gaming console

## Customization

You can customize the project by:
- Adjusting pin assignments in the pin definitions
- Modifying the button mapping in the matrix keyboard configuration
- Tuning the joystick deadzone value
- Changing the mouse sensitivity

## Troubleshooting

If you encounter issues with the device not being recognized:
1. Check that the BLE connection is established
2. Ensure all components are properly wired
3. Verify the product ID of the ADNS5050 sensor
4. Check the serial monitor for debug information

## Future Improvements

Potential enhancements for this project:
- Add configuration options via a web interface
- Implement button mapping profiles
- Add battery level monitoring
- Optimize power consumption for longer battery life
