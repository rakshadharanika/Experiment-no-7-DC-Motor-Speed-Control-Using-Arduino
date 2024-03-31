
###  DATE: 21-03-2024
###  NAME: V RAKSHA DHARANIKA
###  ROLL NO :212223230167
###  DEPARTMENT:AIDS
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
```
int enable=6;
int input1=3;
int input2=4;

void setup()
{
  pinMode(enable, OUTPUT);
   pinMode(input1, OUTPUT);
   pinMode(input2, OUTPUT);
}

void loop()
{
  analogWrite(enable,600);
  delay(1000);
  digitalWrite(input1, HIGH);
  digitalWrite(input2, LOW);
  delay(7000);
  digitalWrite(input1, LOW);
  digitalWrite(input2, HIGH);
   delay(7000);
     
     
     
}
```
### OUTPUT

![Screenshot (87)](https://github.com/rakshadharanika/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/149348380/d24d25fd-56ac-4b28-ab6d-578e07f9ce1b)




### SIMULATION REPRESENTATION


![Screenshot (89)](https://github.com/rakshadharanika/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/149348380/ebe65dc1-53cf-4556-9bda-c37f99158971)



### GRAPH 
![image](https://github.com/anbuselvan1519/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/139841744/5630056f-f16b-44b7-8aa1-9bbe7ed57fca)



###  TABULATION 
 ![image](https://github.com/anbuselvan1519/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/139841744/d495b501-e0cf-4cab-ac85-50f7fc473818)
1	10	660
2	30	2024
3	50	3216
4	80	5120
5	100	6523
6	150	9715
7	170	11234
8	190	12345
9	220	14276
10	225	16587
![image](https://github.com/rakshadharanika/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/149348380/08b3a11a-a865-4536-8091-b90d6939dddf)









### RESULTS AND DISCUSSION 

The program to control the speed and the direction of a DC motor using L293D driver ic( H- bridge) is completed and executed successfully.
