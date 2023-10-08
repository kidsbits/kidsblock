# Project 04：An Automatic Door

![Img](/media/411.png)

## 1. Introduction
I find that there are many interesting inventions in our life. Last time I went to a library with my classmates to borrow a book about learning robots. When we came to the door, it opened automatically.

How magical it is! Today, let's make a device that can open the door automatically. Let’s look at the tools first.

## 2. Components
|![Img](/media/KidsunoMainboard.png)|![Img](/media/PIRMotionSensor.png)|![Img](/media/270°Servo.png)|
| :--: | :--: | :--: |
|Kidsuno Mainboard×1|PIR Motion Sensor×1|270°Servo×1|
|![Img](/media/ConnectionWire.png)|![Img](/media/USBCable.png)| ![Img](/media/AutomaticDoor.png) |
|Connection Wire×1|USB Cable×1| Automatic Door×1 |

![Img](/media/412.png)

## 3. Function: Rotate the Servo
![Img](/media/413.png)

## 4. Wiring Diagram
Connect the kidsuno mainboard and computer via a USB cable, and connect the servo to the G, V and D13 interface of the mainboard. The brown wire is connected to G, the red wire is connected to V and the orange wire is connected to D13.
![Img](/media/414.png)

## 5. Add the Servo Instruction Module
![Img](/media/415.png)

![Img](/media/416.png)
Diagram of the **Extension** Instruction Block

![Img](/media/417.png)
Add **Servo**

![Img](/media/418.png)


## 6. Description of the the Building Blocks

![Img](/media/419.png)
Set the rotation angle of the servo and the delayed time for a specified pin


## 7. Write the Program
① Drag the instruction block![Img](/media/420.png) in the **Events** module to the script area.
![Img](/media/421.png)

② Drag the instruction block ![Img](/media/422.png)
in the **Pins** module to the script area. Since the servo is connected to port G, V and D13 on the mainboard, then change the number 0 to 13 and the **input** to **output**.
![Img](/media/423.png)

③Drag the instruction block ![Img](/media/424.png)
in the **servo** module to the script area, then change the number 3 to 13 and the angle number 90 to 93, the delay of 200 remains unchanged.
![Img](/media/425.png)

④ Drag the instruction block ![Img](/media/426.png) in the **Control** module to the script area.

![Img](/media/427.png)

⑤ Drag the instruction block ![Img](/media/424.png)
in the **servo** module to the script area, then change the number 3 to 13, the angle number 90 to 93 and the delay of 200 to 500.
![Img](/media/428.png)

⑥ Copy the instruction block![Img](/media/429.png) 3 times in the ![Img](/media/430.png)block and place them into it, then change the angle number 93 to 62, 31 and 0.
![Img](/media/431.png)

⑦ Complete Program
![Img](/media/432.png)

## 8. Test Result
Click ![Img](/media/433.png) to upload the complete program to the kidsuno mainboard and power up, then the servo will rotate from 93°to 62° to 31° to 0° and rotate from 0° to 31° to 62° to 93°.

## 9. Installation Steps
Please refer to the following link：https://www.dropbox.com/scl/fo/whacdlki5y44kevau03qa/h?dl=0&rlkey=ogbigsw7lxv8zhkvr1oqhlkmz

## 10. Wiring Diagram
Connect the kidsuno mainboard and computer via a USB cable, and connect the servo to the G, V and D13 interface of the mainboard and the PIR motion sensor to the No.1 interface of the mainboard.
The brown wire is connected to G, the red wire is connected to V and the orange wire is connected to D13.
![Img](/media/434.png)

## 11. Function: Read the PIR Motion Sensor
![Img](/media/435.png)


## 12. Description of the the Building Blocks
![Img](/media/436.png)
This is the digital signal (0 or 1) for a specified pin.


## 13. Write the Program
① Drag the instruction block ![Img](/media/437.png) in the **Events** module to the script area.
![Img](/media/438.png)

② Drag the instruction block ![Img](/media/439.png) in the **Serial** module to the script area and take the baud rate 9600 as an example.
![Img](/media/440.png)

③  Drag the instruction block ![Img](/media/441.png) in the **Pins** module to the script area. Since the PIR motion sensor is connected to pin D5 of port 1 on the mainboard, then change the number 0 to 5.
![Img](/media/442.png)

④ Drag the instruction block ![Img](/media/443.png) in the **Control** module to the script area. 
![Img](/media/444.png)

⑤ Drag the instruction block ![Img](/media/445.png) in the **Serial** module to the script area.
![Img](/media/446.png)

⑥ Drag the instruction block ![Img](/media/447.png) in the **Pins** module to the script area and put it into the block ![Img](/media/448.png), then change number 0 to 5.
![Img](/media/449.png)

⑦ Drag the instruction block ![Img](/media/450.png) in the **Control** module to the script area and change the number 1 to 0.3.
![Img](/media/451.png)

⑧ Complete Program
![Img](/media/452.png)


## 14. Test Result
Click![Img](/media/453.png) to upload the complete program to the kidsuno mainboard and power up, then click ![Img](/media/454.png) in the serial monitor area to set the baud rate to 9600. When the PIR motion sensor detects a person or animal moving, the serial monitor prints a digital signal 1, otherwise it prints 0.
![Img](/media/918.png)
![Img](/media/455.png)

## 15. Function: PIR Motion Sensor Controls the Servo
![Img](/media/456.png)

## 16. Flow Chart 
First, set the angle of the servo to 93°. When the PIR motion sensor detects a person or animal passing by, it will rotate to 0° and it will not rotate if no man or animal is passing by.
![Img](/media/457.png)


## 17. Write the Program

① Find the instruction blocks
（1）![Img](/media/458.png)
<br>         
（2）![Img](/media/459.png)
<br>
（3）![Img](/media/460.png)
<br>
（4）![Img](/media/461.png)
<br>
（5）![Img](/media/462.png)
<br>
（6）![Img](/media/463.png)
<br>

② Complete Program
![Img](/media/464.png)


## 18. Test Result
Click![Img](/media/453.png) to upload the complete program to the kidsuno mainboard and power up. When the PIR motion sensor detects a person or animal passing by, it will rotate to 0° and the door will be opened automatically , and it will not rotate if no man or animal is passing by and the door will not be opened.
![Img](./FILES/Project%2004：An%20Automatic Door.md/img-20230714083105.png)


## 19. Extended Project
![Img](/media/465.png)

The sample code is below：
![Img](/media/466.png)













