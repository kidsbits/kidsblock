# Project 05：Windshield Wipers

![Img](media/511.png)

## 1. Introduction
Our family drove out for a trip at the weekend, however, it suddenly rained heavily on the way home. My father turned on the windshield wipers and the rain on the front glass of the car was constantly scraped away. Let’s explore the reason!

## 2. Components
|![Img](media/KidsunoMainboard.png)|![Img](media/SteamSensor.png)|![Img](media/270°Servo.png)|
| :--: | :--: | :--: |
|Kidsuno Mainboard×1|Steam Sensor×1|270°Servo×1|
|![Img](media/ConnectionWire.png)|![Img](media/USBCable.png)| ![Img](media/WindshieldWipers.png) |
|Connection Wire×1|USB Cable×1| Windshield Wipers×1 |

![Img](media/512.png)

## 3. Installation Steps
Please refer to the following link：https://www.dropbox.com/scl/fo/whacdlki5y44kevau03qa/h?dl=0&rlkey=ogbigsw7lxv8zhkvr1oqhlkmz


## 4. Function: Steam Sensor Detects Water
![Img](media/513.png)


## 5. Wiring Diagram
Connect the kidsuno mainboard and computer via a USB cable, and connect the servo to the G, V and D13 interface of the mainboard and the steam sensor to the No.7 interface of the mainboard.
The brown wire is connected to G, the red wire is connected to V and the orange wire is connected to D13.
![Img](media/514.png)

## 6. Write the Program
① Drag the instruction block ![Img](media/515.png) in the **Events** module to the script area.
![Img](media/516.png)

② Drag the instruction block ![Img](media/517.png) in the **Serial** module to the script area and take the baud rate 9600 as an example.
![Img](media/518.png)

③ Drag the instruction block ![Img](media/519.png) in the **Pins** module to the script area. Since the steam sensor is connected to pin A0 of port 7 on the mainboard, then change the number 0 to A0.
![Img](media/520.png)

④ Drag the instruction block ![Img](media/521.png) in the **Control** module to the script area. 
![Img](media/522.png)

⑤ Drag the instruction block ![Img](media/523.png) in the **Serial** module to the script area.
![Img](media/524.png)

⑥ Drag the instruction block ![Img](media/525.png) in the **Pins** module to the script area and put it into the block![Img](media/526.png).
![Img](media/527.png)

⑦ Drag the instruction block![Img](media/528.png) in the **Control** module to the script area and change the number 1 to 0.3.
![Img](media/529.png)

⑧ Complete Program
![Img](media/530.png)


## 7. Test Result
Click ![Img](media/531.png) to upload the complete program to the kidsuno mainboard and power up, then click![Img](media/532.png) in the serial monitor area to set the baud rate to 9600. When we drip water gradually into the metal detection area of the steam sensor, the analog number will increase gradually.
![Img](media/533.png)


## 8. Function: Steam Sensor Controls the Servo
![Img](media/534.png)


## 9. Flow Chart 
First, set the angle of the servo to 0°. When the analog value of the steam  sensor is greater than 200, the servo will rotate back and forth at 0-100°, otherwise, it will not rotate and the angle of the servo will be 0°.
![Img](media/535.png)


## 10. Add the Servo Instruction Module
![Img](media/536.png)


## 11. Description of Building Blocks 
<span style="color: rgb(255, 76, 65);">This is the variable module. Let’s look at it!</span> 

There are commonly used **declare global numeric variable type integer name assigned to 0**, **variable** and **Set variable to 0** instruction squares:
![Img](media/537.png)

When you need to use this variable, drag the block directly into the script area to edit it!

## 12. Write the Program

① Find the instruction blocks
（1）![Img](media/538.png)
<br>   
（2）![Img](media/539.png)
<br>   
（3）![Img](media/540.png)
<br>
（4）![Img](media/541.png)
<br>
（5）![Img](media/542.png)
<br>
（6）![Img](media/543.png)
<br>
（7）![Img](media/544.png)
<br>
（8）![Img](media/545.png)
<br>

② Complete Program
![Img](media/546.png)


## 13. Test Result
Click![Img](media/531.png) to upload the complete program to the kidsuno mainboard and power up. Dripping water gradually into the metal detection area of the steam sensor, if the analog value is greater than 200, the servo will rotate back and forth at 0-100° and the windshield wipers will swing, otherwise, it will not rotate and the wipers will not swing.
![Img](media/project05.png)


## 14. Extended Project
![Img](media/547.png)

The sample code is below：
![Img](media/548.png)











































