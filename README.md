# Arduino-Security-Alarm-System
Hardware based project with C programming at the back-end. Built with Arduino Mega 2560 and other components, Arduino IDE, and Fritzing.

![](https://github.com/rimshub/Arduino-Security-Alarm-System/blob/main/Hardware.PNG)

For alarm activation press button A from keypad, alarm will activates in 10 seconds. 
Ultrasonic sensor will detect the objects. When the alarm detect something the 
buzzer starts emitting sound. Now, in order to stop the alarm user need to enter the 
password. A four digit password is already set however user can change the 
password. The preset password will be 1234. By pressing button B on the keyboard 
user will enter “set new password” menu, where user has to enter previous password 
in order to continue and then enter the new four digit password. Now in order to stop 
alarm user have to enter new (current) password. On entering the wrong password 
user will get a message “Try Again”.

# Hardware used:
1. Arduino Mega 2560
2. Ultrasonic Sensor HC-SR04
3. Active Buzzer Module
4. Breadboard
5. Jumper wires
6. Membrane 4x4 Keypad
7. LCD 16x2
8. Potentiometer 

# Software used:
1. Arduino IDE (For Source code)
2. Fritzing (For drawing Schematics)

# Circuit Schematics:
![](https://github.com/rimshub/Arduino-Security-Alarm-System/blob/main/semantic.PNG)

![](https://github.com/rimshub/Arduino-Security-Alarm-System/blob/main/circuit%20semantic.PNG)

## Explanation:

### Keypad:
The 4×4 keypad has 8 pins, 4 of them are for the rows and 4 of them for the columns 
of the keypad. Each button is actually a push button switch which makes a short 
between one row and column when pressed. So, for example, if we set the row 1 line 
low, and all column lines high, when we will press, for example, the button 3, due 
to the short between the two lines, the column 3 line will drop to low so in such a 
case we can register that the button 3 has been pressed.

### Ultrasonic Sensor:
It emits an ultrasound at 40,000 Hz which travels through the air and if there is an 
object or obstacle on its path it will bounce back to the module. Using the travel time 
and the speed of the sound you can calculate the distance. The HC-SR04 Ultrasonic 
Module has 4 pins, Ground, VCC, Trig and Echo. The Ground and the VCC pins of 
the module needs to be connected to the Ground and the 5 volts pins on the Arduino 
Board respectively and the trig and echo pins to any digital I/O pin on the Arduino 
Board. In order to generate the ultrasound you need to set the Trig on a High State 
for 10µs. That will send out an 8 cycle sonic burst which will travel at the speed 
sound and it will be received in the Echo pin. The Echo pin will output the time in 
microseconds the sound wave traveled. Following is the circuit schematic that I draw 
using Fritzing Software.

### LCD:
It has 16 pins and the first one from left to right is the Ground pin. The second pin 
is the VCC which we connect the 5 volts pin on the Arduino Board. Next is the Vo 
pin on which we can attach a potentiometer for controlling the contrast of the display.
Next, The RS pin or register select pin is used for selecting whether we will send 
commands or data to the LCD. For example if the RS pin is set on low state or zero 
volts, then we are sending commands to the LCD like: set the cursor to a specific 
location, clear the display, turn off the display and so on. And when RS pin is set on 
High state or 5 volts we are sending data or characters to the LCD. Next comes the 
R / W pin which selects the mode whether we will read or write to the LCD. Here 
the write mode is obvious and it is used for writing or sending commands and data 
to the LCD. The read mode is used by the LCD itself when executing the program 
which we don’t have a need to discuss about it in this tutorial. Next is the E pin 
which enables the writing to the registers, or the next 8 data pins from D0 to D7. So through this pins we are sending the 8 bits data when we are writing to the registers 
or for example if we want to see the latter uppercase A on the display we will send 0100 0001 to the registers according to the ASCII table. And the last two pins A and 
K, or anode and cathode are for the LED back light.

# User Interface:
User interface will be LCD screen and keypad.
![](https://github.com/rimshub/Arduino-Security-Alarm-System/blob/main/user_interface.PNG)
