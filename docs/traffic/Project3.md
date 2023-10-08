# Project 03：Street Lamps

![Img](/media/311.png)

## 1. Introduction
Street lamps are ubiquitous in our daily life. For example, some public street lamps come on automatically at night and go off automatically during the day. Do you want to know why? Let’s make a small street lamp together. Look at the tools first.

## 2. Components
|![Img](/media/KidsunoMainboard.png)|![Img](/media/Photoresistor.png)|![Img](/media/WhiteLED.png)|
| :--: | :--: | :--: |
|Kidsuno Mainboard×1|Photoresistor×1|White LED Module×1|
|![Img](/media/ConnectionWire.png)|![Img](/media/USBCable.png)| ![Img](/media/StreetLamps.png) |
|Connection Wire×2|USB Cable×1| Street Lamps×1 |

![Img](/media/312.png)

## 3. Installation Steps
Please refer to the following link：https://www.dropbox.com/scl/fo/whacdlki5y44kevau03qa/h?dl=0&rlkey=ogbigsw7lxv8zhkvr1oqhlkmz

## 4. Function: Detect the Light Intensity 
![Img](/media/313.png)

## 5. Wiring Diagram
Connect the kidsuno mainboard and computer via a USB cable, and connect the photoresistor to the No.7 interface of the mainboard and the LED module to the No.1 interface of the mainboard.
![Img](/media/314.png)

## 6. Description of the the Building Blocks
![Img](/media/315.png)
The block is used to set serial baud rate(generally, the baud rate 9600 is taken as an example)

![Img](/media/316.png)
This block is used to set print mode for the serial port. **warp** means line feed printing, **no-warp** means no line feed printing, **HEX** means hexadecimal printing.

![Img](/media/317.png)
It is used to read the analog signal value of the specified pin（range：0~1023)

## 7. Write the Program
① Drag the instruction block![Img](/media/318.png) in the **Events** module to the script area.
![Img](/media/319.png)

② Drag the instruction block![Img](/media/320.png)
in the **Serial** module to the script area and take the baud rate 9600 as an example.
![Img](/media/321.png)

③ Drag the instruction block![Img](/media/322.png)
in the **Pins** module to the script area. Since the photoresistor is connected to pin A0 of port 7 on the mainboard, then change the number 0 to A0.
![Img](/media/323.png)

④ Drag the instruction block ![Img](/media/324.png) in the **Control** module to the script area. 
![Img](/media/325.png)

⑤ Drag the instruction block![Img](/media/326.png) in the **Serial** module to the script area.
![Img](/media/327.png)

⑥ Drag the instruction block![Img](/media/328.png) in the **Pins** module to the script area and put it into the block ![Img](/media/329.png)
![Img](/media/330.png)

⑦ Drag the instruction block![Img](/media/331.png) in the **Control** module to the script area and change the number 1 to 0.3.
![Img](/media/332.png)

⑧ Complete Program
![Img](/media/333.png)

## 8. Test Result
Click ![Img](/media/334.png) to upload the complete program to the kidsuno mainboard and power up, then click ![Img](/media/335.png) in the serial monitor area to set the baud rate to 9600. Then the serial monitor will print the analog value read by the photoresistor. When the light intensity in the environment where the photoresistor is located gradually decreases, the analog value increases gradually, otherwise, the analog value decreases.
![Img](/media/917.png) 
![Img](/media/analogvalue.png)

## 9. Function: Photoresistor Controls LED
![Img](/media/336.png)


## 10. Description of the the Building Blocks
![Img](/media/337.png)
It is a conditional statement code executing **if-then-else ** function: If the logical judgment statement in ![Img](/media/338.png) is satisfied, the code statement below **then** is executed, otherwise, the code below **else** is executed.

## 11. Flow Chart 
First, set the LED to off. When the light intensity value read by the photoresistor is less than 200, the LED will be on, otherwise, it will be off.
![Img](/media/339.png)

## 12. Write the Program

① Find the instruction blocks
（1）![Img](/media/340.png)
<br>         
（2）![Img](/media/341.png)
<br>
（3）![Img](/media/342.png)
<br>
（4）![Img](/media/343.png)
<br>
（5）![Img](/media/344.png)
<br>

② Complete Program
![Img](/media/345.png)


## 13. Test Result
Click ![Img](/media/334.png) to upload the complete program to the kidsuno mainboard and power up, then use your hands to cover the photoresistor . When the light intensity value read by the photoresistor is less than 200, the LED will be on, otherwise, it will be off.
![Img](./FILES/Project%2003：Street%20Lamps.md/img-20230714083023.png)

## 14. Extended Project
![Img](/media/346.png)

The sample code is below：
![Img](/media/347.png)









