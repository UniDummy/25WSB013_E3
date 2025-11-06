This project will utilize an Arduino to program various components for participation in the Olympic event.

Our chosen event is Wireless Charging, which involves maneuvering a robot using a custom-built remote control within a 3-meter range. The robot must navigate around obstacles, climb a see-saw and wirelessly charge a provided capacitor. However not all the charging pads at the charging station will be functional, therefore we need to develop a method to detect which charging pads are operational and also monitoring the charging status of the capacitor.

To achieve this, we have broken down into 3 main sections:

Robot Movement:

We have programmed the robot to perform basic movement functions, including moving forward, moving backward, turning left and turning right. These movements are controlled through a hand-made remote control that communicates wirelessly with the Arduino on the robot. A stop function has also been implemented for safety consideration, which it immediately halt the robot's motion when the stop fuction is active, ensuring safety or incase of any emergencies.

Remote Control:

For our remote control, we have decided to use 5 buttons to control the robot. Each button corresponds to a specific movement command, enabling the robot to navigate through obstacles and climb the see-saw. To establish communication between the remote control and the robot, we are using Bluetooth modules for connecting the Arduino on the robot, as the risk of having interference at the Olympic will be low. The remote control program will be using a polling technique to continuously checking the status of each button. This will allow the robot to move when a button is pressed and to stop immediately when the button is released, provding a smoother control. 

Wireless Charging:
