


Semester: I
Subject Name: Embedded and Iot Technology
Name: Aishwarya Pandurang Jawalekar
Class: MSc. Computer Science (Part-1)
Roll No.: 18
Exam Seat No.: 13228318










This is to certify that

Mr. /Miss. 			Aishwarya Pandurang Jawalekar

Roll No. 18 Exam Seat No. 13228318 Satisfactorily completed the Practical in Embedded And Iot Technology As laid down in the regulation of University Of Mumbai for the purpose of MSc (Computer Science) Semester -I   (Practical) Examination 2022 -2023 .

Date:       
Place:                          
                                                                                                                         Head
                                                                                                        Dept. of Computer Science
                                                                                                           Signature of Examiners

Professor In-charge Computer Science
 1)_______________________
   2)_______________________



(DEPARTMENT OF COMPUTER SCIENCE)



Date	Sr. No.	Practical Name	Pg. No.	Remark
	

1	Design and implement basics embedded circuits 
1. Automatic Alarm system- Alarm should get tigger by senor 2. Timer based buzzer 3. Sensor based Counting device		
	

2	Demonstrate communication between two embedded devices using UART port 		
	
3
	Built an IoT system to send ticket before entering the bus.		
	
4
	Demonstrate an IoT based game which can be played between two player who are physically at a considerable distance. 		
	
5
	Develop a IoT application which will record the movement and orientation of your phone and give the data back to the PC		
	

6	Develop an IoT application that will raise an alarm whenever with going to rain outside based on the weather prediction data
			
	

7	Deploy an IoT application which will alert you by beeping or vibrating your phone whenever you get someone call your name. 		
	8	Develop an IoT application for monitoring water levels in tanks and automatically start the motor to fill the tank if the level goes below the critical level.		
	9	Develop an IoT module to which measure the intensity of light and send the same to your PC/ Phone		
	10	Develop an IoT application for Motion detection		







Practical 1: Design and implement basics embedded circuits

1.(a) Automatic Alarm system- Alarm should get tigger by sensor:
Steps to Perform:
Step 1:  1) Take Motion Sensor
              2) Take Component - MCU Board 
              3) Take Alarm 

Step 2: 1) Now we will connect the Motion Sensor to MCU Board with 
                  IoT custom cable connect Motion Sensor (D0) to connect with MCU Board (D0) 
    2)Then we will connect MCU board to Alarm with IoT custom cable connect MCU 
        Board (D1) to Alarm (D0)
 
Step 3 : 1) Now click on MCU Board go to Programming then Select New, Select Template-
                  Empty-Python then click on Create
              2) Click on main.py file then write code  



 
 
Code :-
from gpio import *
from time import *

def main():
	pinMode(0,IN)
	while True:
		if digitalRead(0) == HIGH:
			print("Alaram Activated")
			digitalWrite(1,HIGH)
		else:
			print("Alarm DeActivated")
			digitalWrite(1,LOW)
		sleep(1)
if __name__ == "__main__":
main()






Step 4 : 1) Click on Run  

 

1.(b) Timer based buzzer:

Steps to Perform:
Step 1: 1) Take Component - MCU Board 
             2) Take Alarm

Step 2: 1) Now we will connect MCU board to Alarm with IoT custom cable connect MCU 
      Board (D0) to Alarm (D0)

   




Step 3: 1) Now click on MCU Board go to Programming then Select New, Select Template-
                 Empty-Python then click on Create
             2) Click on main.py file then write code  

 


Code:
from gpio import *
from time import *

def main():
	while True:
		print("Program Started")
		digitalWrite(0,HIGH)
		sleep(1)
		digitalWrite(0,LOW)
		sleep(1)
if __name__=="__main__":
	main()
Step 4 : 1) Click on Run 
 
 
 
1.(c) Sensor based Counting device: 
Steps to Perform:
Step 1:  1) Take Motion Sensor
              2) Take Component - MCU Board 
 Step 2: 1) Now we will connect the Motion Sensor to MCU Board with 
                  IoT custom cable connect Motion Sensor (D0) to connect with MCU Board (D0) 

 



Step 3 : 1)Now click on MCU Board go  to Programming then Select New , Select Template-
                  Empty-Python then click on Create
              2) Click on main.py file then write code  

Code:
from gpio import *
from time import *
 
def main():
	count = 0
	pinMode(0,IN)
	while True:
		if digitalRead(0) == HIGH:
			print(count)
			sleep(1)
			count += 1

if __name__ == "__main__":
	main()

Step 4 : 1) Click on Run  
              2) Press Alt button then Start Counting

   
 
Practical 2
Demonstrate communication between two embedded devices using UART port

Steps to Perform:

Step 1:  1) Take Smoke Sensor
          2) Take Component - MCU Board 
          3) Take Alarm
          4) Take LCD


Step 2:  1) Now we will connect Smoke Sensor to MCU Board with IoT custom cable
              connect Smoke Sensor (D0) to MCU Board (D0) 
2) Then we will connect MCU Board to Alarm with IoT custom cable connect MCU
    Board (D1) to Alarm (D0) 
3) Then we will connect MCU Board to LCD with IoT custom cable connect MCU
    Board (D2) to LCD (D0) 

 




Step 3: 1) Now click on MCU Board go to Programming then Select New, Select Template-
                  Empty-Python then click on Create
             2) Click on main.py file then write code 
 
Practical 3
Built an IoT system to send ticket before entering the bus
Steps to Perform:
Step 1:  1) Take LCD
          2) Take Component - MCU Board 
          3) Take RFID Reader
          4) Take DLC Home Gateway
          5) Take PC
          6) Take Door
          7) Take RFID Card

Step 2:  1) Now we will connect LCD to MCU Board with IoT custom cable
              connect LED (D0) to MCU Board (D0) 
2) Then go to the RFID Reader click on Advanced then  click  i/o config
     then go the Analog slots and collect value 2 then close. 


 



3) Now we will connect RFID Reader to MCU Board with IoT custom cable connect
 RFID Reader (A1) to MCU Board (A0) 
 


Step 3: 1) Click on pc then go to the physical then switch off then select PT-HOST-NM-1W
                 Then switch on.
             2) Then go to the config click on wireless0 then select HomeGateway then close 
             3) Then go to RFID Reader click on i/0 config then select network Adapter (PT-IOT-NM
                 1W) then go to config and select Home Gateway 
Step 4: 1) Now click on MCU Board go to Programming then Select New, Select Template-
                  Empty-Python then click on Create
             2) Click on main.py file then write code 
 

 Code: 
from gpio import *
from time import *
from ioeclient import IoEClient

def main():
	pinMode(0,OUT)
	pinMode(1,IN)
	
	while True:
		customWrite(0,"Waiting")
		rfid = analogRead(A1)
		if (rfid==0):
			customWrite(0,"Sucessful")
			
		delay(3000)
		
if __name__ == "__main__":
	main()
			
Step 5: 1) Click on Run
       2) Drag RFID Card and Drop in front of RFID Reader
 
  



 
Practical 4
Demonstrate an IoT based game which can be played between two player who are physically at a considerable distance

Steps to Perform:
Step 1:  1) Take Fan
          2) Take Window 
          3) Take Smart Phone 
          4) Take Thermostat
          5) Take DLC (Home gateway)

Step 2:  1) Now we will connect Thermostat to DLC (Home gateway)
              Copper Straight cable connect Thermostat (Fastethernet0) to DLCBoard (Ethernet1)
          2) Then go to DLC (Home Gateway) config IP 


 

Step 3:  1) Now we will click Thermostat then go to config change display name and select Home gateway then click on FastEthernet 0 then select IP configuration DHCP
          2) Then go to Smart Phone then click on Desktop then click on conditions and click on add   
               Name – Turn the celling fan 
                 

 
 
Practical 5
Develop a IoT application which will record the movement and orientation of your phone and give the data back to the PC


Steps to Perform:
Step 1:  1) Take Motion Detector
          2) Take Webcam 
          3) Take Switch 2960
          4) Take Genetic Server


Step 2:  1) Now we will connect Switch to Server with Copper Straight cable
              connect Switch(FastEthernet0/1) to Server (FastEthernet0)
          2) Then connect Switch to Motion Detector with Copper Straight cable 
              connect Switch(FastEthernet0/2) to Motion Detector (FastEthernet0)
3) Now we will connect Switch to Webcam with Copper Straight cable connect Switch (FastEthernet0/3) to Webcam (FastEthernet0)


Step 3:  1) Click on Server go to Desktop then go IP configuration and set the IP 
              2) Then go to the Webcam then click on config then set the IPs 
              3) Then go to Server click on Desktop then go to Web Browser  then fill URL then        Register Server Login 
              4) Then go to Webcam click on Config select Remote Server 
              5) Same goes for Motion Detector 


   


 
Practical  6 
Develop an IoT application that will raise an alarm            whenever with going to rain outside based on the weather prediction data.

Steps to Perform: 
Step 1:  1) Take Alarm  
              2) Take Component - MCU Board 
              3) Take Humiture Sensor 
              4) Take Humiture Monitor 
              5) Take Humidifier

Step 2: 1) Now we will connect the Alarm to MCU Board with 
                  IoT custom cable connect Alarm (D0) to connect with MCU Board (D0) 
   2) Then we will connect the   MCU Board Humiture sensor with 
                  IoT custom cable connect MCU Board (D1) to connect with Humiture sensor (A0) 

 
Step 3 : 1) Now click on MCU Board go to Programming then Select New, Select Template-
                  Empty-Python then click on Create
              2) Click on main.py file then write code

   

Code:
from gpio import *
from time import *

def main():
	while True:
		val = digitalRead(0)
		print (val)
		if val >= 600:
			digitalWrite(1,HIGH)
			print("status : Carry your Umbrella")
		else: 
			digitalWrite(1,LOW)
			print("status : no need to carry Umbrella")
		delay(500)
		
if __name__ =="__main__":
     main()
     
     
Step 4 : 1) Click on Run  

 
 
Practical 7
Deploy an IoT application which will alert you by beeping or vibrating your phone whenever you get someone call your name.

Steps to Perform:
Step 1:  1) Take LCD
              2) Take Component - MCU Board 
              3) Take Temperature Sensor 
              4) Take Laptop 
              5) Take DCL(HomeGateway)
              6) Take Thermostat


Step 2: 1) Now we will connect the LCD to MCU Board with 
                  IoT custom cable connect LCD (D0) to connect with MCU Board (D0) 
   2) Then we will connect MCU board to Temperature Sensor with IoT custom cable 
        connect MCU Board (A0) to Temperature Sensor (A0)
                  3) Now we will connect Thermostat to DLC (Home gateway)
                  Copper Straight cable connect Thermostat (Fastethernet0) to DLCBoard (Ethernet1)
                  4) Then we will connect Laptop to DLC (Home gateway)
                  Copper Straight cable connect Laptop (Fastethernet0) to DLCBoard (Ethernet2)


Step 3: 1) Now click on MCU Board go to Programming then Select New, Select Template-
                  Empty-Python then click on Create
              2) Click on main.py file then write code  


 
        



 
Practical 8
Develop an IoT application for monitoring water levels in tanks and automatically start the motor to fill the tank if the level goes below the critical level
Steps to Perform:
    Step 1:  1) Take LED
              2) Take Component - MCU Board 
              3) Take Motor
              4) Take Water sensor 
              5) Take Water Level Monitor 
              6) Take Lawn Sprinkle

Step 2:  1) Now we will connect LED to MCU Board with IoT custom cable
                  connect LED (D0) to MCU Board (D0) 
              2) Then we will connect MCU Board to Water Sensor with IoT custom     cable connect MCU Board(D1) to water sensor (A0)
              3) Now we will connect MCU Board to Motor with IoT custom cable connect MCU Board(D2) to Motor (A0)

 
Step 3:  1) Now click on MCU Board go to Programming then Select New, Select Template-
                  Empty-Python then click on Create
              2)  Click on main.py file then write code 
 
 
Code:
from options import Options
from time import *
import math
from physical import *
from gpio import *
from environment import Environment
from ioeclient import IoEClient
from pyjs import *

def setup ():
    pinMode(0, OUTPUT)
    pinMode(1,OUTPUT)

def loop ():
    waterLevel = math.floor(js_map(analogRead(A0), 0, 1023, 0, 20) + 0.5) 
    if waterLevel >= 5:
        digitalWrite(0, HIGH)
        digitalWrite(1,LOW)
    else:
        digitalWrite(0, LOW)
        digitalWrite(1,HIGH)
    delay(1000)

if __name__ == "__main__":
    setup()
    while True:
        loop()
        idle()
               
Step 4: 1) Now click on MCU Board go to Programming then Select New, Create new       python file of name pyjs.py and click on Create
           2) Click on pyjs.py file then write code  
 

Code:
class JsObject(dict):
    def __init__(self, d):
        for k in d.keys():
            setattr(self, k, d[k])

def js_map(x, inMin, inMax, outMin, outMax):
    return (x - inMin) * (outMax - outMin) / (inMax - inMin) + outMin

Step 5: 1) Click on Run 
             2) Press Alt button then Start
 
 
 
 Step 6: Wait for some time motor  will run automatically.
 
Practical 9
Develop an IoT module to which measure the intensity of light and send the same to your PC/ Phone
Steps to Perform:
Step 1:  1) Take Breadboard 
              2) Take Resistor  
              3) Take LDR
              4) Take Laptop 
              5) Take MCU Board 
              6) Take Jumping Cable 

Step 2: 1) LDR put on Breadboard 
             2) Resistor going to connect one end of a resistor and one end of the Breadboard 
             3) We connect MCU Board to Breadboard Using Jumper wire



 




Step 3: 1) Now we will connect Breadboard and MCU board Using Red colour jumper wire 
             2) Then Connect MCU board to using Yellow colour jumper wire
             3) Then free end of Resistor to MCU Board using Green Colour jumper wire   


 
 

	Practical 10: Develop an IoT application for Motion detection

Steps to Perform:
Step 1:  1) Take Fan 
              2) Take Component - SBC Board 
    3) Take Motion Sensor

Step 2:  1)  Now we will connect Fan to SBC Board with 
                   IoT custom cable connect Fan (D0) to connect with SBC Board (D0) 
    2) Then we will connect SBC board to Motion Sensor with IoT custom cable connect       MCU Board (D1) to Motion Sensor (D0)

 



Step 3: 1) Now click on SBC Board go  to Programming then Select New, select Template
 Empty-Python then click on Create
               2) Click on main.py file then write code
   

  
 
Code :-
from gpio import *
from time import *

def main():
	while True:
		value = digitalRead(0)
		if value >=1:
			customWrite(1, "2")
			print("Fan ON")
		else:
			customWrite(1, "0")
			print("Fan OFF")
		delay(500)
		
if __name__ == "__main__":
	main()

Step 4 : 1) Click on Run  

 
