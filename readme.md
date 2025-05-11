# Automatic Gate Demo Kit

An Arduino-based automatic gate system that uses ultrasonic sensors to detect objects and automatically control a gate's movement. The system includes visual and audio feedback through LEDs and a buzzer.

## Features

- Automatic gate opening when objects are detected
- Automatic gate closing after a 5-second delay when no objects are present
- Visual status indicators using red and blue LEDs
- Audio feedback using a buzzer
- Ultrasonic distance sensing for reliable object detection

## Hardware Requirements

- Arduino board (Uno, Nano, or similar)
- Servo motor
- HC-SR04 Ultrasonic sensor
- 2 LEDs (1 Red, 1 Blue)
- Buzzer
- Jumper wires
- Breadboard (optional)
- Power supply

## Pin Connections

| Component | Pin |
|-----------|-----|
| Ultrasonic Trigger | D2 |
| Ultrasonic Echo | D3 |
| Red LED Anode | D4 |
| Red LED Cathode | D8 |
| Blue LED Cathode | D7 |
| Blue LED | D5 |
| Servo Motor | D6 |
| Buzzer | D12 |

## Software Requirements

- Arduino IDE
- Servo.h library

## Installation

1. Clone or download this repository
2. Open the `sketch.ino` file in Arduino IDE
3. Install the Servo library if not already installed:
   - Go to Tools > Manage Libraries
   - Search for "Servo"
   - Install the "Servo" library by Arduino
4. Connect your Arduino board to your computer
5. Select the correct board and port in Arduino IDE
6. Upload the code to your Arduino

## How It Works

1. The system continuously monitors the distance using the ultrasonic sensor
2. When an object is detected within 50cm (threshold distance):
   - The gate opens (servo rotates to 90 degrees)
   - Red LED turns off
   - Blue LED turns on
   - Buzzer starts gentle beeping
3. When no object is detected for 5 seconds:
   - The gate closes (servo returns to 0 degrees)
   - Red LED turns on
   - Blue LED turns off
   - Buzzer stops

## Customization

You can modify the following parameters in the code:
- `thresholdDistance`: Detection distance (default: 50.0 cm)
- `closedAngle`: Gate closed position (default: 0 degrees)
- `openAngle`: Gate open position (default: 90 degrees)
- `closeDelay`: Time before automatic closing (default: 5000 ms)
- `beepOnTime`: Duration of each beep (default: 50 ms)
- `beepCycle`: Time between beeps (default: 500 ms)

## Troubleshooting

1. If the servo doesn't move:
   - Check the servo connections
   - Verify the servo library is installed
   - Ensure the servo is receiving power

2. If the ultrasonic sensor doesn't detect objects:
   - Check the trigger and echo pin connections
   - Ensure the sensor is properly powered
   - Clean the sensor surface

3. If LEDs don't light up:
   - Verify the correct pin connections
   - Check if the LEDs are properly oriented (anode/cathode)

## License

This project is open source and available under the MIT License.

## Contributing

Feel free to submit issues and enhancement requests! 
