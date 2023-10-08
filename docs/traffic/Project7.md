# Project 07：Astern Indicating Device

![Img](/media/711.png)

## 1. Introduction
With the development of science and technology, cars boast the ability of intelligent environment perception, which can automatically analyze the safety and danger when driving. 

For example, we can observe the specific situation behind the car if we turn on the astern indicating device when backing up, which can avoid the car being knocked. Let’s make an astern indicating device together! 
The following are the tools we need.

## 2. Components
|![Img](/media/KidsunoMainboard.png)|![Img](/media/UltrasonicAdapter.png)|![Img](/media/UltrasonicSensor.png)| ![Img](/media/AsternIndicatingDevice.png) |
| :--: | :--: | :--: | :--: |
|Kidsuno Mainboard×1|Ultrasonic Adapter Board×1|Ultrasonic Sensor×1| Astern Indicating Device×1 |
|![Img](/media/8×8DotMatrixDisplay.png)|![Img](/media/ConnectionWire.png)|![Img](/media/USBCable.png)| |
|8×8 Dot Matrix Display×1|Connection Wire×2|USB Cable×1| |

![Img](/media/712.png)


## 3. Installation Steps
Please refer to the following link：https://www.dropbox.com/scl/fo/whacdlki5y44kevau03qa/h?dl=0&rlkey=ogbigsw7lxv8zhkvr1oqhlkmz


## 4. Function: 8*8 Dot Matrix Displays Expression Patterns
![Img](/media/713.png)


## 5. Wiring Diagram
Connect the kidsuno mainboard and computer via a USB cable. Then connect the 8×8 dot matrix module to the No.8 interface of the mainboard and the ultrasonic adapter board to the No.9 interface of the mainboard. The Vcc, Trig, Echo, and Gnd of the ultrasonic sensor correspond to the same port of the ultrasonic adapter board.
![Img](/media/714.png)

## 6. Add the Instruction Library of the 8*8 Dot Matrix
To use the 8×8 dot matrix , we need to call the "Display" module in the "Extension" function. Click "Matrix 8*8 IIC" then tap ![Img](/media/744.png) to return to the programming interface.
![Img](/media/715.png)
**Extension** Instruction 

![Img](/media/716.png)
Add **Matrix 8*8 IIC** Display                        

![Img](/media/717.png)


## 7. Write the Program
① Drag the instruction block![Img](/media/718.png) in the **Events** module to the script area.
![Img](/media/719.png)

② Click the **Matrix HT16K33** module on the left of the instruction area, then all the 8*8 dot matrix instruction blocks will be displayed.
![Img](/media/720.png)
![Img](/media/721.png)

③ Drag the instruction block![Img](/media/722.png) and ![Img](/media/723.png) in the **Matrix HT16K33** module to the script area.
![Img](/media/724.png)

④ Drag the instruction block ![Img](/media/725.png) in the **Control** module to the script area. 
![Img](/media/726.png)

⑤ Drag the instruction block![Img](/media/727.png) ,![Img](/media/728.png) and ![Img](/media/729.png) in the **Matrix HT16K33** module to the script area.
![Img](/media/730.png)

⑥ Drag the instruction block ![Img](/media/731.png) in the **Control** module to the script area and change the number 1 to 2.
![Img](/media/732.png)

⑦ Copy the instruction block![Img](/media/733.png)10 times and put them into the block ![Img](/media/734.png) respectively, then change the expression pattern ![Img](/media/735.png) to![Img](/media/736.png).
![Img](/media/737.png)

⑧ Complete Program
![Img](/media/738.png)
![Img](/media/739.png)
![Img](/media/740.png)
![Img](/media/741.png)


## 8. Test Result
Click![Img](/media/742.png) to upload the complete program to the kidsuno mainboard and power up, then the the 8*8 dot matrix will display colorful expression patterns.
![Img](/media/920.png)

## 9. Function：Ultrasonic Sensor Detects Distance
![Img](/media/743.png)


## 10. Add the Instruction Library of the Ultrasonic Sensor
To use the ultrasonic sensor , we need to call the **Sensor** module in the **Extension** function. Click **Ultrasonic** then tap ![Img](/media/744.png) to return to the programming interface.
![Img](/media/745.png)
**Extension** Instruction 

![Img](/media/746.png)
Add **Ultrasonic** Sensor

![Img](/media/747.png)

## 11. Description of the the Building Blocks
![Img](/media/748.png)
This is the ultrasonic sensor instruction block used to measure the distance for the specified pin. The distance unit can be selected as cm or inch.


## 12. Write the Program
① Drag the instruction block in the **Events** module to the script area.
![Img](/media/749.png)

②  Drag the instruction block  in the **Serial** module to the script area and take the baud rate 9600 as an example.
![Img](/media/750.png)

③ Drag the instruction block ![Img](/media/751.png) in the **Pins** module to the script area and copy once. Since the ultrasonic sensor is connected to port 9 on the mainboard(Trig corresponds to pin D10 and Echo corresponds to pin D11), then change the number 0 to 10 and 11, and change the input behind number 10 to output.
![Img](/media/752.png)

④ Drag the instruction block ![Img](/media/753.png) in the **Control** module to the script area.
![Img](/media/754.png)

⑤ Drag the instruction block ![Img](/media/755.png) in the **Serial** module to the script area.
![Img](/media/756.png)

⑥ Drag the instruction block ![Img](/media/757.png) in the **Ultrasonic** module to the script area and put it into the block![Img](/media/758.png), then change the number 2 to 10, 6 to 11, and take the distance unit cm as an example.
![Img](/media/759.png)

⑦ Drag the instruction block ![Img](/media/760.png) in the **Control** module to the script area and change the number 1 to 0.3.
![Img](/media/761.png)

⑧ Complete Program
![Img](/media/762.png)


## 13. Test Result
Click![Img](/media/763.png) to upload the complete program to the kidsuno mainboard and power up, then click![Img](/media/764.png) in the serial monitor area to set the baud rate to 9600. 
Moving your hand in front of the ultrasonic sensor, the distance displayed becomes smaller when we are close to the sensor and larger when we are far away from it.
![Img](/media/921.png)
![Img](/media/765.png)


## 14. Function: Ultrasonic Sensor Controls the 8*8 Dot Matrix
![Img](/media/766.png)


## 15. Flow Chart 
Initialize the 8*8 dot matrix and read the distance value of the ultrasonic sensor. If the distance is greater than 0 and less than 10cm, the 8*8 dot matrix shows a "stop" pattern, otherwise, it displays a "backward" pattern.
![Img](/media/767.png)


## 16. Write the Program

① Find the instruction blocks
（1）![Img](/media/768.png)
<br>        
（2）![Img](/media/769.png)
<br>
（3）![Img](/media/770.png)
<br>
（4）![Img](/media/771.png)
<br>
（5）![Img](/media/772.png)
<br>
（6）![Img](/media/773.png)
<br>
（7）![Img](/media/774.png)
<br>
（8）![Img](/media/775.png)
<br>
（9）![Img](/media/776.png)
<br>

② Complete Program
![Img](/media/777.png)

## 17. Test Result
Click![Img](/media/763.png) to upload the complete program to the kidsuno mainboard and power up. When the ultrasonic sensor detects the object within a range of 0cm to 10cm, the 8*8 dot matrix shows a "Stop" pattern, otherwise, it displays a "backward" pattern.
![Img](./FILES/Project%2007：Astern Indicating Device.md/img-20230714083256.png)


## 18. Extended Project
![Img](/media/778.png)


The sample code is below：
![Img](/media/779.png)























