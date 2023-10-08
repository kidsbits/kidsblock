<span style="color: rgb(255, 76, 65);">**Note：The sensors, modules and the 270° servo in each project are shared.**</span>

# Project 01：Traffic Lights

![Img](/media/111.png)

## 1. Introduction
I met a big traffic jam on my way to school today. The red light at the intersection where I waited lasted very long and the green light flashed a few times and then changed to yellow. It seems that there's something wrong with the traffic light's digital signal. 
Can we use a traffic light module to simulate the working principle of traffic lights?  Let's take a look at the tools first.


## 2. Components
|![Img](/media/KidsunoMainboard.png)|![Img](/media/TrafficLightModule.png)|![Img](/media/ConnectionWire.png)|![Img](/media/USBCable.png)| ![Img](/media/TrafficLights.png) |
| :--: | :--: | :--: | :--: | :--: |
|Kidsuno Mainboard×1|Traffic Light Module×1|Connection Wire×1|USB Cable×1| Traffic Lights×1 |

![Img](/media/112.png)


## 3. Component Knowledge
（1）Traffic lights are signal lights that command the traffic operation, which are generally composed of a red light, a green light and a yellow light. The red light means impassable, the green light means passable, and the yellow light means a warning.

（2）To keep the light on, the electricity is needed. When we say that there is electricity, we mean that there is current flowing through an electrical appliance like a light. Current comes to our home from the power station via wires. And the generator of a power station is the power supply, which enables to provide voltage and current. 

The battery we usually use is also the power supply. Wires can be used to conduct electricity, which connect a path for the current to flow. This path is called a circuit. If we want to make a lamp emit light, both a power supply and a complete circuit are needed.
![Img](/media/113.png)

## 4. Installation of Traffic Lights

Please refer to the following link：https://www.dropbox.com/scl/fo/whacdlki5y44kevau03qa/h?dl=0&rlkey=ogbigsw7lxv8zhkvr1oqhlkmz


## 5. Function: Light Up the Traffic Lights
![Img](/media/114.png)

## 6. Wiring Diagram
Connect the kidsuno mainboard and computer via a USB cable, and connect the traffic light module to the No.1 interface of the mainboard.

![Img](/media/115.png)

## 7. Description of the Building Blocks
![Img](/media/116.png)

Set **input** or **output** to the specified pin. **input** means input mode,**output** means output mode. Select **input-pullup** can set the input mode for the pin and make it become high level.
![Img](/media/117.png)

Set **high** or **low** to the specified pin. Select **high** means to set high level for the pin. If there is voltage and current, the LED will be on. Select **low** means to set low level for the pin. If there is no voltage and current, the LED will be off.

## 8. Write the Program

① Drag the instruction block ![Img](/media/118.png)in the **Events** module to the script area.
![Img](/media/119.png)

② Drag the instruction block![Img](/media/120.png) in the **Pins** module to the script area and copy it twice. Since the interface of the traffic light module is connected to port 1 on the mainboard (the red light is connected to D3, the yellow light is connected to D5, and the green light is connected to D6), then change the number 0 to 3, 5 and 6 and **input** to **output** respectively.
![Img](/media/121.png)

③ Drag the instruction block![Img](/media/122.png) in the **Pins** module to the script area and copy it twice. Then change the number 0 to 3, 5, and 6 respectively.
![Img](/media/123.png)

④ Complete Program
![Img](/media/124.png)


## 9. Test Result
Click ![Img](/media/125.png) to upload the complete program to the kidsuno mainboard and power up, then the lights on the traffic light module will be on. It seems pretty amazing, right?
![Img](/media/911.png)

## 10. Function: Make the Traffic Lights On and Off
![Img](/media/126.png)

## 11. Description of the the Building Blocks
![Img](/media/127.png)
This is a delay block, and change the number 1 to the delayed time

## 12. Write the Program
①  Write the program according to the knowledge learned before and refer to the last program code.
![Img](/media/128.png)

② Drag the instruction block![Img](/media/127.png) in the **Control** module to the script area. The number 1 can be changed to other numbers. Here, the number 1 is taken as an example.
![Img](/media/129.png)

③ Copy the code string![Img](/media/130.png) once and change **high** to **low**.
![Img](/media/131.png)

④ Complete Program
![Img](/media/131.png)

## 13：Test Result 
Click ![Img](/media/125.png) to upload the complete program to the kidsuno mainboard and power up, then the lights on the traffic light module will go on and then off.
![Img](/media/912.png)![Img](/media/913.png)


## 14. Function of Traffic Lights 
![Img](/media/132.png)

## 15. Flow Chart 
First set the three LED lights to off, then the red light will be on for 5 s then go off, then the yellow light will flash for 3 times then go off, then the green light will be on for 5 s then go off.
![Img](/media/133.png)

## 16. Description of the the Building Blocks
![Img](/media/134.png)
This is a loop statement: do a same thing over and over again.

![Img](/media/135.png)
This is a conditional loop control statement and it will exit the loop  when the number of loops is met. For example, 10 means 10 cycles, and the number 10 can be changed to other numbers.

## 17. Write the Program

① Find the instruction blocks
（1）![Img](/media/136.png)
<br>
（2）![Img](/media/137.png)
<br>
（3）![Img](/media/138.png)
<br>

② Complete Program
![Img](/media/139.png)
![Img](/media/140.png)

## 18.Test Result 
Click ![Img](/media/125.png) to upload the complete program to the kidsuno mainboard and power up, then the red light will be on for 5 s then go off, then the yellow light will flash for 3 times then go off, then the green light will be on for 5 s then go off and continue the cycle.
![Img](/media/914.png)

## 19. Extended Project
![Img](/media/141.png)

The extended sample code is below：
![Img](/media/142.png)





