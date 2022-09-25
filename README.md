# Toxic chemical level sensor
## Why build this?
We use a highly concentrated form of chlorine called AWSB-7000 that is constantly pumped into the water system to treat bacteria growth. It needs to be refilled by a contracted chemical company prior to being fully depleted. A wooden stick with 1" markings was used to measure the height of the liquid in inches, then a multiplier was used to convert to gallons. This required an operator to open the tank lid, exposing their eyes and lungs to the highly concentrated chemical gas, then dipping the wooden stick into the tank, exposing their skin and clothing to the liquid form.


## Solution
Using a <a href="https://www.amazon.com/s?k=JSN-SR04T&crid=2UX1JDB96KFTE&sprefix=jsn-sr04t%2Caps%2C75&ref=nb_sb_noss_1"> JSN-SR04</a> ultrasonic sensor and an <a href="https://www.amazon.com/s?k=arduino+nano&crid=2SKIY0QD65UP0&sprefix=arduino+nan%2Caps%2C81&ref=nb_sb_noss_2"> Arduino Nano</a>, I came up with a solution to monitor the tank level remotely with a <a href="https://www.amazon.com/s?k=4x20+lcd+i2c&sprefix=4x+20+lcd+%2Caps%2C80&ref=nb_sb_ss_ts-doa-p_1_10">20x4 LCD display</a> utilizing the I2C communication protocol. The ultrasonic sensor is mounted inside of a fill cap using a self-designed 3d printed friction fit adapter, which allows the sensor to sit inside the tank. On the front of the controller below the display, there is an illuminated momentary push button that provides a visual indicator when the controller is in a low level state, a low level but acknowledged state, and a high level state. The level is calculated by getting the sensor data from the ultrasonic sensor, which is used to find the distance from the sensor to the top of the liquid. A calculation is then made to get the remaining liquid level in inches, and then converted into gallons. After the calculation is made, it is stored into an array of size 9 and a function is used to find the running median. This is done because the distance of the sensor to the tank wall is so small that the signal waves reflect and produce irratic low/high values. 


AWSB-7000 Tank            |  Controller Display
:-------------------------:|:-------------------------:
![](https://github.com/griffincorriher/Tank-Level-Sensor/blob/main/pictures/308432110_472071698183540_2184842942179239873_n.jpg) | ![](https://github.com/griffincorriher/Tank-Level-Sensor/blob/main/pictures/308571166_460609469177128_8450469272247332403_n.jpg)

LCD connection            |  Arduino Nano + Ultrasonic board
:-------------------------:|:-------------------------:
![](https://raw.githubusercontent.com/griffincorriher/Tank-Level-Sensor/main/pictures/308309851_756642738744793_202947544131946022_n.jpg) | ![](https://github.com/griffincorriher/Tank-Level-Sensor/blob/main/pictures/309009767_1196586654225176_6489248929801947862_n.jpg)



## Issues
- As mentioned above, the placement of the ultrasonic sensor is not ideal, but it is placed in the only nondestructive location (3d printed adapter mounted inside extra cap). If possible, it should be placed in the center so that the sensor waves are able to more accurately read the liquid level.
- The ultrasonic sensor has a working range of 25cm-4M. An issue arises if the tank is filled too high, then sensor is out of range and does not read properly. I have countered this with displaying a message saying that the level is out of range. Once the level drops and the level is in range, the display and median filter calculations start.
- If the tank level is too low, the ultrasonic sensor will give irratic results because of the distance from the tank walls. Since the level is lower, the beam of the sensor is now wider causing it to reflect off of the tank. This could be fixed with the sensor being moved closer to the center.

## Conclusion
This has been used for the past two years without any issues, and has saved many man-hours by reducing how often the tank has to be opened up and manually checked, as well as reduced the potential harm to employees.

## Skills used
- C/C++/<a href="https://www.arduino.cc/reference/en/?_gl=1*116vz4k*_ga*MTI0MDgzODE2NS4xNjYxNjYwNTYy*_ga_NEXN8H46L5*MTY2NDA4ODY5OC4zLjEuMTY2NDA4ODcyNC4wLjAuMA">Arduino language</a>
- Hardware/firmware integration
- 3D modeling using <a href="https://www.autodesk.com/products/fusion-360/overview"> Fusion 360 </a>
- 3D printing
