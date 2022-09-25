# Tank Level Sensor Project
## Why?
We use a highly concentrated form of chlorine called AWSB-7000 that is constantly pumped into the water system to treat bacteria growth. It needs to be refilled by a contracted chemical company prior to being fully depleted. A wooden stick with 1" markings was used to measure the height of the liquid in inches, then a multiplier was used to convert to gallons. This required an operator to open the tank lid, exposing their eyes and lungs to the highly concentrated chemical gas, then dipping the wooden stick into the tank, exposing their skin and clothing to the liquid form.

Using a <a href="https://www.amazon.com/s?k=JSN-SR04T&crid=2UX1JDB96KFTE&sprefix=jsn-sr04t%2Caps%2C75&ref=nb_sb_noss_1"> JSN-SR04</a> ultrasonic sensor and an <a href="https://www.amazon.com/s?k=arduino+nano&crid=2SKIY0QD65UP0&sprefix=arduino+nan%2Caps%2C81&ref=nb_sb_noss_2"> Arduino Nano</a>, I came up with a solution to monitor the tank level remotely with a <a href="https://www.amazon.com/s?k=4x20+lcd+i2c&sprefix=4x+20+lcd+%2Caps%2C80&ref=nb_sb_ss_ts-doa-p_1_10">20x4 LCD display</a> utilizing the I2C communication protocol. On the front of the controller below the display, there is an illuminated momentary push button that provides a visual indicator when the controller is in a low level state, a low level but acknowledged state, and a high level state. The level is calculated by getting the sensor data from the ultrasonic sensor, which is used to find the distance from the sensor to the top of the liquid. A calculation is then made to get the remaining liquid level, and then converted into gallons. After the calculation is made, it is stored into an array of size 9


AWSB-7000 Tank            |  Controller Display
:-------------------------:|:-------------------------:
![](https://github.com/griffincorriher/Tank-Level-Sensor/blob/main/pictures/308432110_472071698183540_2184842942179239873_n.jpg) | ![](https://github.com/griffincorriher/Tank-Level-Sensor/blob/main/pictures/308571166_460609469177128_8450469272247332403_n.jpg)

LCD connection            |  Arduino Nano + Ultrasonic board
:-------------------------:|:-------------------------:
![](https://raw.githubusercontent.com/griffincorriher/Tank-Level-Sensor/main/pictures/308309851_756642738744793_202947544131946022_n.jpg) | ![](https://github.com/griffincorriher/Tank-Level-Sensor/blob/main/pictures/309009767_1196586654225176_6489248929801947862_n.jpg)


<img src="https://github.com/griffincorriher/Tank-Level-Sensor/blob/main/pictures/308571166_460609469177128_8450469272247332403_n.jpg" title="LCD" width="400">


