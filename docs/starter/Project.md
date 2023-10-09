## **Project 1: Blinking**

**1.  Description**

LED blinking is a simple project designed for starters. You only need to install an LED on Arduino board and upload the code on Arduino IDE. 

This project reinforces the learning of Arduino conceptual framework and using methods for starters. 

**2.  Working Principle**

![](./media/led.png)
**LED lighting principle:** 

Generally speaking, limited IO ports of output current may cause enough-less brightness of LED, so NPN triode (Q2) is applied in circuit as a switch.
In this case, the LED will light up if the base(pin 1) of triode is at a high level. On the contrary, LED goes off when the base is at low.

**Triode switch controlling principle:**

To have a clear understanding of its principle, certain knowledge of electronic circuit is required. For details, please consult materials by yourself.
Briefly, LED lights up when the base(pin 1) is at a high level. In the same breath, the collector(pin 3) and emitter(pin 2) are connected, and then VCC passes through a current-limiting resistor to LED and finally to GND, which forms a circuit. On the contrary, LED goes off when the base is at low. In this circumstance, the collector and emitter are disconnected hence the circuit is not a closed loop.

**3.  Wiring Diagram**

![01](media/01.jpg)

**4.  Test Code**

According to previous principles, we can control LED via power levels of pins on the development board.

1.Drag this "when Arduino begin" block in "Events".This is one basic block. Or else, the following code blocks won't execute.

![image-20230324144129788](media/image-20230324144129788.png)

2.Drag a "forever" in "Control" to circulate the execution of the including code blocks. This is another basic block.

![image-20230324144235832](media/image-20230324144235832.png)

3.Drag an "LED output" block in "LED" and set the pin to 3 and output to HIGH.

![image-20230324144552097](media/image-20230324144552097.png)

4.Drag a delay time block in "Control" and set "wait 1 seconds".

![image-20230324144523478](media/image-20230324144523478.png)

5.Set another LED output to LOW at pin 3 as well as "wait 1 seconds".

![image-20230324144721033](media/image-20230324144721033.png)

**Complete Code:**

![img-20230307165550](media/img-20230307165550.png)


**5. Test Result**

After uploading the code and powering on, LED will blink alternatively of on for 1s and off for 1s.

**6. Code Block Description**

1.Code blocks will not execute if there is no "when Arduino begin".

![Img-20230307162920](media/img-20230307162920.png)

2.Code blocks in this "forever" block will execute in a loop. 

![Img](media/img-20230307164251.png)

3.In this block, you can choose a pin to output a HIGH or LOW level. 

![Img](media/img-20230307165305.png)

4.You can type a delay time in the middle blank in the unit of seconds. 

![Img](media/img-20230307164630.png)



## **Project 2：Breathing Light**

**1. Description**
Arduino breathing light utilizes on-board programmable PWM to output analog waveform. After powering on, LED brightness can be adjusted through duty cycle of the waveform to eventually realize a breathing light.
In this way, ambient light can be simulated by changing LED brightness along with time. Also, breathing light can form a colorful mini light show to construct a tranquil and warm environment.

**2. PWM Working Principle**

PWM controls analog output via digital means, which are able to adjust the duty cycle of the wave (a signal circularly shifting between high level and low level).
For Arduino, digital ports of voltage output are LOW and HIGH, which respectively correspond to 0V and 5V.
Generally, we define LOW as 0 and HIGH as 1. Arduino will output 500 signals of 0 or 1 within 1s. If they are 500 "1", 5V will be output. Oppositely, if they are all 0, the output will be 0V. Or if they are 010101010101..., the average output will be 2.5V.
In other words, output ratio of 0 and 1 affects the voltage value. Honestly, it differs from real continuous output, yet the more 0 and 1 signals are output per unit time, the more accurate the control will be.

![](media/img-20230225090854.png)

**3. Wiring Diagram**

![01](media/01-1679396611356-2.jpg)

**4. Test Code**

We adopt "for" statement to increase a variable from 0 to 255, and we define the variable as PWM output (analogWrite(pin, value)). By the way, a delay time may reinforce the control of LED shining time. Next, we use another "for" statement to decrease it from 255 to 0 with also a delay time to control LED dimming process.
As a result, a breathing light is complete.

1.Drag the basic two code blocks.

![image-20230324145038355](media/image-20230324145038355.png)

2.Drag the following block from "Variable Type", and define the name to "item" with an initial assignment "0". Put this block in "forever". 

![image-20230324145311206](media/image-20230324145311206.png)

3.Drag a "repeat" block from "control" and set it to 255 times, which is the maximum value of PWM.

![image-20230324145621946](media/image-20230324145621946.png)

4.Drag a "Change" block from "Variable Type", put "item" as its changed object and set the mode to "++".

![image-20230324145715047](media/image-20230324145715047.png)

5.Drag an "analogWrite" from “LED” and set the LED pin to 3. Then add an "variable" block in it and fill in the blank with "item". 

![image-20230324150352779](media/image-20230324150352779.png)

6.Drag a delay time block from "Control" and set the waiting time to 0.01s = 10ms. 

![image-20230324150616342](media/image-20230324150616342.png)

7.According to previous steps, build another code block with the only difference of variable mode "– –".

![image-20230324150902217.png](media/image-20230324150902217.png)

**Complete Code:**

![Img](media/img-20230307185310.png)

**5. Test Result**

After uploading the code, we can see the LED dims gradually rather than all of a sudden. It "breathes" evenly.
**6. Code Block Explanation**

1.This definition block is used to set variable usable range, variable type , name and its initial value. 

![Img](media/img-20230307190132.png)

2.Repeating times can be assigned in the blank of this repeat block. 

![Img](media/img-20230307190325.png)

3.This block adds one to the variable. Input a variable name in the blank and its value will add one each time the code executing. "++" can be altered to "– –".

![Img](media/img-20230307190714.png)

4.This block suntract one from the variable. Similarly, input a variable name in the blank and its value will reduce one each time the code executing. 

![Img](media/img-20230307192056.png)

5.A certain analog output value and pins can be set in this PWM outptu block. Totally, six pins on Nano board cater for PWM, including pin 3, 5, 6, 9, 10 and 11. Besides, the analog value can be scheduled in the blank. 

![Img](media/img-20230307190828.png)

## **Project 3：SOS Distress Device**

**1. Description**

Arduino SOS device is able to emit distress signals, which coincide with the principle of Morse code. It is convenient for emergencies.

**2. Wiring Diagram**

![01](media/01-1679396626664-4.jpg)

**3. Test Code**

What we should clear firstly is how SOS distress light blinks: LED quickly blinks three times for “S” and slowly blinks three times for “O”.
And then, we control the blinking times and duration via "for" statement and set interval time among letters.

1.Drag the two basic code blocks.

**Letter "S"**

2.Drag a "repeat" block from "Control" and set to 3 times, as "S" only needs to blink for 3 times. 

![image-20230324151732249](media/image-20230324151732249.png)

3.Drag an “LED output” block from "LED" and set the output to HIGH at pin 3. Put a delay block after it and set the its time to 0.15s.

![image-20230324151939418](media/image-20230324151939418.png)

4.Drag another “LED output” block and set the output to LOW at pin 3. Also add a delay block after it but set the waiting time to 0.1s.

![image-20230324152108217](media/image-20230324152108217.png)

**Letter "O"**

5.Refering to previous steps, build the following code block. Modify the HIGH ouput to delay 0.4s and LOW to 0.2s.

![image-20230324152610886.png](media/image-20230324152610886.png)

**Letter "S"**

6.Operate step 2, 3 and 4 again. 

![image-20230324152644605.png](media/image-20230324152644605.png)

7.Add a delay time of 5s to the end, and "SOS" will repeat every 5s. 

**Complete Code:**

![3.png](media/3.png)

**4. Test Result**

After uploading the code, LED respectively blinks for 3 times in the sequence of quick, slow and quick, which forms "S.O.S". It repeates after 5s.


## **Project 4：Traffic Light**

**1. Description**

The traffic light module limits the pedestrian and vehicular thoroughfare. It includes a red, a yellow and a green light, which imply different instructions.
**Red for Stop:** Pedestrians and vehicles stop proceeding.
**Yellow for Caution:** Pedestrians and vehicles are ready for stopping. If the drive is already in process, the speed should be slow.
**Green for Proceed:** Pedestrians and vehicles keep going with the abidance of traffic regulations.

In this project, you can program to control a mini traffic light. For instance, set the duration of each lights and the interval time among them. Besides, you may also add a timer to alter light colors to schedule.

**2. Wiring Diagram**

![02](media/02.jpg)

**3. Test Code**

