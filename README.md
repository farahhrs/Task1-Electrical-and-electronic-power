# Task1-Electrical-and-electronic-power
This repository contains 4 parts:

1- Brushless motor electronic circuit

2- Brushless motor algoritm.

3-Servo motor.

4- Stepper motor.

## 1- Brushless motor electronic circuit:
This circuit contains the following components:
- Arduino Uno R3.
- 30 , 5 Power Supply.
- H-bridge Motor Driver.
- 416 DC Motor with encoder(Brushless Motor).

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

Click [here](https://www.tinkercad.com/things/61wjgfv8Y8t-glorious-fulffy-esboo/editel) to see the simulatation of the  electronic circuit.

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
- Inside the "void setup()" we should declare the pinMode as INPUT.
- Inside the "void loop()" we should use the digitalRead of those pins, and write if-else statements to control the rotation direction, if the first pushbutton clicked (have a HIGH value) the motor rotation direction will be forward, and if the second pushbutton clicked (have a HIGH value) the motor rotation direction will be backward.

