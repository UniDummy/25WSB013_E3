This project will utilise an Arduino to program various components for participation in the Olympiad event.

Our chosen event is Wireless Charging, which involves maneuvering a robot using a custom-built remote control with a minimum 3-meter range. The robot must navigate around obstacles, climb a see-saw and wirelessly charge a provided supercapacitor up to 5V. However, not all the charging pads at the charging station will be functional, therefore we need to develop a method to detect which charging pads are operational and also monitoring the charging status of the capacitor.

To achieve this, we have broken down into 3 main sections:

1. Robot Movement:

We have programmed the robot to perform basic movement functions, including moving forward; moving backward; turning left and turning right. These movements are controlled through a custom remote control that communicates wirelessly with the Arduino on the robot. Movement capabilities of the robot have been scaled to accommodate user-friendly control for the Olympiad's obstacle scenario.


2. Remote Control:

For our remote control, we have decided to use 4 buttons to control the robot. Each button corresponds to a specific movement command, enabling the robot to navigate through obstacles and climb the see-saw. To establish communication between the remote control and the robot, we are using Classic Bluetooth modules for connecting the Arduino on the robot, as the risk of having interference at the Olympiad will be low. The remote control program will be using a polling technique to continuously check the status of each button. This will allow the robot to move when a button is pressed and to stop immediately when the button is released, provding smooth control.


3. Wireless Charging:

- Coil Placement and Mechanical Design:
  
The receiver coil is mounted underneath the robot using a custom 3D-printed holder. It is positioned below the battery pack rather than near the servo motors to minimize potential magnetic interference which could affect the performance.
The design targets a 1mm ground clearance between the robot and ground. Considering the physical structure of the charging station and custom 3D-printed holder, there are 1mm of plastic covering above the transmitter coil and 1mm inner disc supporting the receiver coil respectively. As a result, the total separation distance between the transmitter and receiver coil is approximately 3mm. This distance was selected for balancing the mechanical protection with efficient wireless power transfer.


- Capacitor Voltage Monitoring:
  
We decided to use the Arduino onboard the robot for monitoring the capacitor voltage during wireless charging. To optimise the charging efficiency and provide clear visual feedback, an LED-baased indication system are implemented:

1. Capacitor Voltage Indication System

  This system uses a single LED to indicate when the capacitor has reached the minimum charging requirement we have set. When the capacitor voltage reaches 4.9V, the LED turns on and remains illuminated for 5 seconds, this indicates the capacitor has reached the requirement and the robot is ready to get moving. After this 5 second period, the LED will automatically turns off for minimizing any unnecessary power consumption from the battery.

2. Coil Alignment Indication System
  
  This system uses a single LED to indicate the quality of alignment between the transmitter and receiver coil. The flashing frequency of the LED corresponds to how well the coils are aligned. The LED operate as follows:
  
  - LED Off -> capacitor is not charging / finish charging
  - Slow flashing -> reciver coil is far off from perfect alignment
  - Fast flashing -> reciver coil is half way from perfect alignment
  - LED ON -> reciver coil is nearly in perfect alignment
  
  These feedback allows adjustments to the robot's position for maximizing the charging efficiency.


- Charging Strategy
  
Since the system uses wireless charging to charge a capacitor, the charging behavior follows an exponential curve. The capacitor charges rapidly at lower voltages and slow down significantly as it approaches its maximum voltage. Although the target is to charge up to 5V, but reaching to this value would require a long charging time.
Given the competition rules impose a time penalty if fail to reach 5V. Therefore after performing a trade-off analysis back with calculation, we decided to keep charging the capacitor even when its above 5V, so we can have more than 5V inside the capacitor when we leave.
However, the capacitor naturally experience voltage leakage after charging, because of the experimental results, it shows that the time require for the voltage drop from 5V to 4.7V is around 2 mins. Therefore, charging up to more than 5V will ensure the capacitor maintains a voltage value above 4.7V by the end of the competition.
Although ending up at 4.8V results in a penalty of approximately 1.2 seconds, even in worst-case scenario it will result in no more than 2.7 seconds, the time used to stay charging even after 5V outweights the penalty. Consequently, the strategy of charging up to more than 5V ensures we have more than 4.8V and optimized the balance between charging duration and penalty cost. 