We simply stimulate the traffic light: green LED lights up for 5s, yellow LED blinks for 3 times, and red LED lights up for 5s. And we set this to loop.
The blinking of yellow LED can utilize the code blocks we have mentioned in project 3. Thus, we now only need to set a lighting time to complete a traffic light.

1.Drag the two basic code blocks.

2.**Green LED lights for 5s:** Drag an “LED output” block from "LED" and set the output to HIGH at pin 4. Place a delay block after it and set the waiting time to 5s. Drag another “LED output” block but set the it to LOW. 

![image-20230522132039969](media/image-20230522132039969.png)

3.**Yellow LED blinks 3 times:** Drag a "repeat" block from "Control" and set it to 3 times. Put an “LED output” block in it and set the output to HIGH at pin 4 followed by a 0.5s delay time. Repeat this step but set the output to LOW, as shown below. 

![image-20230522132052355](media/image-20230522132052355.png)

4.**Red LED lights for 5s:** Do the same as step to, but set the output pin to 2. 

![image-20230522132107369](media/image-20230522132107369.png)

**Complete Code:**

![image-20230522132138034](media/image-20230522132138034.png)

**4. Test Result**

After uploading the code, green LED will light up for 5s, yellow LED will blink for 3 times, and red LED will light up for also 5s, in circulation.


## **Project 5：Rainbow Ambient Light**

**1. Description**

Arduino 2812RGB LED is a programable colorful dreamy light, whose lighting color, brightness and rhythm are adjustable.
This rainbow ambient light can used as a dynamic decoration at will. Or you may control it to "dance with music".

Importantly, it can be improved as an alarm. Its built-in sensor detects the ambient surroundings to warn users by changing lighting colors, brightness and rhythm.

**2. Working Principle**

![image-20230314194251127.png](media/image-20230314194251127.png)
**Working Principle:** 

The data protocol adopts communication mode of single-line RTZ code.
After powering on and pixel resetting, DIN terminal receives data from the controller. The firstly arriving 24bit data will be extracted by the first pixel and be sent to the inner data register. And remaining data will be amplified by an amplification circuit and be transmitted through DOUT port to the next cascaded pixel. After being transmitted through pixels, the signal decreases 24bit each time.
Besides, the automatic amplification and transmitting technology offer unlimited number of cascade from signal transmitting, yet it is limited by transmitting speed.

**3.Wiring Diagram**

![03](media/03.jpg)

**4. Test Code**

To begin with, let's learn how to set 2812 RGB colors! 

1.Drag the two basic code blocks.

2.Drag a “RGB LED” block from “RGB LED” and set the pin to 8 and the number of LED to 6.

![image-20230324155834546](media/image-20230324155834546.png)

3.Drag an “LED brightness” block from “RGB LED” and set the pin to 8 and the brightness to 20. We don't recommend you to set it particularly bright, as it is bad for your eyes when debugging.

![image-20230324155850899](media/image-20230324155850899.png)

4.Drag a "clear all LEDs" block and set the pin to 8. 

![image-20230324155902287](media/image-20230324155902287.png)

5.Drag six "show color" blocks and set pins to all 8. Orderly, define the RGB as: 0 to 0, 1 to 1, 2 to 2, 3 to 3, 4 to 4, 5 to 5, which respectively correspond to red, green, blue, purple and white. 

![image-20230324155920173.png](media/image-20230324155920173.png)

**Complete Code:**

![5-1](media/5-1.png)

**5. Test Result**

After uploading code, wiring up and powering on, the LED will light up in different colors as the scheduled sequence.

![image-20230331150517106](media/image-20230331150517106.png)

**6. Expansion Code**

In this expansion project, let's model a mini light show!

1.Nest three "repeat" block and add a "variable +" in each, as follows. 

![image-20230324161017237.png](media/image-20230324161017237.png)

2.Put the above three variables in "RGB" block so that these color values are controlled. 

![image-20230324161152823](media/image-20230324161152823.png)

3.Put the "RGB" block in a "show color" block to display colors. And define a variable item to control the showing LED.

![image-20230324161606134](media/image-20230324161606134.png)

**Complete Code:**

![5-2](media/5-2.png)

**7. Code Block Explanation**

1.Set the number of 2812 RGB. One development pin can control multiple 2812 RGB LEDs, so we need to set the number in advance and select the connecting pin. 

![image-20230318082805508](media/image-20230318082805508.png)

2.Set the brightness of 2812 RGB. Select the pin firstly and input the brightness value within 0-255, in which 255 is the brightest.

![image-20230318082634565](media/image-20230318082634565.png)

3.Turn off all 2812 RGB. This block clears all LED by selecting their common affecting pin. 

![image-20230318082831101](media/image-20230318082831101.png)

4.Control the display of 2812 RGB. We can fill the blanks to control the lighting LED and its color after selecting the pin. For instance, "0 to 0" means only the first LED lights up. After uploading the code, the first LED will turn on in the set color.

**NOTE:** The two blanks also can be filled with variables, so that a light show is able to be formed. 

![image-20230318083119425](media/image-20230318083119425.png)

5.Set the color of 2812 RGB. The displaying color can be modulated by the value in red, green and blue(R, G and B). Although we have covered how to set the showing color in Point 4, it is a direct choice which does not facilitate the control of code. Thus, we add this block in the color settings of 2812 RGB.

![image-20230318083847459](media/image-20230318083847459.png)

6.Set a gradient color of 2812 RGB. We firstly choose the pin and lighting LED(0-5 means all six LED), and then set the color value from 0 to 360. Variables also can be added. 

![image-20230318090458878](media/image-20230318090458878.png)

7.Set the distance. The blank should be input a number to indicate the shift distance. In this example code, it means to shift 1 unit in each loop. 

![image-20230318090735123](media/image-20230318090735123.png)

8.Set the rotation distance. We set the pin and input the rotation distance in the blank .

![image-20230318091401332](media/image-20230318091401332.png)

9.We set the pin firstly and define the pixel to "0 to 5". The max value is 360. We light 2812 RGB up through setting the current value. When the current value equals the maximum, all six LED light up.

![image-20230318090825899](media/image-20230318090825899.png)

## **Project 6：Water Flow Light**

**1. Description**

This simple water flow light project guides you in electronic packaging. In this project, we control LED to shift the color in a specified speed.

**2. Wiring Diagram**

![04](media/04-1679645817641-7.jpg)

**3. Test Code**

A water flow light consists of a stream of LED lighting from left to right and vice versa.

1.Drag the two basic code blocks.

2.Drag two "LED output" block from "LED" and set the output to LOW at pin 6 and HIGH at pin 3. And set a 0.2s delay. 

![image-20230324162317521.png](media/image-20230324162317521.png)

3.Drag another two "LED output" block and set the output to LOW at pin 3 and HIGH at pin 4. Also, set a 0.2s delay. 

![image-20230324162405342.png](media/image-20230324162405342.png)

4.Similarly, set the output to LOW at pin 4 and HIGH at pin 5 with a delay time of 0.2s.

![image-20230324162437947.png](media/image-20230324162437947.png)

5.Again, set the output to LOW at pin 5 and HIGH at pin 6 with a delay time of 0.2s. 

![image-20230324162511769](media/image-20230324162511769.png)

**Complete Code:**

![6](media/6-1679444142675-2.png)

**4. Test Result**

After uploading code and powering on, the stream of LED light up from left to right and vice versa in a loop.

## **Project 7：Buzzer**
**1. Description**
An active buzzer can function as an alarm, a reminder or an entertaining device. It provides reliable voice warning for you.
What's more, it stimulates various sounds and features high controllability, so that you can experience an interesting and real experiment.

**2. Working Principle**

![image-20230317144940800.png](media/image-20230317144940800.png)

**Working Principle:** 

An active buzzer integrates a multi-vibrator, so it makes sound only by a DC voltage.
Pin 1 of the buzzer connects to VCC and pin 2 is controlled by a triode. When a high level is provided for the base (pin 1) of the triode, its collector (pin 3) and emitter (pin 2) link to GND, and then the buzzer emits sound.
Oppositely, if we offer a low level to the base, the rest of pins will be disconnected, so the buzzer will remain quiet.

**3. Wiring diagram**

![05](media/05.jpg)

**4. Test Code**

If the development board outputs a high level, the buzzer will emit sound. If it outputs a low level, the buzzer will stop ringing.
Thus, its code is similar to light up an LED.

1.Drag the two basic code blocks.

2.Set the “Buzzer output” block from “Buzzer” to HIGH at pin 3 with a delay of 1s.

![image-20230324164439805](media/image-20230324164439805.png)

3.Set another “Buzzer output” to LOW at pin 3 also with a delay of 1s. 

![image-20230324164455404](media/image-20230324164455404.png)

**Complete Code:**

![Img](media/img-20230308081530-1679038470910-1-1679444168044-4.png)

**5. Test Result**

After uploading code and powering on, the buzzer emits sound for 1s and stays quiet for another 1s, in circulation.

**6. Code Block Explanation**

Buzzer output block. We firstly define the pin to 3 and then set the output to "HIGH" or "LOW". The buzzer will beep when at HIGH, while it will be quiet at LOW.
![Img](media/img-20230308091645-1679038470911-2-1679444195290-6.png)

## **Project 8：Music Performer**

**1. Description**
This project realizes a music player with an amplifier on the development board. This speaker can not only play simple songs, but also perform music made by yourself. Thus, you can program other interesting codes in the project to accomplish splendid learning outcomes.

**2. Working Principle**

![img-20230225081927.png](media/img-20230225081927.png)
**Working Principle:** 

The electrical signal is input from pin 1 of RP1 (adjusts signal intensity, which is also the sound volume).
After coupling in C4 and passing R5, the signal reaches IN- pin of 8002B, in which it is operationally amplified and output to BEE1 speaker.

**3. Wiring Diagram**

![06](media/06.jpg)

**4. Test Code**

![image-20230522152408267](media/image-20230522152408267.png)

**5. Test Result**

After uploading code and powering on, the amplifier circularly plays music tones with corresponding frequency: Do, Re, Mi, Fa, So, La, Si.

**6. Expansion Code**

For a little more complicated, let's make it to play a birthday song. We have already added some songs in library so you can directly drag these song blocks from "Music". 

**Code:**

![image-20230522152818744](media/image-20230522152818744.png)

**7. Code Block Explanation**

1.Set the tone frequency. After setting the pin, we can select the frequency to compose music. However, do not forget a delay time. 

![image-20230318104144376](media/image-20230318104144376.png)

2.It is also used to set the tone frequency. What differs is that it has already included a duration so that we can omitted a delay block. 

![image-20230318104617301](media/image-20230318104617301.png)

3.Play music. For convenience, we have integrated six songs in our code blocks. Therefore, you only need to select the pin to play different songs. 

![image-20230318104854681](media/image-20230318104854681.png)

4.Quit the play. Just select the relevant pin to stop the playing song.

![image-20230318105011897](media/image-20230318105011897.png)

## **Project 9：Digital Tube Display**

**1. Description**
This display module, whose display range includes 0 ~ 9 and simple letters, consists of four digital tubes with seven LED on each and can be used as a counter or a clock.

Moreover, multiple functions can be realized by connecting their pins to the development board, such as timekeeping and some game storing.

**2. Working Principle**

![img-20230225082040.png](media/img-20230225082040.png)

**Working Principle:** TM1650 utilizes IIC protocol and adopts two bus lines (SDA and SCL).

The code is provided in our blocks, and the digital tube will display numbers via this code. 

**3. Wiring Diagram**

![07](media/07.jpg)

**4. Test Code**

To show numbers on the display, you only need to drag a "TM 1650 display" block from "Digital tube" and set the number string to 9999.

![9-1](media/9-1-1679444429891-10-1679444542378-12-1679444550514-14.png)

**5. Test Result**

After wiring up and uploading code, the digital tube display shows "9999", as shown below.

![image-20230321161936665.png](media/image-20230321161936665.png)

**6. Expansion Code**

Let's have some difficult operations. Rather than static numbers, we handle it to show some dynamic ones. The following code manipulates the tubes to display 1~9999 via a "for" loop.

1.Drag the two basic code blocks.

2.Drag a "variable Type" block from "Variables". Set the type to int and name to item, and assign 0 as its initial value.

![image-20230325084909953](media/image-20230325084909953.png)

3.Drag a "repeat" block from "Control" and set to 9999 times. 

![image-20230325085129944](media/image-20230325085129944.png)

4.Drag a "variable mode" from "Variables", define its name to item and set the mode to "++".

5.Drag a "TM 1650 display" block from "Digital tube" and replace the string value with variable item. Add a delay time of 0.5s after it.  

![image-20230325085529957.png](media/image-20230325085529957.png)

6.Add a "set variable" block after the "repeat". Set item variable by 0. Otherwise, the item value will be out of display range after 9999 loops. 

![image-20230325085754198](media/image-20230325085754198.png)

**Complete Code:** 

![9-2](media/9-2.png)

**7. Code Block Explanation**

1.Set the display string. Directly type numbers or letters you want to display in the blank. 

![image-20230318110740509](media/image-20230318110740509-1679444741274-16-1679444774697-20-1679444776814-22-1679444778343-24-1679444780601-26.png)

2.Set the ON or OFF of this TM 1650 digital tube. Each tube can be controlled separately. 

![image-20230318111231604](media/image-20230318111231604.png)

3.It is able to clear the display or used as a master switch to turn on or turn off the digital tube. 

![image-20230318111521907](media/image-20230318111521907-1679444748652-18-1679444818234-28.png)


## **Project 10：Dot Matrix Display**

**1. Description**
This module consists of a 8x8 LED dot matrix with one control pin for each row as well as each column to adjust the brightness of LED.
Connecting with Arduino board, the brightness of LED is controlled via programs. In this way, simple characters and figures are able to be displayed. It also can be applied in game machines or screens.

**2. Working Principle**

![img-20230225082512](media/img-20230225082512.png)

**Working Principle:** 

MAX7219 is an IC with SPI communication and controls 8x8 dot matrix. The MAX7219 SPI communication has integrated in our libraries and you can recall directly.

**3. Wring Diagram**

![08](media/08.jpg)

**4. Test Code**

1.Drag the two basic code blocks.

2.Drag a "init matrix display" from “Matrix” and set CS to 10. DIN and CLK are fixed pin respectively to 11 and 13.

![image-20230325090233965](media/image-20230325090233965.png)

3.Drag a "set brightness" block and set it to 3. Don't set an extreme high value when debugging. It may hurt your eyes. 

![image-20230325090343317](media/image-20230325090343317.png)

4.Drag a "image" block and choose heart icon.

![image-20230325090650972](media/image-20230325090650972.png)

5.Lastly do remember to add a "refresh" block at the end. 

![image-20230325090527357](media/image-20230325090527357.png)

**Complete Code:**

![10](media/10.png)

**5. Test Result**

After wiring up and uploading code, a heart will be displayed on the dot matrix, as shown below.

![20230420085055](./media/20230420085055.png)

**6. Code Block Explanation**

1.Set the CS pin. In the code, DIN is fixed to 11 and SLK to 13, yet CS pin is optional. For convient wiring, we select 10 (Attention: pin 12 is not available for CS).

![image-20230318115524580](media/image-20230318115524580.png)

2.Draw pixels. This code block will light up or turn off pixels on the dot matrix by axis x and y, with red for on and black for off. 

![image-20230318120021624](media/image-20230318120021624.png)

3.Draw line. Locate the line by two group of coordinate points, also with red for on and black for off. 

![image-20230318120145212](media/image-20230318120145212.png)

4.Show characters. We have add character libraries so you only need to type a letter(only one) to display it on the dot matrix. Besides, it must be used cooperatively with a "rotation 180°" block. 

![image-20230318130321293](media/image-20230318130321293.png)

5.Show numbers. Similarly, you only need to type a number(only one) to display it on the dot matrix, and it also must be used cooperatively with a "rotation 180°" block. 

![image-20230318130346709](media/image-20230318130346709.png)

6.Show scrolling character strings. Collocating a "rotation 180°" block, the specified scrolling strings will be displayed after setting its speed. 

![image-20230318130405179](media/image-20230318130405179.png)

7.Display image. For convenience, we have already integrated some emotion icons which can be selected directly. 

![image-20230318130421059](media/image-20230318130421059.png)

8.Display fill colors. You may set to black (LED goes off) or red(LED lights up).

![image-20230318130444192](media/image-20230318130444192.png)

9.Refresh the display. The dot matrix must be refreshed if it displays something. Or else, an errer may occur.

![image-20230318130500471](media/image-20230318130500471.png)

10.Set the brightness. You can lower the brightness when debugging to avoid offending to your eyes. 

![image-20230318133821875](media/image-20230318133821875.png)

11.Set rotation angles. For high compatibility with more code, some data and icons need a rotation with the avoidence of inverted display.  That is why a "rotation 180°" block is necessary in codes. 

![image-20230318133843286](media/image-20230318133843286.png)



## **Project 11: LCD**

**1. Description**
Arduino I2C 1602 LCD is a commonly-used auxiliary device for MCU development board to connect with external sensors and modules. It features a 16-bit wide character and 2-line LCD screen, whose brightness is adjustable.

