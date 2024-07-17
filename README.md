
# Servo Motor Control by Potentiometer

## Overview
This project demonstrates how to control a servo motor using a potentiometer with an Arduino. It reads the analog input from the potentiometer and adjusts the servo motor's position accordingly.

## Demo
Watch a demo of the project [here](https://github.com/shathalshehri/ServoMotorControl-by-Potentiometer/blob/main/ServoControlDemo.MP4).

## Components Used
- Arduino Board
- Servo Motor
- Potentiometer
- Jumper Wires
- Breadboard

## Setup
1. **Connect Components:**
   - Connect the servo motor signal pin to Arduino pin 9.
   - Connect one end of the potentiometer to 5V and the other end to GND.
   - Connect the wiper (middle pin) of the potentiometer to Arduino analog pin A0.

2. **Upload Code:**
   - Upload the `ServoMotorControl.ino` sketch to your Arduino using the Arduino IDE.

3. **Run the Project:**
   - Power up your Arduino board.
   - Adjust the potentiometer and observe the servo motor's movement.

## Code
Find the Arduino code `ServoMotorControl.ino` in this repository. Here's a snippet to illustrate:

```cpp
// Include the Servo library
#include <Servo.h>

// Create a Servo object
Servo myServo;

// Define potentiometer pin
int potPin = A0;

void setup() {
  // Attach servo to pin 9
  myServo.attach(9);
}

void loop() {
  // Read potentiometer value
  int potValue = analogRead(potPin);

  // Map potentiometer value to servo angle (0-180 degrees)
  int servoAngle = map(potValue, 0, 1023, 0, 180);

  // Move the servo motor
  myServo.write(servoAngle);

  // Delay for stability
  delay(15); // Adjust delay as needed
}
