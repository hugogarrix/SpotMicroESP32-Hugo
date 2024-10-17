# SpotMicroESP32

My take on a SpotMicro, based on the 3D models and wiring diagram of Michael Kubina. This is still a Work-in-Progress!

You can find the 3D-printing parts on Thingiverse as well: https://www.thingiverse.com/thing:4559827/files

- Join the Discord-Channel for this remix: https://discord.gg/s8F6xHGk9Y (#spotmicro-esp32)

This Project currently lacks the whole programming/software part. Luckily Maarten Weyn already made the inverse kinematics work and wrote also an Smartphone App for simple Control of this Robot via BLE. I advice to take a look into his Repository as well, as this currently my preferred codebase:
https://github.com/maartenweyn/SpotMicro_ESP32

An walking gait implementation and voice-commanding was achieved by Guna R. from the slacks #spotmicro-esp32 channel, whis is build upon Maartens software (see Repo above). You definitly have to take a look there as well - but it seems the repo is incomplete and missing the app:
https://github.com/cholan2100/ceasar

Look also at the GitLab pages for the general SpomicroAI community, where you can find different models and resources: https://gitlab.com/custom_robots/spotmicroai

![SpotMicroESP32](https://github.com/hugogarrix/SpotMicroESP32-Hugo/blob/master/spotmicroESP32.jpg)

## Note of thanks
I want to thank Deok-yeon Kim (KDY0523) for his beautyful and well thought out design of the SpotMicro, without whom my derivate would not have been possible. You can find his original Design here on Thingiverse: https://www.thingiverse.com/thing:3445283

Him sharing the files with an open licence, made it possible to let it grow a community around it. This is why i want to reference to them as well - the SpotMicroAI Community: https://spotmicroai.readthedocs.io/en/latest/

## Preface
This is a work-in-progress, with rather loose milestones.

For 2024 the goals are;
- xx

For 2025 the goals are;
- xx

This repository is currently just my hobby and as such, it will have its own pace. This being said, i am still happy about any questions, collaborations, suggestions, ideas, forks and what else comes to your mind. I want you to participate, because i think there are a lot of things, that you could dig into.

## Sections

* [3D-printed Partlist](https://github.com/hugogarrix/SpotMicroESP32-Hugo/blob/master/parts/SpotMicroESP32_parts_v1_0_0/)
* [Bill of Materials](https://github.com/hugogarrix/SpotMicroESP32-Hugo/#bill-of-material)
* [Assembly Guide](https://github.com/hugogarrix/SpotMicroESP32-Hugo/blob/master/assembly/)
* [Electronics](https://github.com/hugogarrix/SpotMicroESP32-Hugo/blob/master/electronics/)
* [Programming](https://github.com/hugogarrix/SpotMicroESP32-Hugo/blob/master/code/)
* [Inverse Kinematics](https://github.com/hugogarrix/SpotMicroESP32-Hugo/blob/master/kinematics/)

## Bill of Material
The following Section will describe in detail the different parts needed for your own SpotMicroESP32 build, with at least some rough estimate of the price.

### 3D-Printing
To build your own SpotMicroESP32 you will need to print a lot parts. For an overview of the 3D printed parts needed, please visit the [3D-printed Partlist](https://github.com/hugogarrix/SpotMicroESP32-Hugo/blob/master/parts/SpotMicroESP32_parts_v1_0_0/). It might be necessary to remix some of the templates to suit your needs, when chosing other electronic components than those listet here.

### Electronics
The SpotMicroESP32 is still a Work-in-Progress and as such the BOM might change as well. There are still some parts missing and some others are not tested yet - those status will be marked as such. I will give a rough price estimate, which may or may not work for you and might be out of date at some point.

| part or module | number | short description | status | estimated price | 
|----------------|--------|-------------------|--------|:-------------------------|
| ESP32-DevKitC 							|  1x | the core MCU for the build with WIFI + BLE capabilities. 											| tested			| 7€		|
| ESP32-CAM									|  1x | Tested with the ESP32-Module with OV2640 Camera (version 2). There are also cameras with a version 1 OV2640, where the sensor is in landscape orientation and not in portrait. Also the flexcable seems to be some millimeters shorter than the one from Version 2. You can distinguish them by the imprint on the flexcable, stating TY-OV2640-V2.0. Both OV2640 Cameras should work in theory, as the part is designed to fit both models. Definetly dont go with the one with an fisheye-lens or other variations - the field of view would be hindered and most likely the lens would not fit through the hole anyway. 																		| tested	| 10€		|
| FT232RL USB-TTL-Adapter					|  1x | USB-to-Serial Adapter for ESP32-CAM flashing														| tested			| 2€		|
| DS3218MG Servo 			| 12x | 20Kg servos with metal gears and ball bearings. Much less play and also very strong. | tested	| 15€-20€ each 	|
| FSH6S Servohorn 							| 12x | servohorn used for this build (should be already shipped with your servos) otherwie use model from 3D parts 							| tested 			| n.n. 		|
| Servocable Extension						|  4x | extending the servocables of the lower legs about 10cm to 15cm 										| tested			| 10€		|
| 625ZZ Ball Bearing 						|  8x | miniature ball bearing without a flange 															| tested 			| 1€ each 	|
| WS2812b 12 LED Ring (50mm outer diameter) |  1x | Neopixel-Clone-Ring with an outer diameter of 50mm used to signal status/mood						| tested            | 6€        |
| 0.96" OLED I2C Display					|  1x | small OLED screen with SSD1306 IC for status informations											| tested			| 4€		|
| HC-SR04 Ultrasonic Sensor					|  2x | ultrasonic sensor module for distance measuring														| tested			| 3€ each	|
| GY-521 Gyroscope and Accelerometer		|  1x | a module to measure accelaration and spatial orientation, which can be extented with magnetometers  | tested			| 3€		|
| PCA9685 16Channel 12Bit PWM Board			|  1x | PWM driver board used for your servos and LEDs, which can power your parts from an external source	| tested			| 5€		|
| HW-482 / KY-019 5V 10A Relais				|  1x | relais module to cut the power to your servos completely											| tested			| 3€		|
| 19mm Push Button with LED					|  1x | illuminated latching pushbutton 																	| tested			| 10€		|
| Micro-USB to DIP Adapter					|  2x | USB-Ports used for extending the USB-Ports of the ESP32 DevKitC and ESP32-CAM (TTL-Adapter)			| tested			| 2€		|
| or SZBK07 DC-DC 20A Stepdown Converter  	|  1x | even bigger step-down converter to lower your LiPo 2S voltage to 6,5V | tested		    | 12€		|
| LM2596 DC-DC or similar Stepdown Module	|  1x | small step-down converter to lower your LiPo 2S voltage 5V for ESP32's VIN and Modules 				| tested			| 2€ each	|
| ACS712 30A current sensor module			|  1x | current sensor module capable of max. 30A for e.g. emergency shutdown				 				| tested			| 2€ 		|
| 25V voltage sensor module					|  1x | simple voltage divider module for up to 25V used as a voltage sensor to determin battery charge		| tested			| 2€ 		|
| 5200mAh - 6200mAh LiPo 30C+ 2S Tamiya/XH	|  1x | beefy LiPo as your main power source ***(this is actually your individual choice)***				| tested		 	| 40€		|

### Miscellaneous

| part or module | number | short description | status | estimated price | 
|----------------|--------|-------------------|--------|:-------------------------|
| M2x8 cylinderhead screws + M2 nuts		| 84x each | screws + nuts to mount your servohorns ***(you could glue the servohorns in place instead and save yourself 72x M2x8 screws and nuts, but i have not tested it)***, also used to mount the 1,77" TFT and the pins for the ball bearings 	| tested | 8€  |
| M3x8 cylinderhead screws + M3 nuts		| 80x each | screws + nuts for the whole assembly ***(i hope i have not forgotten some, better buy in bulk as these are usefull for other projects as well)***																							| tested | 8€  |
| M3x20 cylinderhead screws + M3 nuts		| 64x each | screws + nuts to mount your servos and assemble the upper legs																																												| tested | 12€ |
| lots of cables and connectors and stuff	|          | it's up to you which cables or wires and connectors you want to use, or if you would like to solder everything into place, and if you use heat shrinks, fabric hoses 																		| up to you | 20€ |
| PLA + TPU (***?***)						|          | you will need about 1Kg of PLA + some grams of TPU (eg. my Black/White design: 500g for the covers + upper legs, 500g for the chassis + lower legs + shoulder joints, some small grams for the grey sensorplate in the head) + some grams of TPU for the foottips | tested | 30€+ |