This programable module is convenient for data editing, displaying and managing. Besides, it can display not only characters and figures but sensors value, like temperature, humidity or pressure value.

As a result of its usability, the display is wildly applied in many fields, including smart home, industrial monitoring system, robot control and automatics' electronics.

**2. Working Principle**

![](./media/lcd.png)

**Working Principle:** 

It is the same as IIC communication principle. Underlying functions have packaged in libraries so that you can recall them directly.

If you are interested in these, you may have a further look of underlying driving principles.

**3. Wiring Diagram**

![09](media/09.jpg)

**4. Test Code**

1.Drag the two basic code blocks.

2.Drag “init LCD” block from “LCD” and set the I2C address to 0x27.

![image-20230325093620843](media/image-20230325093620843.png)

3.Drag the "LCD back light" block and set it to ON. Characters are not easy to read if there is no back light.

![image-20230325093708827](media/image-20230325093708827.png)

4.Drag a "LCD cursor position" block and set x to 3 and y to 0. Add an "LCD print" block and type “keyestudio” in the blank. 

![image-20230325093952628](media/image-20230325093952628.png)

5.Again, drag another "LCD cursor position" and set x to 2 and y to 1. Add an "LCD print" and type “Hello,world!” in the blank. 

![image-20230325094043434](media/image-20230325094043434.png)

**Complete Code:**

![Img](media/img-20230308101037.png)

**5. Test Result**

After wiring up and uploading code, turn on the LCD, and "Hello, world!" and "keyestudio!" will displayed on the LCD.

If the characters are unclear, please fix the backlight potentiometer by the small slotted screwdriver(included in this kit). Connect an external power supply if necessary.

![image-20230325091056039.png](media/image-20230325091056039.png)

**6. Code Block Explanation**

1.Set the IIC communication address. In this project, the address of LCD 1602 is 0x27.

![Img](media/img-20230308101228.png)

2.Control the LCD back light. The displayed characters will be seen much clearly if the back light is on. 

![Img](media/img-20230308101438.png)

3.Set the cursor position. It will provide an accurate position through axis x and y. Possible values are X: 0-15 and Y: 0-1.

![Img](media/img-20230308101746.png)

4.Print characters on LCD. The blank can be filled with characters or variables, which is convenient for displaying the values from sensors and modules. 

![Img](media/img-20230308102036.png)

5.Blink the cursor at the display position. By default, the cursor is in inactive. 

![Img](media/img-20230308102320-16805113851661.png)


## **Project 12：Servo**

**1. Description**
This servo features high performance and high precision with a maximum rotation angle of 180°. Weighting only 9g with a tiny size, it is perfectly suitable for any mini devices in any occasion.

What's more, it enjoys short startup time, low noise and strong stability.

**2. Working Principle**

**Angle Scale:** 180° (commonly 360°, 180° and 90°)

**Drive Voltage:** 3.3V / 5V

**Pin:** Three-wire

![wps1](media/wps1.png)

**GND:** Grounded, in brown

**VCC:** power supply pin connecting to +5v/3.3V, in red

**S:** Signal pin controlling PWM signal, in orange

![](./media/wps2(1)(1)-1684483122626-1.png)

**Control Principle**:
The rotation angle is controlled via duty cycle of PWM.

Theoretically, standard PWM cycle is 20ms(50Hz), so pulse width should distribute within 1ms~2ms. However, the actual pulse width reaches 0.5ms~2.5ms, corresponding to 0°～180°.

Pay attention that, for the same signal, the rotation angle vary from servo brands.

**3. Wiring Diagram**

![](./media/34(1).jpg)

**4. Test Code**

1.Drag the two basic blocks and put a "variable" block between them. Set the variable type to int, name to angle, and assign 0 as its initial value. 

![image-20230325102408697.png](media/image-20230325102408697.png)

2.**Servo gradually rotates from 0° to 180°:** 

Add a repeat block and set to 180 repeat times (180 angles). Drag a "change variable" and a "servo" block and put them in the repeat one. Name the variable "angle" and select the mode "++". Set Servo PIN to 9 and degree to the named variable. Don't forget to delay 15s.

![image-20230325103811524.png](media/image-20230325103811524.png)

3.**Servo gradually rotates from 180° to 0°:** Repeat step 2, but set the variable mode to "- -".

![image-20230325104016623.png](media/image-20230325104016623.png)

**Complete Code:**

![Img](media/img-20230308103125.png)



**5. Test Result**

After wiring up and uploading code, the servo starts to rotate from 0° to 180° and vice versa.

**6. Code Block Explanation**

1.Set the values of Servo. Servo pin and rotation angle can be controlled by setting parameters on this block.

![Img](media/img-20230308103522.png)

2.Read the current degree of the Servo. 

![Img](media/img-20230308103633.png)



## **Project 13：Mini Lamp**

**1. Description**
In this project, we control a lamp by Arduino UNO and a button. When we press the button, the state of the lamp will shift (ON or OFF).

**2. Working Principle**

![](./media/img-20230225082310-1684554788483-3.png)

**Working Principle:** 

When the button is released, a voltage VCC passing through R29 provides a high level for S terminal. 

When it is pressed, pin 1 and 3, pin 2 and 4 are connected and voltage on S1 arrives GND as a low level. At this moment, R29 avoids a short circuit between VCC and GND.

**3. Wiring Diagram**

![14](media/14.jpg)

**4. Test Code**

1.Add two basic blocks.

2.Drag a "baud rate" from “Serial” and set it to 9600. 

![image-20230325132829253](media/image-20230325132829253.png)

3.Then drag a "print" block from “Serial”, type “Key status:” in the blank and set it to "no-warp".

![image-20230325133041424](media/image-20230325133041424.png)

4.Drag another “Serial print” block  from “Serial” and set the mode to "warp". Add a "state value of button" from “Button” and set the interface to 8.

![image-20230325133328150](media/image-20230325133328150.png)

**Complete Code:**



![13-1](media/13-1.png)

**5. Test Result**

After wiring up and uploading code, open the serial monitor and set the baud rate to 9600. 
When we press the button, serial port prints "Key status: 0"; When we release the button, serial port prints "Key status: 1".

![image-20230318140232396](media/image-20230318140232396.png)

**6. Expansion Knowledge**

We then will control the LED via a button.

**Flow Diagram:**

![image-20230322114827986.png](media/image-20230322114827986.png)

**Wiring Diagram:**

![10](media/10.jpg)

**Code:**

1.Drag two basic blocks. 

2.Drag a "if&else" block from “Control”. Add a "button pin" block from “Button” after "if" and set its interface to 8. 

3.Put an "LED output" block under "if" and set the output to HIGH, and put another under "else" and set to LOW. LED pins are both at 3.

![image-20230325134557767.png](media/image-20230325134557767.png)

**Complete Code:**

![13-2](media/13-2.png)

**7. Code Block Explanation**

1.Determine whether the button is pressed. If it is, this block expresses true; If not,it is false.

![image-20230318160105218](media/image-20230318160105218.png)

2.Read the current button value. When the button is pressed, the value is 1. Or else, it is 0.

![image-20230318160315012](media/image-20230318160315012.png)

3.If the condition in the hexagon is true, "if" block will be executed. Otherwise, the program runs "else" according to block.

![image-20230318160426073](media/image-20230318160426073.png)

4.Set the baud rate. Please guarantee the serial baud rate fit the counterpart of serial monitor, or it won't print anything. The commonly used baud rate are 9600 and 115200, and here we set to 9600.

![image-20230325132829253](media/image-20230325132829253.png)

5.Print characters on serial monitor. The printed words are what you type in the blank. Besides, three print modes are included: warp, no-warp and HEX (hexadecimal). 

![image-20230325133733586](media/image-20230325133733586.png)



## **Project 14：Counter**

**1. Description**
Arduino 4-bit digital tube counter can record numbers within 0~9999. It features display speed and counting mode adjustment as well as resetting function. 

This module is wildly applied in real-time counter (such as button-press and DC motor rotation count), gaming and experiment equipment.

**2.Flow Diagram**

![](./media/1679466016942-28.png)

**3. Wiring Diagram**

![11](./media/11.jpg)

**4. Test Code**

1.Drag the two basic blocks and put a "variable" block between them. Set the variable type to int and name to item. Assign 0 as its initial value. 

![image-20230325142143536](./media/image-20230325142143536.png)

2.Drag an "if" block from “Control” (it executes only when its condition is satisfied). Put a “Button pressed” block from “Button” to the condition box(the hexagon one) and set the interface to 5. Drag a "variable mode" block and put it after "then", and define it as "item" and set the mode to "++".

![image-20230325142757764](./media/image-20230325142757764.png)

