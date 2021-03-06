Notes on Wiring diagrams

Arduino_Keypad_Wiring.jpg

This image is very similar to a drawing posted on Mark Kimsal's site.  My components are sized for the
5 volt signaling used by the Arduino Mega.  I also added a 1k pull down resistor on the transmit line
to the keypad (my circuit would not work without it).

Alarm_Power_Wiring.jpg

This image documents the circuit I am using to power my alarm project.  I am using a Dell laptop power
brick (19v output) and a couple of large diodes (to drop the voltage a bit) to drive a picoUPS-100 module.  
The picoUPS will trickle charge a connected 12v sealed lead-acid (SLA) battery and continue to provide DC output if 
the primary power is removed.  The output of the picoUPS drives a DC-DC converter set for 5 volt output.  
This will power the Raspberry PI as well as the connected Arduino.  As a future mod, I plan to monitor the input and output 
power of the picoUPS as well as the battery voltage via analog inputs on the Arduino.  This should allow 
for a clean shutdown of the Raspberry PI if I detect that the input power is off and the battery voltage 
is getting low.

perfboard.jpg

This image shows how I arranged the components to build the hat for the Arudino.

rpi-alarm-1.jpg

This image shows the 6160 Honeywell keypad connected the the Arduino and RPi running my custom code.

rpi_alarm-2.jpg

This image documents the full alarm setup.  The RPi is at the top with a GPIO break-out board hat installed.  My home's sense loops connect to the RPi GPIO pins via the screw terminals on the break-out board.  You will also notice I am using a TP-Link USB wifi adapter with an external antenna.  The Arduino 2560 mega is connected vi a short USB cable.  The Arduino has a protoboard hat with circuit shown in Arduino_Keypad_Wiring.jpg.  The keyboards are connected to this hat via a screw terminal block.  The power to the RPi and Arduino is provided by a DC-DC converter with its output adjusted to 5V.  The DC-DC converter's input is provided by a picoUPS card which is connected to the input DC adapter and a 12V SLA battery. 

Links to some of parts mentioned above:
 - DC-DC converter https://www.amazon.com/gp/product/B009HPB1OI
 - picoUPS: https://www.amazon.com/gp/product/B005TWE4GU
 - battery: https://www.amazon.com/PowerStar3-Warranty-Security-System-Battery/dp/B00G045G1I
