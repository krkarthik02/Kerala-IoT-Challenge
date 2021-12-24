# Experiment 1 - Hello World LED Blinking
A basic Program similar to printing “Hello World “ in any programming language. The Aim is to blink an LED using Arduino Uno Board.
Arduino Uno is an open-source microcontroller board developed by Arduino.cc. It has several advantages over the conventional microcontrollers. It comes with a pre-tested software and hardware libraries and has its own integrated development environment (IDE). Also it is less expensive & beginner friendly.

## Components Required
* Arduino Uno Board
* USB Cable
* LED (Any Color) x 1 Nos
* 220 OHM Resistor X 1 Nos
* Breadboard
* Jumper Wires (Male to Male ) X 2 Nos
## Circuit Diagram

![blink circut](https://user-images.githubusercontent.com/95871421/147322940-8d19b77b-7ae9-4437-b231-1c75ead01c83.png)

## Code
```
void setup()
{
  pinMode(7,OUTPUT);

}

void loop() 
{
  digitalWrite(7,HIGH);//Led ON
  delay(1000);// waits
  digitalWrite(7,LOW);//Led OFF
  delay(1000);// waits
 

}
```
## Output


https://user-images.githubusercontent.com/95871421/147326488-ddded820-d5e0-46cb-a2ec-ab6eb0316895.mp4