3.Repeat step 2, but set the interface to 4 and mode to "– –".

![image-20230325142853404](./media/image-20230325142853404.png)

4.Drag another "if" block from “Control” and define its condition that "interface 3 button was be pushed?". Put a variable setting block after "then" and set the "variable by 0".

![image-20230325142950442](./media/image-20230325142950442.png)

5.Drag one more "if" block from “Control”. Find the "＞" block in “Operators” and fill the left blank with "variable item" and the right with "9999". Also, put a variable setting block after "then" and set the "variable by 0".

![image-20230325143340106](./media/image-20230325143340106.png)

6.Drag a "TM1650 display" block from "Digital tube" and set the displayed string to "variable item" block. Finally, don't forget to add a 0.2s delay. 



**Complete Code:**

![](./media/14-1679725104178-13.png)

**5. Test Result**

After wiring up and uploading code, press green button to add 1, yellow to minus 1, and red to reset. Press the button and hold, and the displayed value will keep adding or subtracting.

**6. Code Block Explanation**

![image-20230325144251951](./media/image-20230325144251951.png)

A greater-than block is used for judgment between two values. These two blanks can be replaced with either numbers or variables. 


## **Project 15：Responder**

**1. Description**
This programable responder inputs and receives signals through Arduino development board and a group of buttons, and it judges the correctness of answers by an LED.

Responders exercise students' reaction ability and draw their attention to questions. If the answer is correct, the respondent obtains a lot scores. 

Moreover, it simplifies teachers' manipulation of question-grabbers and cuts answer clutters. It may even stimulate students' interests in learning. 

**2. Flow Diagram**

![](./media/1679464174206-17.png)

**3. Wiring Diagram**

![12-1679549372415-76](./media/12-1679549372415-76.jpg)

**4. Test Code**

1.Drag the two basic blocks and put a "variable" block between them. Set the variable type to int and name to item with an initial assignment of 0.

2.Add an "LED output" block, define its pin to 10 and set the output to HIGH.

3.Drag an "if" block and add the condition "interface 6 button was be pushed?".

![image-20230325145141695](./media/image-20230325145141695.png)

4.Add a variable setting and four LED output blocks under "then". Among them, we name the variable "item" with an assignment of "0", and set all outputs to LOW respectively at pin 10, 9, 8 and 7 (The responder works only when all LED light out). Likewise, don't forget a 0.2s delay. 

![image-20230325145434234](./media/image-20230325145434234.png)

5.Add a "repeat until" block and set the "until" to "item = 1", as shown below. When item = 1, exit the loop. 

![image-20230325145555120](./media/image-20230325145555120.png)

6.Drag another "if" block and set the condition "Interface 3 button was be pushed?". Add an "LED output" block under "then" and set the output to HIGH at pin 7. And add a "set item variable by 1" to exit this condition block. 

![image-20230325150040415](./media/image-20230325150040415.png)

7.Repeat step 6, but set interface to 4 and LED pin to 8. 

![image-20230325150223129](./media/image-20230325150223129.png)

8.Operate step 6 again, but set interface to 5 and LED pin to 9. 

![image-20230325150238979](./media/image-20230325150238979.png)

**Complete Code:**

![15](media/15.png)

**5. Test Result**

Wire up and upload the code. The answers of respondents are only valid when the red LED is off(red button is pressed). 

When someone presses his/her button(yellow, green or blue), the appropriate LED as well as the red counterpart lights up. By now, rest of LED cannot turn on when pressing buttons. The responding action can be performed only when the red button is pressed again.

**6. Code Block Explanation**

An equal block is used to judge whether the two values are equal. 

![image-20230325150347252](./media/image-20230325150347252.png)



## **Project 16：Time-bomb**

**1. Description**
This project will give you an opportunity experience an interesting timebomb game.  

In this project, the dot matrix represents your timebomb, while the digital tube displays remaining time. Buttons can not only control the bomb but also set its time. You may set a countdown to control this bomb, and it explodes when the countdown is over. Beyond that, a buzzer is adopted to alarm. 

Anyhow, by programming on multiple sensors, your comprehensive capability of logic thinking can be enhanced. 

**2. Flow Diagram**

![](./media/161616.png)

**3. Wiring Diagram**

![13-1679549618528-80](./media/13-1679549618528-80.jpg)

**4. Test Code**

1.Drag that two basic blocks.

2.Add an "init matrix display" block from "Matrix" and set the pin CS to 10. What follows it are a "brightness" block with its value of 7 and a "variable" block (set variable type to int and name to item, assign 0 as its initial value).

![image-20230325160028190](./media/image-20230325160028190.png)

3.In "Matrix", drag a "fill color" block and select "black"(i.e. all LED go off to clear previous display). Add a "display image" to define a new icon, and here we choose a smile face. Then, put a refresh block to renew the display. 

![image-20230325161001760](./media/image-20230325161001760.png)

4.Drag an"if" block and fill the condition box with "interface 3 button was be pushed?". Add a "variable mode" block after "then" and set its name to item and mode to "++".

![image-20230325161015187](./media/image-20230325161015187.png)

5.Repeat the operation in step 4, but set the interface to 4 and the mode to "- -".

![image-20230325161029844](./media/image-20230325161029844.png)

6.Drag an "if" block to judge whether pin 5 is pushed. In this "if", we add a repeat block and set its stopping condition that the variable "item" equals 0 (item = 0). 

7.In the "repeat until" loop, put a "variable mode" and set "item" to "- -", as shown below. Drag a "TM1650 display" block from "Digital tube" and define the showing string as "variable item" block. Then add a "buzzer output" block and set output to HIGH at pin 2 followed by a 0.5s delay. Re-operate the last procedure but set the output to LOW. 

![image-20230325161740603](./media/image-20230325161740603.png)

8.Program another loop code and define the quit condition as "interface 6 button was be pushed?". The following executions are in this loop. Put a "TM1650 display" block and define the showing string as "variable item" block.  Then repeat step 3 but here we set the image to a crying face. 

![image-20230325162223793](./media/image-20230325162223793.png)

9.Drag an "if then" block and fill the blank with a greater-than condition: item ＞ 9999. Add a statement "set item variable by 0" in this condition block. 

![image-20230325162514307](./media/image-20230325162514307.png)

10.Drag a "TM1650 display" from "Digital tube" and define the showing string as "variable item". For the same, don't forget to delay 0.2s.

![image-20230325162611261](./media/image-20230325162611261.png)

**Complete Code:**

![16](media/16-1679281663238-2.png)

**5. Test Result**

After wiring up and uploading code, press blue button to add time, green to reduce and red to reset. Press yellow button for counting down. When it is over, the bomb explodes. 



## **Project 17：Invasion Alarm**

**1. Description**
This simple invasion alarm detects invaders in houses or small offices and warns the host to take measures in time. 

In this project, the sensor monitors a certain area. Some device on Arduino board will trigger LED to light up and buzzer to beep for caution if a movement is detected in that zone.

Virtually, this module features practicability, simpleness and low costs. With the exception of home and office, it also applies to factories, warehouses and markets, which, to a large extent, protects property security.

**2. Working Principle**

![por](./media/por.png)

**Working Principle:** 

Human body(37°C) always emits infrared ray with a wavelength of 10μm or so, which approximates to that of the sensor detected. On this account, this module is able to detects human beings movement. If there is, PIR sensor outputs a high level about 3s . If not, it outputs a low level . 

**3. Wiring Diagram**

![15](./media/15.jpg)

**4. Test Code**

1. Add the two basic blocks and drag a "baud rate" block from “Serial” between them. Set the serial baud rate to 9600.

![image-20230325162826626](./media/image-20230325162826626.png)

2.Add an "if&else" block. Put a "read PIR motion sensor" block in the hexagon box and set the interface to 4, thus it will determine whether there is a human motion. Add two "serial print" blocks after "then" and "else" and set both modes to "warp". If the condition is satisfied, print “Someone Invaded”. Or else, print “No one”. 

3.Last but not least, delay 1s to limit the printing speed. 

![image-20230325163433871](./media/image-20230325163433871.png)

**Complete Code:**

![17-1](media/17-1.png)

**5. Test Result**

After wiring up and upload code, open serial monitor to set baud rate to 9600. When the sensor detects movement, the serial port prints "Someone Invaded", or else, it prints “No One”.

![image-20230320110614054](media/image-20230320110614054.png)

**6.Expansion Code**

In this expansion project, let's make an invasion alarm. When the PIR sensor detects human, LED lights out and the buzzer emits sound. By contrast, LED goes off and the buzzer stays quiet.

**Flow Diagram:**

![172172](./media/172172.png)

**Wiring Diagram:**

![16](./media/16.jpg)

