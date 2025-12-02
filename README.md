This is the sub branch for the project.

This branch contains the individual test scripts used to demonstrates the specific tasks of each component will partake and verify the performance of it. This included the buttons, robot motors and LED.

Buttons:
This code used to test the input detection. The button should generate a constant input while it is held down, and no input when it is released.

Robot Motors:
This code used to test movement control is all four directions: forward, backward, left turn and right turn. These tests are performed using keyboard inputs to ensure the robot only moves when explicit commands are given.

LED:
This code used to test the task carried out by the LED based on different voltage levels. The LED should remain off when the capacitor isnt charging, it flashes continuously while the capacitor is charging and stay litted once the capacitor exceeds a defined charge threshold.

Bluetooth: (Connect EP32-WROOM with HC-05)
This code used to test the Bluetooth paring and communication between the EP32-WROOM and HC-05 module. In this setup the EP32-WROOM should successfully transmit data through the HC-05 to the Arduino on the robot. This test are performed by sending text messages via the Serial Monitor from one device to another.
