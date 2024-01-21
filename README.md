## Automatic-Railway-Gate-Controller

# Introduction 
The Automatic Railway Gate Control System is a simple but very useful project, which helps is automatically opening and closing the railway gate upon detecting the arrival or departure of the train.
In general, Railway gates are opened or closed manually by a gatekeeper. The information about the arrival of the train for opening or closing of the door is received from the nearby station. However, some railway crossings are unmanned, and many railway accidents occur at these unmanned level crossings.
This system is designed to manage the control system of the railway gate using the 8051 microcontrollers. The main purpose of this project is to propose an idea to make the process automated so that the probability of accidents at railroad crossings is reduced drastically. As a train approaches the railway crossing from either side, the sensors placed at a certain distance from the gate detect the approaching train and inform the microcontroller about it. This signal is used to trigger the microcontroller for opening or closing of gates. The abstraction of this system is to provide the advanced control system available everywhere.

To avoid human intervention at level crossings completely, we need to automate the process of railway gate control. 

# Principle of Operation
The principle of operation behind the working of this project lies in the functioning of the IR Sensor. A Reflective type IR Sensor is used in this project.
In Reflective Type IR Sensor, the IR transmitter and receiver are placed side by side. When there is no obstacle in front of the sensor, the IR rays transmitted by the IR Transmitter will travel undetected as no rays are falling on the IR Receiver.
If there is an obstacle in front of the IR Transmitter and Receiver pair, the IR Rays get reflected off from the surface of the obstacle and are incident on the IR Receiver.
This setup can be configured to detect an object like a Train and in turn, can be used to switch ON or OFF loads like motors with the help of a microcontroller. 

# Project Components
# Microcontroller Section: 
<br>AT89C51 MCU: 8051 Microcontroller<br>
<br>11.0592 MHz Quartz Crystal<br>
<br>2 x 33pF Ceramic Capacitor<br>
<br>10µF / 16V Electrolytic Capacitor<br>
<br>10KΩ Resistors x 2<br>
<br>AT89C51 Programmer Board<br>

# Sensor and Load Section:
<br>2 x Reflective Type IR Sensor<br>
<br>2 x 1KΩ Resistor<br>
<br>L293D Motor Driver IC: Motor Driver (Rotates motor in either direction.)<br>
<br>Motor<br>

# Component Description

# IR Sensor:
An IR sensor is used in this project to sense the arrival and departure of the train.
An IR Sensor generally comprises two components: an IR Transmitter and an IR Receiver. An IR Transmitter is a device that emits IR Rays.
Similarly, an IR Receiver is a device that detects the IR Rays. Photo Diodes are the most commonly used IR Receivers. 
The following image shows the circuit of the IR Sensor used in this project : 
![image](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/c8967fb7-2104-4b17-9415-2b16bc5e9bf2)

# L293D Motor Driver: 
L293D is a motor driver IC used in this project to control the gate motor. L293D Motor Drive IC is a dual H-bridge type motor driver and is available in a 16-pin Dual in-line Package.
With the help of this motor driver IC, we can control two motors at a time with both forward and reverse direction control for individual motors.
Motor drivers are generally used to drive high-current drawing devices like DC Motors, stepper motors, high-intensity lights, etc. They act as simple current amplifiers as their input is a low current signal usually from a microcontroller and their output is a high current signal to drive the loads.

# Softwares:
<br>Keil uVision5<br>
<br>Proteus Software (Used for testing and verification)<br>

# Block Diagram 
![image](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/67e723e5-ff5e-4cff-afc1-be3a425e3116)

# Circuit Diagram of Automatic Railway Gate Control using 8051
![image](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/b3564a54-2c03-4852-9668-914f8c5a5afa)

# Circuit Design
The major components of our project are an 8051 microcontroller (AT89C51), a Reflective Type IR Sensor, an L293D Motor Driver IC, and a Motor.

The mandatory connections for 8051 MCU include an oscillator circuit, reset switch, and EA Pin.

A crystal oscillator of up to 20MHz can be used as a source of external clock. In this project, an 11.0592 MHz quartz crystal oscillator is used. To complete the external oscillator circuit, two 33pF capacitors are used. Finally, the EA pin is pulled high using a 10KΩ resistor.

