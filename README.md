# Obstacle Avoiding Robot Using Arduino

## Project Image

(Project image will be added soon.)

## Project Overview

This project demonstrates how a robot can detect obstacles and automatically change its direction to avoid collisions.

The robot uses an ultrasonic sensor to measure distance. When an obstacle is detected, the Arduino commands the motors to stop and turn before continuing its movement.

## Learning Objectives

- Understand how ultrasonic sensors work.
- Learn distance measurement using Arduino.
- Explore autonomous robot navigation.
- Build an obstacle detection system.

## Components Required

| Component | Quantity |
|------------|----------|
| Arduino UNO | 1 |
| HC-SR04 Ultrasonic Sensor | 1 |
| L293D Motor Driver | 1 |
| DC Motors | 2 |
| Wheels | 2 |
| Robot Chassis | 1 |
| Battery Pack | 1 |
| Jumper Wires | As Required |

## Working Principle

1. The ultrasonic sensor continuously measures the distance ahead.
2. Arduino processes the distance value.
3. If an obstacle is detected within a predefined range, the robot stops.
4. The robot turns to find a clear path.
5. The robot resumes moving forward.

## Circuit Connections

- Ultrasonic Trigger Pin → Digital Pin 9
- Ultrasonic Echo Pin → Digital Pin 10
- Motor Driver IN1 → Pin 5
- Motor Driver IN2 → Pin 6
- Motor Driver IN3 → Pin 7
- Motor Driver IN4 → Pin 8

## Arduino Code

```cpp
const int trigPin = 9;
const int echoPin = 10;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
}

void loop() {

  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);

  digitalWrite(trigPin, LOW);

  long duration = pulseIn(echoPin, HIGH);
  int distance = duration * 0.034 / 2;

  if(distance < 15) {
    // Turn Robot
  }
  else {
    // Move Forward
  }
}
```

## Applications

- Autonomous robots
- Warehouse automation
- Delivery robots
- Smart navigation systems

## Future Improvements

- Servo-based scanning
- AI obstacle recognition
- Bluetooth monitoring
- Camera integration

## Author

AnanyaLabs
