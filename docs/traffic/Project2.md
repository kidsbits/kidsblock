<span style="color: rgb(255, 76, 65);">**Note：The sensors, modules and the 270° servo in each project are shared.**</span>

# Project 02： Sound of Traffic Lights

![Img](/media/211.png)

## 1. Introduction
Today, I was walking home from school when I saw the traffic light beep at the intersection. Can we add a sound to the traffic light module in project 01? Let's take a look at the tools first.

## 2. Components
|![Img](/media/KidsunoMainboard.png)|![Img](/media/TrafficLightModule.png)|![Img](/media/ActiveBuzzer.png)|
| :--: | :--: | :--: |
|Kidsuno Mainboard×1|Traffic Light Module×1|Active Buzzer×1|
|![Img](/media/ConnectionWire.png)|![Img](/media/USBCable.png)| ![Img](/media/Sound.png) |
|Connection Wire×2|USB Cable×1| Sound of Traffic Light×1 |

![Img](/media/212.png)


## 3. Installation Steps
Please refer to the following link：https://www.dropbox.com/scl/fo/whacdlki5y44kevau03qa/h?dl=0&rlkey=ogbigsw7lxv8zhkvr1oqhlkmz

## 4. Function: Make the Active Buzzer Sound
![Img](/media/213.png)

## 5. Wiring Diagram
Connect the mainboard and computer via a USB cable, and connect the traffic light module to the No.1 interface of the mainboard and the active buzzer to the No.9 interface of the mainboard.
![Img](/media/214.png)

## 6. Write the Program
① Drag the instruction block![Img](/media/215.png) in the **Events** module to the script area.
![Img](/media/216.png)

② Drag the instruction block ![Img](/media/217.png)
in the **Pins** module to the script area. Since the interface of the active buzzer module is connected to the D10 pin of interface 9 on the mainboard, then change the number 0 to 10 and the **input** to **output**.
![Img](/media/218.png)

③ Drag the instruction block![Img](/media/219.png)
in the **Pins** module to the script area and change the number 0 to 10.
![Img](/media/220.png)

④ Complete Program
![Img](/media/221.png)


## 7. Test Result
Click ![Img](/media/222.png) to upload the complete program to the kidsuno mainboard and power up, then the active buzzer will sound. It seems pretty amazing, right?
![Img](/media/915.png)

## 8. Function: Make the Active Buzzer Beep
![Img](/media/223.png)

## 9. Write the Program
① change the **high** in the previous program to **low**.
![Img](/media/224.png)

② Drag the instruction block![Img](/media/225.png) in the "Control" module to the script area. 
![Img](/media/226.png)

③ Drag the instruction block![Img](/media/227.png) in the **Pins** module to the script area and change the number 0 to 10.
![Img](/media/228.png)

④ Drag the instruction block![Img](/media/229.png) in the **Control** module to the script area. The number 1 can be changed to other numbers. Here, the number 0.5 is taken as an example.
![Img](/media/230.png)

⑤ Copy the code string![Img](/media/231.png) once and change **high** to **low** .
![Img](/media/232.png)

⑥ Complete Program
![Img](/media/233.png)

## 10. Test Result
Click ![Img](/media/222.png) to upload the complete program to the kidsuno mainboard and power up, then the active buzzer will beep. It seems pretty amazing, right?
![Img](/media/915.png)

## 11. Function: Sound of Traffic Lights 
![Img](/media/234.png)

## 12. Flow Chart 
First the three LED lights will be off the buzzer will not beep, then the buzzer beeps and the red light flashes for 5 s then goes off , then the yellow light flashes for 3 times then goes off, then the green light will be on for 5 s then go off.
![Img](/media/235.png)

## 13. Write the Program

① Find the instruction blocks
（1）![Img](/media/236.png)
<br>
（2）![Img](/media/237.png)
 <br>
（3）![Img](/media/238.png)

② Complete Program
![Img](/media/239.png)
![Img](/media/240.png)

## 14. Test Result
Click ![Img](/media/222.png) to upload the complete program to the kidsuno mainboard and power up, then the buzzer beeps and the red light flashes for 5 s then it won’t beep and the light will be off , then the yellow light flashes for 3 times then goes off, then the green light will be on for 5 s then go off.
![Img](/media/916.png)

## 15. Extended Project
![Img](/media/241.png)

The sample code is below：
![Img](/media/242.png)
![Img](/media/243.png)





















