Now, let us see the actual connections required to implement the project. That, first is the L293D Motor drive. The inputs (IN1 and IN2) to the motor driver (Pins 1 and 2) are given from Port 0 of the microcontroller.

But before connecting them, two 1KΩ resistors are used to pull the Port 0 pins high. Now, connect the motor driver input pins i.e. IN1 and IN2 to the first two pins of Port 0 i.e. P0.0 and P0.1.

A motor is connected to the OUT pins of the motor driver.

Finally connect two IR sensors to the microcontroller: one for detecting the arrival of the train and one for detecting the departure of the train.

So, connect the data outputs of the IR sensors to the pins P2.6 and P2.7 of the microcontroller.

# Methodology 
<br>1. Create a new project in the Keil uVision5 software, search for the microchip AT89C51RD2, and add the STARTUP.A51 file to the project.<br>
<br>2. Create a new empty document and write all the code in that. Save the file with the extension “.asm” and add the file to the Source Group.<br>
<br>3. In the Project menu, select Options for Target and go to the Output tab.<br>
<br>4. Check Create HEX File and click the OK button.<br>
<br>5. Thus Translate, Build, and Rebuild the project, making sure that there are no errors.<br>
<br>6. Create the project on Proteus Software, and implement the circuit.<br>
<br>7. Copy the destination of the HEX file and insert it in the Edit Component window of the AT89C51RD2 component in the Proteus Software.<br>
<br>8. Thus, we are ready with the simulation of the working project.<br>

# Hardware Circuit 

![1](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/9d4ae898-84ef-42ee-a638-72605b55ad7d)

![2](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/6a0e1761-e91d-462f-8b5a-653911c1b1ff)

![3](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/46d7cd84-fa6d-4605-8ef2-91aea7a5db39)

![4](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/af5bfcbd-6b77-4987-aa72-68bd3832ed27)
(Gate remains closed) 

![5](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/3328073b-abae-4c91-9e6d-4ca8573a7b6b)
(Gate opens for the train to pass)

# Working of the project

# CASE 1:
Assuming the length of the train is very long, the train cuts IR sensor 1 and the gates are closed. Then it travels and interrupts IR sensor 2. Now both IR sensors are being blocked. As the train passes further, IR sensor 1 is no longer blocked by the train but IR sensor 2 is still being blocked. Eventually train moves further and IR sensor 2 is no longer interrupted and the gates are closed. Therefore, the gates will be opened only when both IR sensors are not blocked.

# CASE 2:
There is a possibility that the train passes IR sensor 1 and waits in between. So in such cases, the gates must remain closed and open only when the train completely passes through IR sensor 2.

# CASE 3:
There is a possibility that there is only a single engine passing through the sensors. When it blocks IR sensor 1 and moves a little further, IR sensor 1 is again unblocked. Now, the engine is somewhere between IR sensors 1 and 2 but both sensors are unblocked. As per case 1, when both IR sensors are open, the gates shall be opened. That logic is very dangerous in this case because the engine is running somewhere between the two sensor pairs but the gates are open. To tackle this issue, a new algorithm is designed. In the new algorithm, the gates will be opened only when there is a block-unblock transition in IR sensor 2 equivalent to a similar transition in IR sensor 1.

# Results of the Simulation

# 1. Green light ON, Train has not arrived yet.

![image](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/92865127-77e5-4fef-a2c3-0287bc1e7d4c)

# 2. The train arrives/is between two sensors, the Gate closes/motor rotates clockwise, Green (OFF), Red (ON), Buzzer (ON)

![image](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/605467b7-0e79-437d-96ba-60a79488db7d)

# 3. Train completely passes the IR sensor 2, the Gate opens (motor rotates anti-clockwise), RED(OFF), Buzzer (OFF), GREEN(ON)

![image](https://github.com/PriyanshaNayak/Automatic-Railway-Gate-Controller/assets/87187181/34d16503-773f-4cf6-8693-c55310ff72bc)

# Advantages and Applications
<br>1. An Automatic Railway Gate Control is implemented with very simple hardware and easy control.<br>
<br> 2. Human intervention at level crossings can be removed with the help of this project and many railway level crossing accidents can be prevented.<br>

# Limitations
<br> 1. The system can be implemented more efficiently by incorporating a more efficient sensor network.<br>
<br> 2. A combination of manual wireless control and sensors-based control can be used for better operation.<br>