**Code:**

![17-2](media/17-2.png)

**7. Code Block Explanation**

![image-20230327102737820](./media/image-20230327102737820.png)

When PIR senses human motions, it outputs a high level. Therefore, we can tell whether there is a movement by reading the development board pin connected to this sensor. 



## **Project 18：Beating Heart**

**1. Description**
In this project, a beating heart will be presented via an Arduino board, 8X8 dot matrix display, circuit board and other electronic components.
By programming, you can control the beating frequency, heart dimension and its brightness. 

**2. Wiring Diagram**

![08-1679384669847-15](media/08-1679384669847-15.jpg)

**3. Test Code**

1.Drag the two basic blocks. 

2.Initialize the dot matrix display. Set the CS pin to 10 and its brightness to 3. Put these two executions between the basic blocks.

The following executions are all in "forever" block.

3.Clear the display. Control the display to draw lines and establish coordinates system and its origin as the following. Then, refresh the display to show the smaller heart with a delay of 1s. 

![image-20230327090049227.png](media/image-20230327090049227.png)

![image-20230516100427648](media/image-20230516100427648.png)

4.Repeat step 3 but draw lines as the picture below to show a bigger heart. 

![1.png](media/1.png)

![image-20230516100502637](media/image-20230516100502637.png)

**Complete Code:**

![18.png](media/18.png)

**4. Test Result**

After wiring up and upload code, the two sizes of hearts are displayed alternately. 

![image-20230323164511913](./media/image-20230323164511913.png)![image-20230323164436275](./media/image-20230323164436275.png)



## **Project 19：Dimming Light**

**1. Description**
The dimming lamp adjusts the brightness of LED via a potentiometer and an Arduino controller. For potentiometer, the brightness is influenced by different resistance, which can be read and adjusted by connecting the meter pins to digital/analog pins on board. 

What's more, this system is applied to control voltage/current of other devices, such as fans, bulbs and heaters. 

**2. Working Principle**

![img-20230225082629-1679443973070-13](./media/img-20230225082629-1679443973070-13.png)

**Working Principle:** 

Essentially, potentiometer is a resistor with changeable resistance. According to Ohm's law(U=IR), the resistance affects the voltage.

In this project, the maximum resistance is 10K. The Nano board will equally divide the voltage of 5V into 1024 parts (5/1024=0.0048828125). The analog voltage is obtained by multiplying the read value and 0.004882815.

**NOTE:** 
If you power the module by only USB, the working voltage may not reach 5V, which causes a smaller analog value. So please connect an external DC 7-12V power supply if necessary. 

**3. Wiring Diagram**

![19](./media/19.jpg)

**4. Test Code**

The analog value can be read:

1.Drag the two basic blocks. Put the baud rate setting block between them and set to 9600.

2.Add a "serial print" block in "forever" loop, and select "warp" as the print mode.

3.Drag a "read the value" from “pot” to the serial print, and set the pin to A0. 

![19-1](./media/19-1.png)

**5. Test Result**

After wiring up and uploading code, open serial monitor to set baud rate to 9600, and the analog value will be displayed within the range of 0-1023.

![image-20230327094257859](./media/image-20230327094257859.png)

**6. Expansion Code**

We control the brightness of LED via a potentiometer. 

As we know, it is influenced by PWM. However, the range of analog value is 0-1023 while that of PWM is 0-255. Hence, we need a "**map(value, fromLow, fromHigh, toLow, toHigh)**" function to adjust the range.

**Wiring Diagram:**

![18-1679534891950-13](./media/18-1679534891950-13.jpg)

1.Drag the two basic blocks.

2.Add a variable block and set it to local. Select "int" as its type and name it as "pot". 

![image-20230327095102942](./media/image-20230327095102942.png)

3.Drag a "map" function from “Data” and put it to the assignment position. Set the value of "map" to "read the value of pot A0", whose range is from (0,1023) to (0,255).

![image-20230327095138185](./media/image-20230327095138185.png)

4.Finally add an "LED analogWrite" block. Set the pin to 3 and analog value to the variable "pot".

![image-20230327095209123](./media/image-20230327095209123.png)

**Complete Code:**

![Img](./media/img-20230308105508.png)



**7. Code Block Explanation**

1.**map** function. The analog value range can be converted from 0-1023 to 0-255. We have known that LED brightness is controlled via PWM, yet the range of PWM is 0-255 while that of analog value is 0-1023. Thus, the later need a conversion through this f.

![Img](./media/img-20230308105611.png)

2.Read the analog value of potentiometer by setting its pin. 

![Img](./media/img-20230308110840.png)



## **Project 20：Light Pillar**

**1. Description**
The resistance(less than 1KΩ) of the photoresistor varies from the light, hence it can control the brightness of the dot matrix. When controlling, we connect this resistor with an analog pin on the board to monitor the change of resistance. In this way, the light automatically controls the brightness of the display. 

Besides, it is widely applied to our daily life. For instance, a curtain automatically opens or closes according to the outer light intensity. 

**2. Working Principle**

![img-20230225082629-1679443973070-13-1679881978135-5](./media/img-20230225082629-1679443973070-13-1679881978135-5.png)

**Working Principle:** 

When it is totally in dark, the resistance equals 0.2MΩ, and the voltage at signal terminal (point 2) approaches to 0V. The stronger the light is , the smaller the resistance and voltage will be.

**3. Wiring Diagram**

![19](./media/19-1679882037715-7.jpg)

**4. Test Code**

The photoresistor value can be read:

1.Drag the two basic blocks. Put the "baud rate" block between them and set it to 9600.

2.Add a "serial print" block in "forever" loop with the mode "warp".

3.Drag a "read the value" block from “Light” to the "serial print" block, and set the pin to A0.

![20-1](./media/20-1.png)

**5. Test Result**

After wiring up and uploading code, open serial monitor to set baud rate to 9600, the analog value will be displayed, within the range of 0-1023. 

![image-20230327100102059](./media/image-20230327100102059.png)

**6. Expansion Code**

In this expansion project, we use this resistor to sensing the ambient light intensity. The middle two columns are included in this experiment to represent light intensity. The lighter it is, the more the lighting LED will be. This forms a "light pillar".

**Wiring Diagram**

![23](./media/23.jpg)

1.Drag the two basic blocks. 

2.In "Matrix", initialize the dot matrix display and set pin CS to 10. Add a "brightness setting" block and assign to 2.

![image-20230327102411972](./media/image-20230327102411972.png)

3.Drag a "variable" block. Set its range to Local, type to int and name to light.

![image-20230327102526180](./media/image-20230327102526180.png)

4.Assign a map function to the variable. Add "read the value of light A0" from "Light" to the value of map function, whose range is from (0,1023) to (0,7).

![image-20230327102514010](./media/image-20230327102514010.png)

5.Find the following blocks in "Matrix". Clear the display first, and then draw lines on the display at dots (x0:3  y0:0, x1:3  y1: variable light) and (x0:4  y0:0, x1:4  y1: variable light). Finally refresh the display of matrix.

![image-20230327102541765](./media/image-20230327102541765.png)

**Complete Code:**

![20-2](./media/20-2.png)

**7. Code Block Explanation**

![image-20230327103201572](./media/image-20230327103201572.png)

Read the analog value of photoresistor by setting the pin. 




## **Project 21：Voice Control Light**

**1. Description**
Voice control light module uses sound to control the brightness of LED. It can connect to other sensors, for example, microphone converts sound to changing voltage signal to be received by Arduino to control the LED on and off.

**2. Working Principle**

![image-20230315150410153.png](media/image-20230315150410153.png)
**Working Principle:** 

When detecting a sound, the electret-film in microphone vibrates, which changes the capacitance and generates a subtle change of voltage. 
Next, we make use of LM386 chip to build a proper circuit to amplify the detected sound up to 200 times, which can be adjusted by a potentiometer. Rotate it clockwise to enlarge the times. 

**3. Wiring Diagram**

![21](./media/21.jpg)

**4. Test Code**

Find the "read the value" block in “Sound”, and print the read sound in the serial port. Construct blocks as follows. Pay attention that do not add a delay when using sound sensor.

![21-1](./media/21-1.png)

**5. Test Result**

After wiring up and uploading code, open serial monitor to set baud rate to 9600, the analog value will be displayed.

![image-20230330113837135](./media/image-20230330113837135.png)

**6. Expansion Code**

The commonly seen corridor light is a kind of voice control light. Meanwhile, it also includes a photoresistor. 

Differed from that, here we establish a model that an LED is only affected by voice. When the analog volume exceeds 100, LED lights up for 2S and then goes off.

**Flow Diagram:**

![](./media/1679540516529-57.png)

