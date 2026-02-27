This project will utilize an Arduino to program various components for participation in the Olympic event.

Our chosen event is Wireless Charging, which involves maneuvering a robot using a custom-built remote control within a 3-meter range. The robot must navigate around obstacles, climb a see-saw and wirelessly charge a provided capacitor up to 5V. However not all the charging pads at the charging station will be functional, therefore we need to develop a method to detect which charging pads are operational and also monitoring the charging status of the capacitor.

To achieve this, we have broken down into 3 main sections:

1. Robot Movement:

We have programmed the robot to perform basic movement functions, including moving forward, moving backward, turning left and turning right. These movements are controlled through a hand-made remote control that communicates wirelessly with the Arduino on the robot. A stop function has also been implemented for safety consideration, which it immediately halt the robot's motion when the stop fuction is active, ensuring safety or incase of any emergencies.


2. Remote Control:

For our remote control, we have decided to use 5 buttons to control the robot. Each button corresponds to a specific movement command, enabling the robot to navigate through obstacles and climb the see-saw. To establish communication between the remote control and the robot, we are using Bluetooth modules for connecting the Arduino on the robot, as the risk of having interference at the Olympic will be low. The remote control program will be using a polling technique to continuously checking the status of each button. This will allow the robot to move when a button is pressed and to stop immediately when the button is released, provding a smoother control. 


3. Wireless Charging:
- Coil Placement and Mechanical Design:
We planned to mount the receiver coil underneath the robot using a custom 3D-printed holder. It is positioned below the battery pack rather than near the servo motors to minimize potential magnetic interference which could affect the performance.
The design targets a 2mm ground clearance between the robot and ground. Considering the physical structure of the charging station and custom 3D-printed holder, there are 1mm of plastic covering above the transmitter coil and 1mm inner disc supporting the receiver coil respectively. As a result, the total separation distance between the transmitter and receiver coil is approximately 4mm. This distance was selected for balancing the mechanical protection with efficient wireless power transfer.

- Capacitor Voltage Monitoring:
We decided to use the Arduino onboard the robot for monitoring the capacitor voltage during wireless charging. To optimize the charging efficiency and provide clear visual feedback, two separate groups of LEDs act as an indication system are implemented:

  1. Capacitor Voltage Indication System
 
  This group consists of 3 LEDs:
  - Red LED -> illuminates when the capacitor reaches 1V
  - Yellow LED -> illuminates when reaches 3V
  - Green LED -> illuminates when reaches 4.8V
  
  These thresholds provide progressive feedback on the charging status.

  2. Coil Alignment Indication System
  
  This group consists of 3 LEDs of the same colour are used to indicate the quality of alignment between the transmitter and receiver coil. The number of LEDs illuminated corresponds to how well the coils are aligned, provide feedback for adjusting to maximize the charging efficiency.

- Charging Strategy
Since the system uses wireless charging to charge a capacitor, the charging behavior follows an exponential curve. The capacitor charges rapidly at lower voltages and slow down significantly as it approaches its maximum voltage. Although the target is to charge up to 5V, but reaching to this value would require a long charging time.
Given the competition rules impose a time penalty if fail to reach 5V. Therefore after performing a trade-off analysis back with calculation, we decided to charge the capacitor up to 4.8V, although result in receiving a 1.2 second penalty, but this will allows us to begin moving earlier.
However, the capacitor naturally experience voltage leakage after charging, decreasing from 4.8V at an average rate of approximately 0.0004V / s. Because of the experimental results, it shows that the time require for the voltage drop from 4.8V to 4.7V is over 6 mins. Therefore, charging up to 4.8V will ensure the capacitor maintains a voltage value above 4.7V by the end of the competition.
Although stopping at 4.8V results in a penalty of approximately 1.2 seconds, even in worst-case scenario it will result in no more than 2.7 seconds, the time saved by avoiding the slow final charging stage outweights the penalty. Consequently, the strategy of charging up to 4.8V minimizes total runtime and optimized the balance between charging duration and penalty cost. 
