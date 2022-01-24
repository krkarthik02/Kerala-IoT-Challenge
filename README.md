# Kerala-IoT-Challenge
[Experiment 1](Kerala-IoT-Challenge/blob/main/README.md#experiment-1---hello-world-led-blinking)

### Kerala-IoT-Challenge
  Foxlab Makerspace in association with GTech - Group of Technology Companies in Kerala is launching our prestigious program “Kerala IoT Challenge 2021”, with a vision to mould 100 IoT experts in Kerala, hosting on the µLearn platform. Kerala IoT Challenge is a program designed in 4 levels followed by a hackathon to identify and train quality industry leaders in the IoT domain, while any novice learner can start with layer 1 and others can enter laterally to the desired layer after an evaluation.

### About Me
Hello everyone! I’m K R Karthik, 2nd year BCA student from St.George's College ,Aruvithura,Kottayam. I’m here to explore new dimensions of the IoT world.And I am also interested in Cyber Security and Coding.

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
