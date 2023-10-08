# Project 06：Barrier Gate

![Img](/media/611.png)

## 1. Introduction
Last time my dad drove me to eat seafood, however, when our car came to the barrier gate of the parking lot, the gate rose automatically, and when the car passed, it fell automatically. 

Maybe you're as curious about this device as I am, let’s make a barrier gate can automatically rise and fall together! 
The following are the tools we need.

## 2. Components
|![Img](/media/KidsunoMainboard.png)|![Img](/media/ObstacleAvoidanceSensor.png)|![Img](/media/270°Servo.png)|
| :--: | :--: | :--: |
|Kidsuno Mainboard×1|Obstacle Avoidance Sensor×1|270°Servo×1|
|![Img](/media/ConnectionWire.png)|![Img](/media/USBCable.png)| ![Img](/media/BarrierGate.png) |
|Connection Wire×1|USB Cable×1| Barrier Gate×1 |

![Img](/media/612.png)


## 3. Installation Steps
Please refer to the following link：https://www.dropbox.com/scl/fo/whacdlki5y44kevau03qa/h?dl=0&rlkey=ogbigsw7lxv8zhkvr1oqhlkmz


## 4. Function: Read the Obstacle Avoidance Sensor
![Img](/media/613.png)

## 5. Wiring Diagram
Connect the kidsuno mainboard and computer via a USB cable, and connect the servo to the G, V and D13 interface of the mainboard and the obstacle avoidance sensor to the No.1 interface of the mainboard.
Note: The brown wire is connected to G, the red wire is connected to V and the orange wire is connected to D13.
![Img](/media/614.png)

## 6. Write the Program
① Drag the instruction block ![Img](/media/615.png) in the **Events** module to the script area.
![Img](/media/616.png)

② Drag the instruction block ![Img](/media/617.png) in the **Serial** module to the script area and take the baud rate 9600 as an example.
![Img](/media/618.png)

③ Drag the instruction block![Img](/media/619.png) in the **Pins** module to the script area. Since the obstacle avoidance sensor is connected to pin D5 of port 1 on the mainboard, then change the number 0 to 5.
![Img](/media/620.png)

④ Drag the instruction block ![Img](/media/621.png) in the **Control** module to the script area.
![Img](/media/622.png)

⑤ Drag the instruction block ![Img](/media/623.png) in the **Serial** module to the script area.
![Img](/media/624.png)

⑥ Drag the instruction block ![Img](/media/625.png) in the **Pins** module to the script area and put it into the block![Img](/media/626.png), then change the number 0 to 5.
![Img](/media/627.png)

⑦ Drag the instruction block ![Img](/media/628.png) in the **Control** module to the script area and change the number 1 to 0.3.
![Img](/media/629.png)

⑧ Complete Program
![Img](/media/630.png)


## 7. Test Result
Click![Img](/media/631.png) to upload the complete program to the kidsuno mainboard and power up, then click ![Img](/media/632.png) in the serial monitor area to set the baud rate to 9600. When the obstacle avoidance sensor detects an obstacle, the serial monitor will print a digital signal 0, otherwise, it will print 1.
![Img](/media/919.png)
![Img](/media/633.png)


## 8. Function: Obstacle Avoidance Sensor Controls the Servo
![Img](/media/634.png)


## 9. Flow Chart 
First, set the angle of the servo to 32°. When the obstacle avoidance sensor detects an obstacle, the servo will rotate to 100°, otherwise it will not rotate.
![Img](/media/635.png)


## 10. Add the Servo Instruction Module
![Img](/media/636.png)


## 11. Write the Program

① Find the instruction blocks
（1）![Img](/media/637.png)
<br>        
（2）![Img](/media/638.png)
<br>
（3）![Img](/media/639.png)
<br>
（4）![Img](/media/640.png)
<br>
（5）![Img](/media/641.png)
<br>
（6）![Img](/media/642.png)
<br>
（7）![Img](/media/643.png)
<br>
（8） ![Img](/media/644.png)
<br>

② Complete Program
![Img](/media/645.png)

## 12. Test Result
Click![Img](/media/631.png) to upload the complete program to the kidsuno mainboard and power up. When the obstacle avoidance sensor detects an obstacle, the servo will rotate to 100° and the barrier gate will open, otherwise it will not rotate and the barrier gate will close.
![Img](./FILES/Project%2006：Barrier%20Gate.md/img-20230714083213.png)













































