**Wiring Diagram:**

![22-1679616502464-1](./media/22-1679616502464-1.jpg)

1.Drag two basic blocks and put a variable block between them. Set the type to int and name to item. Assign its initial value to 0.

![image-20230327120341139](./media/image-20230327120341139.png)

2.Add a variable block and fill the name with "item", set the value to "read the value of sound A0".

![image-20230327120519481](./media/image-20230327120519481.png)

3.Drag an "if&else" block, and fill the hexagon with a greater-than block (set to: item＞100). If the condition is satisfied, LED outputs a HIGH level at pin 3 with a delay of 2s; or else, it outputs a LOW level at the same pin without a delay. 

![image-20230327120829584](./media/image-20230327120829584.png)

**Complete Code:**

![Img](./media/img-20230313100054.png)



**7. Code Block Explanation**

![Img](./media/img-20230313095907.png)

Read the value of sound by setting the related pin.



## **Project 22：Noisemeter**

**1. Description**

Arduino noisemeter detects and shows noise in an intriguing way. It embodies the voice signal to a sequence of dots, which are converted into patterns to be displayed on the dot matrix. 
**2. Wiring Diagram**

![23-1679536215604-22](./media/23-1679536215604-22.jpg)

**3. Test Code**

1.Drag the basic blocks and initialize the display. Set the pin CS to 10 and brightness to 2. Then add a variable block and select int and name it as "item" with an initial assignment of 0.

2.Add a variable block and name it as "item". Adopt a map function to convert the read sound value range from 0-1023 to 0-7, yet the hypothesis maximum value of sound is 450.

![image-20230330115920251](./media/image-20230330115920251.png)

3.Clear the display. 

4.Program a condition. If the variable item is greater than -1, the dot matrix displays (x0:0  y0:0 x1:1  y1:0) in color of red.

![image-20230330120747953](./media/image-20230330120747953.png)

5.Repeat step 4, but the judgment is whether item is greater than 0. If it is, dots at (x0:1  y0:0  x1:1  y1:1) will light up. By that analogy, build code blocks referring to the following coordinates. 

6.Finally, refresh the display. 

**Reference Coordinates:**

![image-20230331091954165](./media/image-20230331091954165.png)

**Complete Code:**

![22](./media/22.png)

**4. Test Result**

After wiring up and uploading code, the noise level view is displayed on dot matrix, as shown below.

![image-20230324092636680.png](media/image-20230324092636680.png) ![image-20230324092653930.png](media/image-20230324092653930.png)       


## **Project 23：Smart Cup**

**1. Description**
In this project, we mainly adopt the Arduino development board to create a programmable smart cup, which reveals the temperature of inner liquid through a RGB indicator. 

By setting threshold values, the indicator will light up in different brightness levels. When the thresholdlevel is exceeded, it will get brighter. Or else, it gets darker. In this way, you will have a better control of drinking water, preventing from being overheated or overcooled.

**2. Working Diagram**

![img-20230225082723](./media/img-20230225082723.png)

**Working Diagram:**

Related settings in DHT11 is provided by manufacturers, so you only need to orderly read and process data according to its sequence chart. 

Besides, the relevant codes are packaged in our libraries, which is convenient for you to only set pins and read values. 

**3. Wiring Diagram**

![24](./media/24.jpg)

**4. Test Code**

![23.1](media/23.1.png)

**5. Test Result**

After wiring up and uploading code, click ![image-20230320142348367](media/image-20230320142348367.png) to open serial monitor to set baud rate to 9600, and the temperature and humidity value will be displayed.

![image-20230320142447120](media/image-20230320142447120.png)

**6. Expansion Code**

In this expansion experiment, we will make a smart cup which can show liquid temperature. 

We divide 100 into four parts with an LED representing for each: 
Red LED: 75~100°C
Yellow LED: 50~75°C
Green LED: 25~50°C
Blue LED: 0~25°C

**Flow Diagram:**

![](./media/1679903142983-34.png)

**Wiring Diagram:**

![25](./media/25.jpg)

**Code:**

![32.2](media/32.2.png)



**7. Code Block Explanation**

1.In this code block, the marked number can be filled in the blank so that multiple temperature and humidity sensors can be connected. After setting the pin and mode, the value can be read. In this project, we set the mode to DHT11.

![Img](media/img-20230313092101-1679293570318-9.png)

2.Read the humidity value directly. 

![Img](media/img-20230313093350-1679293570319-10.png)

3.Read the temperature value directly in an optional unit of °C or °F.

![Img](media/img-20230313093458-1679293570319-11.png)



## **Project 24：Meteorological Station**

**1. Description**

This mini meteorological station records ambient temperature and humidity value via Arduino board and related sensors. 
Beyond that, for a more comfortable surrounding, it also automatically adjust these two values according to environmental parameters.

**2. Wiring Diagram**

![26](./media/26.jpg)

**3. Test Code**

![Img](./media/img-20230313091951.png)

**4. Test Result**

After wiring up and uploading code, LCD display will directly discover the ambient humidity and temperature value.

![image-20230324100529239](./media/image-20230324100529239.png)


## **Project 25：Ultrasonic Diastimeter**

**1. Description**
This ultrasonic diastimeter measures distance of obstacles by emitting sound waves and then receiving the echo. That is to say, the distance is not an immediate value, but an observed one by a theoretical calculation of time difference between emitter and receiver. 

Except distance measurement, ultrasonic is able to detect objects' form and existence, set up automatic doors and estimate flow velocity and pressure. 

What's more, this module supports cooperative works with computers. As a result, the measured value can be transmitted to computers via Arduino board. 

In daily life, it is widely used for numerous equipment (such as motors, servo and LED) as well as systems (like automatic navigation, controlling and security monitoring systems).

**2. Working Principle**

![image-20230330160129461](./media/image-20230330160129461.png)

**Working principle:** 

As we all know, ultrasonic is a kind of inaudible sound wave signal with high frequency. Similar to a bat, this module measures distance of obstacles by calculating the time difference between wave-emitting and echo-receiving.

**Maximum distance:** 3M

**Minimum distance:** 5cm

**Detection angle:** ≤15°

**3. Wiring Diagram**

![27](./media/27.jpg)

**4. Test Code**

In "forever" block, construct two "serial print" blocks and drag a "read distance" block from “Ultrasonic”. Set trig pin to 12 and echo pin to 13 both in cm. Do not forget a delay of 0.5s. The complete code is shown below.

![25-1](media/25-1.png)

**5. Test Result**

After wiring up and uploading code, open serial monitor to set baud rate to 9600, and the serial port starts to print the distance value. 

![image-20230330161659860](./media/image-20230330161659860.png)

**6. Expansion Code**

In this expansion project, let's make a diastimeter. 

We display characters on LCD 1602. Program to show "Keyestudio" at (3,0) and “distance:” at (0,1) followed by the distance value at (9,1). 

When the value is smaller than 100(or 10), a residue of the third(or the second) bit still exists. Therefore, an "if" judgment is necessary to determine a certain condition.

**Wiring Diagram:**

![28](./media/28.jpg)

**Code:**

1.Drag the two basic blocks.

2.In "LCD", initialize the LCD. Drag an “LCD print” block and add character string “Keyestudio” (It also can be put out of "forever" block as this display is fixed). Add a "variable" block and set type to int and name to "distance" with an initial assignment of 0.

![image-20230330163254633](./media/image-20230330163254633.png)

3.Assign the read distance value to the variable "distance". Set the LCD to print “Distance：” and followed by the distance value (and we need calculate the front displayed characters in advance to set a cursor followed them).

![image-20230330163849498](./media/image-20230330163849498.png)

4.Build a "clear display residue" block when the number of displayed bits decrease. We firstly adopts a condition to judge whether the distance is smaller than 100(or 10). If it is, a space will be printed at the residue of the third (or the second) bit to clear previous display. 

5.Lastly, don't forget to add a delay of 0.5s. 

![image-20230330164331718-1684840146427-1](./media/image-20230330164331718-1684840146427-1.png)

**Complete Code:**

![25-2](media/25-2.png)

**7. Code Block Explanation**

![image-20230330162231242](./media/image-20230330162231242.png)

Read the distance after setting the trig pin and echo pin. The unit of displayed value is optional (cm or inch).


## **Project 26：Human Body Piano**

**1. Description**
The analog piano includes a development board and an ultrasonic sensor. It plays different tones by detecting the position of your fingers. Thus, this module is able to stimulate a piano to perform music and songs. 

**2. Flow Diagram**

![262626](./media/262626.png)

**3. Wiring Diagram**

![29](./media/29.jpg)

**4. Test Code**

