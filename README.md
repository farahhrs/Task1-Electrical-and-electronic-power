# Task1-Electrical-and-electronic-power
This repository contains 4 subtasks:

1- [Brushless motor electronic circuit](https://github.com/farahhrs/Task1-Electrical-and-electronic-power/blob/main/README.md#1--brushless-motor-electronic-circuit).

2- [Brushless motor algoritm](https://github.com/farahhrs/Task1-Electrical-and-electronic-power/blob/main/README.md#2--brushless-motor-algoritm).

3- [Servo motor](https://github.com/farahhrs/Task1-Electrical-and-electronic-power/blob/main/README.md#3--servo-motor).

4- [Stepper motor](https://github.com/farahhrs/Task1-Electrical-and-electronic-power/blob/main/README.md#4-stepper-motor).

## 1- Brushless motor electronic circuit:
This circuit contains the following components:
- Arduino Uno R3.
- 30 , 5 Power Supply.
- H-bridge Motor Driver.
- 416 DC Motor with encoder(Brushless Motor).


Note: In this circuit, the rotation direction of the motor on the top is forward, and to the bottom one is backward.

### The code:
```
// C++ code
//motor  1
#define Ena 10
#define IN1 9
#define IN2 8
//motor  2
#define Enb 11
#define IN3 12
#define IN4 13


void setup()
{
  pinMode(Ena, OUTPUT);
  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT);
  pinMode(Enb, OUTPUT);
  pinMode(IN3, OUTPUT);
  pinMode(IN4, OUTPUT);
 
  
}

void loop(){
  //Motor1, Forward
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, LOW);
  analogWrite(Ena, 120);

  //Motor2, Backward
  digitalWrite(IN3, LOW);
  digitalWrite(IN4, HIGH);
  analogWrite(Enb, 120);

}
```
Click [here](https://github.com/farahhrs/Task1-Electrical-and-electronic-power/blob/52d6c70d2c14be73c47313031ebe186a6e11ff0b/Brushless%20motor%20electronic%20circuit.png) to see the electronic circuit.

Click [here](https://www.tinkercad.com/things/61wjgfv8Y8t-glorious-fulffy-esboo/editel?sharecode=d7nCwHONFTlWHCqBLu08L8OclMTHsXHr4rm-kmkNkkE) to see the simulatation of the  electronic circuit.

## 2- Brushless motor algoritm:
To operate the brushless motor follow these steps:

1- Put the required components:
- Arduino Uno R3.
- 30 , 5 Power Supply.
- H-bridge Motor Driver.
- 416 DC Motor with encoder(Brushless Motor).

2- Connect the components with the appropriate pins on the Arduino.

3- Start writing the code by defining the pins by using #define or const.

4- Configure the pins as OUTPUT using "pinMode" function inside the "void setup()".

5- Use "digitalWrite" function to assign the pin a HIGH or a LOW value inside the "void loop()", if the two pins that are connected to the burshless motor have the same value it will never rotate, if they differ the motor rotation direction will be either forward(input1> HIGH, input2> LOW) or backward(input1> LOW, input2> HIGH).

6- Click on start simulation.

####  Suggestion to control the rotation direction of the motor:

- We can use 2 pushbuttons (or switches), each one must be connected to an Arduino's pin, also we should use two resistors and each one of the resistors must be connected to a GND on the Arduino and to the pushbutton, finally we should connect the pushbuttons to the 5V pin on the Arduino. 
- We should define the pins that are connected to the pushbuttons.
- Inside the "void setup()" we should declare the pinMode of the pushbuttons as INPUT.
- Inside the "void loop()" we should use the digitalRead of those pins, and write if-else statements to control the rotation direction, if the first pushbutton clicked (have a HIGH value) the motor rotation direction will be forward, and if the second pushbutton clicked (have a HIGH value) the motor rotation direction will be backward.

## 3- Servo motor:
This simple circuit contains the following components:
- Arduino Uno R3.
- Positional Micro Servo.


Note: The servo motor will rotate every 500 milliseconds.

### The code:
```
// C++ code
//
int servo= 4;

void setup()
{
  pinMode(servo, OUTPUT);
}

void loop()
{
  digitalWrite(servo, HIGH);
  delay(500); // Wait for 500 millisecond(s)
  digitalWrite(servo, LOW);
  delay(500); // Wait for 500 millisecond(s)
}
```
Click [here](https://github.com/farahhrs/Task1-Electrical-and-electronic-power/blob/b4901cc0312cdd3e551fc9921ee0173f6214fe30/Servo%20motor/Servo%20motor.png) to see the electronic circuit.

Click [here](https://www.tinkercad.com/things/joslypxqlR7-shiny-densor/editel?sharecode=F7EKHXuK-3uudYewlMcJxxWqixKkN6O6hd8nDbi-cSg) to see the simulation of the electronic circuit.

## 4-Stepper motor:
This circuit contains the following components:
- DC Motor with Encoder
- Arduino Uno R3
- H-bridge Motor Driver
- 9V Battery

### The code:
```
#include <Stepper.h>
const int stepsPerRevolution =120;
Stepper myStepper(stepsPerRevolution, 11,10,9,8);
int stepCount= 0; 

void setup()
{
  Serial.begin(9600);
}

void loop()
{
  int sensorRead = analogRead(A0);
  int motorSpeed = map(sensorRead, 0, 1023, 0, 250);
  if(motorSpeed > 0){
    myStepper.setSpeed(motorSpeed);
    myStepper.step(stepsPerRevolution/ 100);
	Serial.println(sensorRead);
  }
  
}
```
Click [here](https://github.com/farahhrs/Task1-Electrical-and-electronic-power/blob/033b5fbab0b1ade4a48abd17d74b330d95883864/Stepper%20motor/Stepper%20motor.png) to see the electronic circuit.

Click [here](https://www.tinkercad.com/things/6w6bSyS4Dvu-super-snaget/editel?sharecode=gGQdMWfQiblBYjOrRCbMnDef73wEdq1RSbRnWHiwOIQ) to see the simulation of the electronic circuit.
