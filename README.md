# Kerala-IoT-Challenge

## Contents
1. [Experiment 1](#experiment-1---hello-world-led-blinking)
2. [Experiment 2](#experiment-2---traffic-light)
3. [Experiment 3](#experiment-3---led-chasing-effect)

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

# Experiment 2 - Traffic Light

In the previous program, we have done the LED blinking experiment with one LED. Now, it’s time to up the stakes and do a bit more complicated experiment-traffic lights. Actually, these two experiments are similar. While in this traffic lights experiment, we use 3 LEDs with different colors rather than 1 LED.

## Components Required
* Arduino board *1
* USB cable *1
* Red M5 LED*1
* Yellow M5 LED*1
* Green M5 LED*1
* 220Ω resistor *3

## Circuit Diagram
![traffic light](https://user-images.githubusercontent.com/95871421/147324918-6cdfe934-2efd-4de4-aed1-1fae4e9f3a82.png)

## Code
```
#define RED 7
#define YELLOW 6
#define GREEN 5
void setup(){ 
  pinMode(RED, OUTPUT);
  pinMode(YELLOW, OUTPUT);
  pinMode(GREEN, OUTPUT);
} 
void loop(){
  //Red led on , green led off and wait 5 secound then Red led OFF
  digitalWrite(RED, HIGH);  
  digitalWrite(GREEN, LOW);
  delay(5000);
  digitalWrite(RED, LOW);
  // yellow led blink 3 time in 1 sec
  for(int i=0;i<3;i++){ 
    digitalWrite(YELLOW,HIGH);
    delay(1000);
    digitalWrite(YELLOW,LOW);
    delay(1000);
  }
  //Green led on , Red led off and wait 5 secound then Green LED OFF
  digitalWrite(GREEN, HIGH);  
  digitalWrite(RED, LOW);
  delay(5000);
  digitalWrite(GREEN, LOW);
  // yellow led blink 3 time in 1 sec
  for(int i=0;i<3;i++){ 
    digitalWrite(YELLOW,HIGH);
    delay(1000);
    digitalWrite(YELLOW,LOW);
    delay(1000);
  }

}
}
```
## Output

In Traffic light the green LED blink about 5 second, then it is turnoff. Then the yellow LED blinks 3 times with a time interval of 1 second.Then the red LED blink about 5 seconds. This process continues.


https://user-images.githubusercontent.com/95871421/147326600-831abffd-2865-4b25-83b6-3d1ce8a371eb.mp4

# Experiment 3 - LED Chasing Effect
We often see billboards composed of colorful LEDs. They are constantly changing to form various light effects. In this experiment, we compile a program to simulate LED chasing effect. The long lead of LED is the positive side; short lead is negative.

## Components Required
* Led *6
* Arduino board *1
* 220Ω resistor *6
* Breadboard *1
* USB cable*1
* Breadboard wire *13

## Circuit Diagram
![chasing](https://user-images.githubusercontent.com/95871421/147329667-5d95d105-c47b-4f0d-86bd-91d250b4b834.png)


## Code
```
int BASE = 2 ;  
int NUM = 6;   
void setup()
{
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     pinMode(i, OUTPUT);   // set I/O pins as output
   }
}
void loop()
{
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     digitalWrite(i, LOW);    // set I/O pins as “low”, turn off LEDs one by one.
     delay(250);        // delay
   }
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     digitalWrite(i, HIGH);    // set I/O pins as “high”, turn on LEDs one by one
     delay(250);        // delay
   }  
}
```
## Output


https://user-images.githubusercontent.com/95871421/147329783-90be3bc1-2cd2-4796-9400-e73f9af32535.mp4