Assign the distance value to item, and the played tones vary from distance. Seven tones are included: Do，Re，Mi，Fa，So，La，Si.

![26](./media/26.png)

**5. Test Result**

Wire up and upload code. 
Play Do when the distance is smaller than 10. 
Play Re when the distance is within 10~20. 
Play Mi when the distance is within 20~30. 
Play Fa when the distance is within 30~40. 
Play So when the distance is within 40~50. 
Play La when the distance is within 50~60. 
Play Si when the distance is within 60~70. 

## **Project 27：Intelligent Parking**

**1. Description**
This intelligent parking system detects and optimizes parking position via ultrasonic sensor. With this system, wrong parking is avoided to a large extent. 

Firstly, you need to install the sensor around the car-park. And then it will detect the distance between the car and its edges and send the information to the development board. After integration, the distance value will be revealed by the lines on the dot matrix display.

**2. Flow Diagram**

![](./media/1679560585424-83.png)

**3. Wiring Diagram**

![30](./media/30.jpg)

**4. Test Code**

Assign the detected distance value to a variable, and judge whether it is greater than the set threshold value. If it is, corresponding lines on the dot matrix light up. In this way, a distance can be revealed by lighting lines. 

**Reference Coordinates:**

![image-20230331092241919](./media/image-20230331092241919.png)

**Complete Code:**

![27](./media/27-1680228886481-10.png)

**5. Test Result**

After wiring up and uploading code, lines displays on the dot matrix. When the detected distance is shorter than 50cm, there are fewer lines.

![image-20230324103259033](./media/image-20230324103259033.png)![image-20230324103353015](./media/image-20230324103353015.png)

## **Project 28：Intelligent Gate**

**1. Description**
The intelligent gate integrates MCU and ultrasonic sensor. It measures the distance of car to open or close gate handler. 

When a certain distance is reached, MCU receives the signal from the sensor and estimates the distance via the signal intensity. If the car is approaching or leaving, MCU will open or close the gate via a servo.

**2. Flow Diagram**

![282828](./media/282828.png)

**3. Wiring Diagram**

![](./media/35-1682295754025-2.jpg)

**4. Test Code**

Define a variable "distance" with the assignment of detected distance value by the ultrasonic module. 

Next, Compare the distance value with 30cm. If it is smaller than 30cm, the servo will rotate to 180° and stands for 5s. Otherwise, the servo returns to 0°.

![](./media/28-1682213749309-5.png)

**5. Test Result**

After wiring up and uploading code, the servo will turn to 180° and stay for 5s if the detected distance is shorter than 30cm. On the contrary, the servo will return to 0°.


## **Project 29：IR Remote Control**
**1. Description**
This module uses IR to remotely control LED, which greatly simplifies the ON and OFF of LED. Now that the control is realized by IR signals, there is no need to worry about considerable circuits. 

**2. Working Principle**

![img-20230225082859](./media/img-20230225082859.png)

**Working principle:** 

In actual communication, signals usually carries a wide spectrum, and a lot of energy is distributed at a low frequency band. We called it baseband signal, which is not suitable for direct transmission in channels. 

For a convenient transmission, a high anti-disturbance capability and an effective utilization of Broadband, and signals, before transmitting, always need to be modulated to a frequency which is suitable for channels and noise characteristics. This is what we called signal modulation. 

At the receiver of the communication system, signals are usually demodulated to regain the initial baseband ones. In this project, we often use a carrier of about 38K in modulation. 

An IR remote control system is mainly split into modulation, emitting and receiving. It sends data through modulating, i.e., an "**and**" operation between data and carriers with a certain frequency. In this way, the emitting efficiency is enhanced while power dissipation is lowered. 

Generally, the frequency of carrier modulation is within 30khz~60khz, with 38kHz more often. The duty cycle of the square wave is 1/3, as shown below, which is decided by the 455kHz crystal oscillator on the emitting end. 

An Integer frequency division is essential for crystal oscillator at this end, and the frequency coefficient usually evaluates 12. Therefore, 455kHz÷12≈37.9kHz≈38kHz. 

**38KH carrier (complete) emitting diagram:**![img-20230225083510](./media/img-20230225083510.jpg)

**Carrier frequency:** 38KHz

**Wave length:**  940nm

**Receiving angle:** 90°

**Control distance:** 6M

**Schematic diagram of remote control buttons:**

![221](./media/221.jpg)

**3. Wiring Diagram**

![31](./media/31.jpg)

**4. Test Code**

1.Drag the two basic blocks.

2.Find and drag the "IR remote init" block from “IR Remote” and set its pin to 3. Add a "baud rate" block from "serial" and set to 9600.

![image-20230331104445825](./media/image-20230331104445825.png)

3.Drag an "if" block and fill its condition with "Received data". Only when the IR module receives data, code blocks in "if" execute.

![image-20230331104631171](./media/image-20230331104631171.png)

4.Drag another "if" block and set its condition to "Read the data ＞ 0". Only when this condition is satisfied, serial port starts to print data. 

This sensor works so fast that the code may run twice or more when you are pressing control buttons. However, the second time of a same command will send out a value of 0, so a greater-than block is necessary for the avoidance of duplication. 

![image-20230331105216727](./media/image-20230331105216727.png)

5.Add a "serial print" block after "then". Set to print the read data from "IR remote" module in the mode of "warp".

![image-20230331114809806](./media/image-20230331114809806.png)

6.In the end, do not forget to refresh data after a full execution. Otherwise, next receiving will be invalid.

![image-20230331114824593](./media/image-20230331114824593.png)

**Complete Code:**

![29-1](./media/29-1-1680247790101-55.png)

**5. Test Result**

After wiring up and uploading code, open the serial monitor and set the baud rate to 9600. Press the button on the remote control unit, and you will see the value in hexadecimal.

![image-20230331114725348](./media/image-20230331114725348.png)

**6. Expansion Code**

In this expansion code, we will make a light controlled by an IR remote switch. Press OK to light up the LED and press it again to turn it off. 

To realize this repeatable operation, the variable "item" is essential in the whole code. For the first time, item = 0 so codes in "else" run to assign 1 as its new value. For the second time when item = 1, however, "if" block executes to reassign to 0, alternatively.

**Wiring Diagram:**

![32](./media/32.jpg)

**Code:**


![](./media/29-2-1682213866846-7.png)



**7. Code Block Explanation**

1.Initialize the IR remote module after setting its receiving pin.

![image-20230331131708045](./media/image-20230331131708045.png)

2.Judge whether the sensor has received data. If it is, related code blocks will run.

![image-20230331131847778](./media/image-20230331131847778.png)

3.Read the received data from IR remote control.

![image-20230331131908873](./media/image-20230331131908873.png)

4.Refresh the received data after each complete receiving execution. Or else, the next receiving will is invalid.

![image-20230331131926563](./media/image-20230331131926563.png)



## **Project 30：Smart Home**

**1. Description**
In this technology era, we are all familiar with smart home. It is a system that can control electric appliance via simple buttons. 

In this project, we stimulate a smart home remotely controlled by infrared sensor. With Arduino MCU as its core, it realizes intelligent control of light, air conditioner, TV and security monitors. 

All in all, this smart home system is convenient and easy to use.

**2. Flow Diagram**

![1680245250541-45](./media/1680245250541-45.png)

**3. Wiring Diagram**

![33-1679536931415-32](./media/33-1679536931415-32.jpg)

**4. Test Code**

With the IR remote control, this smart home reveals various sensor values on LCD,including the value of temperature and humidity sensor, sound sensor, photoresistor, potentiometer and ultrasonic sensor. 

![30](./media/30-1682214027154-9.png)

**5. Test Result**

After wiring up and uploading code, press buttons and observe the displayed contents on LCD.

Press button 1 to display temperature value.

![image-20230324121110679](./media/image-20230324121110679.png)

Press button 2 to display humidity value.

![image-20230324131438306](./media/image-20230324131438306.png)

Press button 3 to display distance value.

![image-20230324133243486](./media/image-20230324133243486.png)

Press button 4 to display luminance value.

![image-20230324135039872](./media/image-20230324135039872.png)

Press button 5 to display the analog sound volume. 

![image-20230324135105983](./media/image-20230324135105983.png)

Press button 6 to display the analog potentiometer value. 

![image-20230324135133788](./media/image-20230324135133788.png)

Press button OK to clear the display. 

![image-20230324121051127](./media/image-20230324121051127.png)



**6. Code Block Explanation**

The blocks are so many that we adopt "Make a Block" function. By doing this, numerous blocks are packaged and can be directly recalled, which vastly simplifies the whole program. 

Click “My Block” to make a self-defined block, and you may build your own code blocks. 

![image-20230331145236585](./media/image-20230331145236585.png)

