This is the sub branch for the project.

It contains the individual test scripts used to demonstrates the specific tasks of each component will partake and verify the performance of it. This included the buttons, robot motors, LED and Bluetooth module.

- Button:

This code used to test the input detection. The button should generate a constant input while it is held down, and no input when it is released.


- Robot Movement:

This code used to test movement control is all four directions: forward, backward, left turn and right turn. These tests are performed using keyboard inputs to ensure the robot only moves when explicit commands are given.


- LED:

This code used to test the task carried out by the LEDs based on different voltage value in the capacitor. The Red LED should only illuminate when the voltage reaches 1V; the Yellow LED should only illuminate when it reaches 3V; the Green LED should only illuminate when it reaches 4.8V.


- Bluetooth: (Connect EP32-WROOM with HC-05)

These code used to test the Bluetooth paring and communication between the EP32-WROOM and HC-05 module. In this setup the EP32-WROOM should successfully transmit data through the HC-05 to the Arduino on the robot. This test are performed by sending text messages via the Serial Monitor from one device to another.


- Movement Control with Bluetooth:

These code is used to test the wireless movement control of the robot. The test is performed using a laptop connected to the ESP32-WROOM, then the movement commands are sent through the Serial Monitor. These commands are transmitted via Bluetooth to the HC-05 module on the robot, whhch then causing the robot to be controlled by the laptop and move accordingly.
