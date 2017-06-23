Concepts of Line Follower

Concept of working of line follower is related to light. We use here the behavior of light at black and white surface. When light fall on a white surface it is almost full reflected and in case of black surface light is completely absorbed. This behavior of light is used in building a line follower robot.
Concept of White Line Follower Robot
Concept of Black Line Follower Robot
In this arduino based line follower robot we have used IR Transmitters and IR receivers also called photo diodes. They are used for sending and receiving light. IR transmits infrared lights. When infrared rays falls on white surface, it’s reflected back and catched by photodiodes which generates some voltage changes. When IR light falls on a black surface, light is absorb by the black surface and no rays are reflected back, thus photo diode does not receive any light or rays.
Here in this line follower robot when sensor senses white surface then arduino gets 1 as input and when senses black line arduino gets 0 as input.
 
Circuit Explanation

The whole line follower robot can be divided into 3 sections: sensor section, control section and driver section.
 
Sensor section:
This section contains IR diodes, potentiometer, Comparator (Op-Amp) and LED’s. Potentiometer is used for setting reference voltage at comparator’s one terminal and IR sensors are used to sense the line and provide a change in voltage at comparator’s second terminal. Then comparator compares both voltages and generates a digital signal at output. Here in this line follower circuit we have used two comparator for two sensors. LM 358 is used as comparator. LM358 has inbuilt two low noise Op-amps.
 
Control Section:
Arduino Pro Mini is used for controlling whole the process of line follower robot. The outputs of comparators are connected to digital pin number 2 and 3 of arduino. Arduino read these signals and send commands to driver circuit to drive line follower. 
 
Driver section:
Driver section consists motor driver and two DC motors. Motor driver is used for driving motors because arduino does not supply enough voltage and current to motor. So we add a motor driver circuit to get enough voltage and current for motor. Arduino sends commands to this motor driver and then it drive motors.
 
Working of Line Follower Robot using Arduino

Working of line follower is very interesting. Line follower robot senses black line by using sensor and then sends the signal to arduino. Then arduino drives the motor according to sensors' output.
Working of Line Follower Robot using Arduino
Here in this project we are using two IR sensor modules namely left sensor and right sensor. When both left and right sensor senses white then robot move forward.
Working of Arduino Line Follower Robot
If left sensor comes on black line then robot turn left side.
Turning left to line follower robot using arduino
If right sensor sense black line then robot turn right side until both sensor comes at white surface. When white surface comes robot starts moving on forward again.
Turning right to line follower robot
If both sensors comes on black line, robot stops.
Stopping Arduino Line Following Robot
Circuit Diagram

Line Follower Robot using Arduino: Circuit Diagram
Complete circuit diagram for arduino based line follower robot is shown in the above iamge. As you can see output of comparators is directly connected to arduino digital pin number 2 and 3. And motor driver’s input pin 2, 7, 10 and 15 is connected to arduino's digital pin number 4, 5, 6 and 7 respectively. And one motor is connected at output pin of motor driver 3 and 6 and another motor is connected at pin 11 and 14. 
 
Program Explanation

In program, first of all we defined input and output pin, and then in loop we checks inputs and sends output according to inputs to output pin for driving motor. For checking input pin we used “if” statements.
Code for line follower robot
Code for arduino line follower
There are four conditions in this line following robot that we read by using arduino. We have used two sensor namely left sensor and right sensor.
Input
Output
Movement
Of Robot
Left Sensor
Right Sensor
Left Motor
 
Right Motor
LS
RS
LM1
LM2
RM1
RM2
 
0
0
0
0
0
0
Stop
0
1
1
0
0
0
Turn Right
1
0
0
0
1
0
Turn Left
1
1
1
0
1
0
Forward
 
We write program according to the conditions shown in table above.
 
Required Components

Arduino
In our Project we have used a microcontroller to control whole the process of system that is ARDUINO. Arduino is an open source hardware and very useful for project developments. There are many types of arduino like Arduino UNO, arduino mega, arduino pro mini, Lilypad etc. available in the market. Here we have used arduino pro mini in this project as arduino pro mini is small and so breadboard compatible. To burn program we have used FTDI burner.
Arduino pro Mini
 
L293D Motor Driver
L293D is a motor driver IC which has two channels for driving two motors. L293D has two inbuilt Transistor Darlington pair for current amplification and a separate power supply pin for giving external supply to motors.
L293D Motor Driver IC
 
IR Module:
IR Module is sensor circuit which consists IR LED/photodiode pair, potentiometer, LM358, resistors and LED. IR sensor transmits Infrared light and photo diode receives the infrared light.
IR Module
