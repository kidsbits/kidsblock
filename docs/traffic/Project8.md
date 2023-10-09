# Project 08：Intelligent Integrated Traffic System

![Img](media/811.png)

## 1. Introduction
We have learned a host of projects before, can we put them together to make an integrated traffic system？Maybe you can't wait to do it，let’s get started!

The following are the tools we need.

## 2. Components
|![Img](media/KidsunoMainboard.png)|![Img](media/TrafficLightModule.png)|![Img](media/ActiveBuzzer.png)|![Img](media/Photoresistor.png)|![Img](media/WhiteLED.png)|
| :--: | :--: | :--: | :--: |  :--: |
|Kidsuno Mainboard×1|Traffic Light Module×1|Active Buzzer×1|Photoresistor×1|White LED×1|
|![Img](media/ObstacleAvoidanceSensor.png)|![Img](media/UltrasonicAdapter.png)|![Img](media/UltrasonicSensor.png)|![Img](media/8×8DotMatrixDisplay.png)|![Img](media/270°Servo.png)|
|Obstacle Avoidance Sensor×1|Ultrasonic Adapter×1|Ultrasonic Sensor×1|8×8 Dot Matrix Display×1|270°Servo×1|
|![Img](media/ConnectionWire.png)|![Img](media/ConnectionWire.png)|![Img](media/USBCable.png)|![Img](media/IntegratedTrafficSystem.png) |
|20cm Connection Wire×4|30cm Connection Wire×3|USB Cable×1|Integrated Traffic System×1 |


## 3. Function: Make An Integrated Traffic System
![Img](media/812.png)


## 4. Installation Steps 
Please refer to the following link：https://www.dropbox.com/scl/fo/whacdlki5y44kevau03qa/h?dl=0&rlkey=ogbigsw7lxv8zhkvr1oqhlkmz

## 5. Wiring Diagram
![Img](media/813.png)
|Module|Kidsuno Mainboard|Module|Kidsuno Mainboard|
| :--: | :--: | :--: | :--: |
|Traffic Lights|Port 1(Red light→D3,Yellow light→D5,Green light→D6)|Active Buzzer|Port 6(D4)|
|Servo|Brown wire→G,Red wire→V,Yellow wire→D13|Obstacle Avoidance Sensor|Port 7(D8)|
|8×8 Dot Matrix|Port(5V, SDA, SCL, GND）|Photoresistor|Port 3(A3)|
|LED Module|Port 4(D2)|Ultrasonic Adapter Board|Port 9(Trig→D10, Echo→D11)|

<br>

| Ultrasonic Sensor | Ultrasonic Adapter |
| :--: | :--: |
| Vcc | VCC |
| Trig | Trig |
| Echo | Echo |
| Gnd | GND |

## 6. Add the Servo, Ultrasonic Sensor and 8*8 Dot Matrix Instruction Module
![Img](media/814.png)
<br>
![Img](media/815.png)
**Extension** Instruction 

<br>

![Img](media/816.png)
Add **Servo** Module

![Img](media/817.png)
Add **Ultrasonic** Sensor

![Img](media/818.png)
Add **Matrix 8*8 IIC** Display

![Img](media/819.png)

## 7. Flow Chart
![Img](media/820.png)


## 8. Write the Program
![Img](media/821.png)

## 9. Test Result
Click![Img](media/822.png) to upload the complete program to the kidsuno mainboard and power up. Then the effect of the intelligent integrate traffic system will appear.
![Img](media/project08.png)

