# Kerala-IoT-Challenge

## Contents
1. [Experiment 1](#experiment-1---hello-world-led-blinking)
2. [Experiment 2](#experiment-2---traffic-light)
3. [Experiment 3](#experiment-3---led-chasing-effect)
4. [Experiment 4](#experiment-4---button-controlled-led)
5. [Experiment 5](#experiment-5---buzzer)
6. [Experiment 6](#experiment-6---rgb-led)
7. [Experiment 7](#experiment-7---ldr-sensor)
8. [Experiment 8](#experiment-8---flame-sensor)
9. [Experiment 9](#experiment-9---lm35-temperature-sensor)
10. [Experiment 10](#experiment-10---ir-remote-control-using-tsop)
11. [Experiment 11](#experiment-11---potentiometer-analog-value-reading)
12. [Experiment 12](#experiment-12---seven-segment-display)
13. [Assignments](#assignments)
    1. [Assignment 1](#assignment-1---night-lighting-system)
    2. [Assignment 2](#assignment-2---6-number-random-dice)

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

![blink circut](https://user-images.githubusercontent.com/95871421/150783162-1fbf57ed-54ea-4587-9911-3e69deaa53eb.png)


## Code
```ino
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


[Output Video](https://user-images.githubusercontent.com/95871421/147326488-ddded820-d5e0-46cb-a2ec-ab6eb0316895.mp4)

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

```ino
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

[Output Video](https://user-images.githubusercontent.com/95871421/147326600-831abffd-2865-4b25-83b6-3d1ce8a371eb.mp4)

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
```ino
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


[Output Video](https://user-images.githubusercontent.com/95871421/147329783-90be3bc1-2cd2-4796-9400-e73f9af32535.mp4)

# Experiment 4 - Button Controlled LED
An experiment to light an LED using a Push Button.

## Components
* Arduino Uno
* Breadboard
* LED 
* Jumper wire
* Restsor 220 ohm , 10 ohm
* michro switch

## Circuit Diagram
![cd4](https://user-images.githubusercontent.com/95871421/150775239-7bec4eb4-d851-444f-8509-b0a406f98251.png)

## Code
```ino
// set Read pin 10
#define READ_PIN 10
// led colnnect 13 
#define LED 13
bool readData=0;
void setup(){ 
  pinMode(READ_PIN ,INPUT);
  pinMode(LED ,OUTPUT);
} 
void loop(){
  readData=digitalRead(READ_PIN); // read data
  Serial.println(readData);
  digitalWrite(LED,readData); // read data high LED WILL ON otherwice led will off
}
```
## Output



[Output Video](https://user-images.githubusercontent.com/95871421/151300869-aaee0c8b-9b24-4fa1-a6f8-416443f0a61a.mp4)



# Experiment 5 - BUZZER
An experiment to understand the working of a buzzer

## Components
* Arduino 
* Breadboard
* BUZZER
* Jumper wire

## Circuit Diagram
![cd5](https://user-images.githubusercontent.com/95871421/150775720-04a5c3ed-69fa-4917-8738-57fbdf8f594c.png)


## Code
```ino
// Buzzer Connect 13
#define BUZZER 13
void setup(){ 
  pinMode(BUZZER ,OUTPUT);
} 
void loop(){
  digitalWrite(BUZZER,HIGH); // BUZZER ON
  delay(1000);
  digitalWrite(BUZZER,LOW); // BUZZER OFF
  delay(1000);
}
```
## Output


[Output Video](https://user-images.githubusercontent.com/95871421/151300914-8cfe9e12-73f6-4dd5-bd29-374049169f9b.mp4)



# Experiment 6 - RGB LED
An experiment to understand the working of a RGB LED.

## Components
* Arduino Uno
* Breadboard
* RGB LED
* Jumper wire
* Restsor 220 ohm 

## Circuit Diagram

![cd6](https://user-images.githubusercontent.com/95871421/150775833-e5fcca96-ec27-43bb-9b2d-553a745d6958.png)


## Code
```ino
int RGB_LED[]={11,9,10};
void setup(){ 
  for(int i=0;i<3;i++)
    pinMode(RGB_LED[i],OUTPUT);
} 
void loop(){
  for(int j=0;j<255;j++){
    analogWrite(RGB_LED[0],j);
    analogWrite(RGB_LED[1],0);
    analogWrite(RGB_LED[2],0);
    delay(5);
  }
  for(int j=0;j<255;j++){
    analogWrite(RGB_LED[0],0);
    analogWrite(RGB_LED[1],j);
    analogWrite(RGB_LED[2],0);
    delay(5);
  }
  for(int j=0;j<255;j++){
    analogWrite(RGB_LED[0],0);
    analogWrite(RGB_LED[1],0);
    analogWrite(RGB_LED[2],j);
    delay(5);
  }
  for(int j=0;j<255;j++){
    analogWrite(RGB_LED[0],j);
    analogWrite(RGB_LED[1],j);
    analogWrite(RGB_LED[2],0);
    delay(5);
  }
  for(int j=0;j<255;j++){
    analogWrite(RGB_LED[0],j);
    analogWrite(RGB_LED[1],0);
    analogWrite(RGB_LED[2],j);
    delay(5);
  }
  for(int j=0;j<255;j++){
    analogWrite(RGB_LED[0],0);
    analogWrite(RGB_LED[1],j);
    analogWrite(RGB_LED[2],j);
    delay(5);
  }
  for(int j=0;j<255;j++){
    analogWrite(RGB_LED[0],j);
    analogWrite(RGB_LED[1],j);
    analogWrite(RGB_LED[2],j);
    delay(5);
  }
  
}
```
## Output


[Output Video](https://user-images.githubusercontent.com/95871421/151300961-ce9c0311-8ab4-4466-8427-0f870929aad5.mp4)



# Experiment 7 - LDR SENSOR 
An experiment to understand the working of an LDR light Sensor.

## LDR : Light Dependent Sensor

![ldr](https://user-images.githubusercontent.com/95871421/151294394-14693f41-38a2-43ab-a53b-3fe53cee18d2.png)

Photo Resistor (Photovaristor) is a resistor whose resistance varies from different incident light strength. It’s based on the photoelectric effect of semiconductor. If the incident light is intense, its resistance reduces; if the incident light is weak, the resistance increases.

## Components
* Arduino Uno
* Breadboard
* RED,GREEN LED
* Jumper wire
* Restsor 220 ohm 10 k
* LDR Sensor

## Circuit Diagram
![cd7](https://user-images.githubusercontent.com/95871421/150775972-a876855a-e3c0-4230-8786-f1da8352fceb.png)


## Code
```ino
#define LDR 12 // LDR CONNECT 12
#define RLED 11 // Red LED CONNECT 11
#define GLED 10 // Green LED Connect 10
bool readData=0;
void setup(){ 
  pinMode(RLED,OUTPUT);
  pinMode(GLED,OUTPUT);
  pinMode(LDR,INPUT);
} 
void loop(){
  readData=digitalRead(LDR);
  digitalWrite(RLED,readData);
  digitalWrite(GLED,!readData);
}
```
## Output



[Output Video](https://user-images.githubusercontent.com/95871421/151300996-ebe37634-52aa-4ace-898e-740045e5d649.mp4)



# Experiment 8 - FLAME SENSOR 
An experiment to understand the working of an Flame sensor

## Components
* Arduino Uno
* Breadboard
* RED LED
* BUZZER
* Jumper wire
* Restsor 220 ohm 10 k
* Flame Sensor

## Circuit Diagram
![cd8](https://user-images.githubusercontent.com/95871421/150776116-853ef3be-762f-4409-90b6-7bed912152b8.png)

## Code
```ino
#define FLAME A0 // Flaem sensor CONNECT A0
#define RED 11 // Red LED CONNECT 11
#define BUZZER 10 // Buzzer LED Connect 10

int data;
void setup(){ 
  pinMode(RED,OUTPUT);
  pinMode(FLAME,INPUT);
  pinMode(BUZZER,OUTPUT);
  Serial.begin(9600);
} 
void loop(){
  data=analogRead(FLAME);
  Serial.print("DATA :");
  Serial.println(data);
  if(data>600){
    digitalWrite(RED,HIGH);
    digitalWrite(BUZZER,HIGH);
    delay(1000);
  }else{
    digitalWrite(RED,LOW);
    digitalWrite(BUZZER,LOW);
  }
}
```
## Output


[Output Video](https://user-images.githubusercontent.com/95871421/151301061-5935e704-66a1-4c80-b37c-5ef0c5dd8ae6.mp4)



# Experiment 9 - LM35 Temperature Sensor
An experiment to understand the working of an LM35 Temperature Sensor.

## LM35 Temperature Sensor
LM35 is a common and easy-to-use temperature sensor. LM35 is a widely used temperature sensor with many different package types. At room temperature, it can achieve the accuracy of ±1/4°C without additional calibration processing. LM35 temperature sensor can produce different voltage by different temperature When temperature is 0 ℃, it outputs 0V; if increasing 1 ℃, the output voltage will increase 10 mv.

## Components
* Arduino Uno
* Breadboard
* Jumper wire

## Circuit Diagram
![cd9](https://user-images.githubusercontent.com/95871421/150776454-7b693faa-6e65-4b87-80e7-48455e1dc78c.png)


## Code
```ino
#define LM35_SENSOR A0 // Flaem sensor CONNECT A0
float readData;
float tempC,tempF;
void setup(){ 
  pinMode(LM35_SENSOR,INPUT);
  Serial.begin(9600);
} 
void loop(){
  readData=analogRead(LM35_SENSOR);
  tempC=(readData/1024.0)*500;
  Serial.print("Temprature : ");
  Serial.print(tempC);
  Serial.print(" *C =");
  tempF=(tempC*9.0)/5.0 + 32.0;
  Serial.print(tempF);
  Serial.println(" *F");
}
```
## Output

![exp 9](https://user-images.githubusercontent.com/95871421/151301122-fe2de1dd-27b8-4a35-aed8-70c5822f76aa.jpg)


# Experiment 10 - IR Remote Control Using TSOP
An experiment to understand the working of IR Remote Control using TSOP

## Components
* Arduino Uno
* Breadboard
* Jumper wire
* IR Recever (TSOP)
* 5 LED
* 220 ohm Resistor
* IR REMOTE (Any remote)

## Circut Diagram

![cd102](https://user-images.githubusercontent.com/95871421/150777235-4750076a-2a17-4287-a7d4-71ea95fe3a03.png)

## Code
```ino
#include <IRremote.h> 
int RECV_PIN = A0;              
int c=0;                      
IRrecv irrecv(RECV_PIN);
decode_results results;
void setup()
{
   pinMode(8, OUTPUT);
   pinMode(9, OUTPUT);
   pinMode(10, OUTPUT);
   pinMode(11, OUTPUT);
   pinMode(12, OUTPUT);

   Serial.begin(9600);
  irrecv.enableIRIn();                     
}
void loop() {
  if (irrecv.decode(&results)) {
    Serial.println(results.value);
    irrecv.resume();                        
  if(results.value==33444015)                              
  {
             digitalWrite(8,HIGH);
  }
  else if(results.value==33441975)
  {
             digitalWrite(8,LOW);
  }
   if(results.value==33478695)                                     
  {
             digitalWrite(9,HIGH);
  }
  else if(results.value==33441975)
  {
             digitalWrite(9,LOW);
  }
    if(results.value==33486855)                                      
  {
             digitalWrite(10,HIGH);
  }
  else if(results.value==33441975) 
  {
             digitalWrite(10,LOW);
  }
    if(results.value==33435855)                                       
  {
             digitalWrite(11,HIGH);
  }
  else if(results.value==33441975)
  {
             digitalWrite(11,LOW);
  }
    if(results.value==33468495)                                        
  {
             digitalWrite(12,HIGH);
  }
  else if(results.value==33441975)
  {
             digitalWrite(12,LOW);
  }
  }
}
```
## Output


[Output Video](https://user-images.githubusercontent.com/95871421/151301880-010bc068-0df9-42fd-ad5a-37804f0a7885.mp4)



# Experiment 11 - Potentiometer analog Value Reading

> An experiment to understand the working of Potentiometer.

## Components Required

* Arduino Uno Board*1
* 10K Potentiometer *1
* Breadboard*1
* Breadboard Jumper Wire*3
* USB cable*1

## Circuit Diagrams

![cd11](https://user-images.githubusercontent.com/95871421/151294058-ed0da37e-5335-4a34-b90c-ad715057073f.png)


## Code

```

int potpin=0;// initialize analog pin 0
int ledpin=13;// initialize digital pin 13
int val=0;// define val, assign initial value 0
void setup()
{
pinMode(ledpin,OUTPUT);// set digital pin as “output”
Serial.begin(9600);// set baud rate at 9600
}
void loop()
{
digitalWrite(ledpin,HIGH);// turn on the LED on pin 13
delay(50);// wait for 0.05 second
digitalWrite(ledpin,LOW);// turn off the LED on pin 13
delay(50);// wait for 0.05 second
val=analogRead(potpin);// read the analog value of analog pin 0, and assign it to val 
Serial.println(val);// display val’s value
}

```

## Output


[Output Video](https://user-images.githubusercontent.com/95871421/151345847-dd8da5e7-f3e0-4cfa-ad3f-62d61d70da17.mp4)





# Experiment 12 - Seven Segment Display
An experiment to understand the working of 7 Segment Display.

## Components
* Arduino Uno
* Breadboard
* Seven Segment Display
* Jumper wire
* Restsor 220 ohm

## Circuit Diagram
![cd12](https://user-images.githubusercontent.com/95871421/150778404-482ea5ae-8324-4427-9a40-7687ad961998.png)



## Code
```ino

int sevenSeg[]={13,12,11,10,9,8,7,6};
void number(int i){
  switch(i){
    case 0: digitalWrite(sevenSeg[0],LOW);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH);
            digitalWrite(sevenSeg[4],HIGH);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
    case 1: digitalWrite(sevenSeg[0],LOW);
            digitalWrite(sevenSeg[1],HIGH);
            digitalWrite(sevenSeg[2],HIGH);
            
            //digitalWrite(sevenSeg[3],HIGH);
            digitalWrite(sevenSeg[4],HIGH);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],HIGH);
            digitalWrite(sevenSeg[7],HIGH);
            break;
    case 2: digitalWrite(sevenSeg[0],LOW);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],HIGH);
            
           // digitalWrite(sevenSeg[3],HIGH); 
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],HIGH);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
    case 3: digitalWrite(sevenSeg[0],HIGH);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH); 
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],HIGH);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
    case 4: digitalWrite(sevenSeg[0],HIGH);
            digitalWrite(sevenSeg[1],HIGH);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH); 
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],HIGH);
            digitalWrite(sevenSeg[7],LOW);
            break;

    case 5: digitalWrite(sevenSeg[0],HIGH);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH); 
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],HIGH);
            break;
   case 6: digitalWrite(sevenSeg[0],LOW);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH); 
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],HIGH);
            break;
    case 7: digitalWrite(sevenSeg[0],HIGH);
            digitalWrite(sevenSeg[1],HIGH);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH);
            digitalWrite(sevenSeg[4],HIGH);
            
            digitalWrite(sevenSeg[5],HIGH);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
   case 8: digitalWrite(sevenSeg[0],LOW);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH);
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
   case 9: digitalWrite(sevenSeg[0],HIGH);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH);
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
      
  }
  
}
void setup(){ 
  Serial.begin(9600);
 
  for(int i=0;i<8;i++){
    pinMode(sevenSeg[i],OUTPUT);
    digitalWrite(sevenSeg[i],HIGH);
  }
  
    
} 
void loop(){
  for(int i=9;i>=0;i--){
    number(i);
    delay(750);
  }
}
```
## Output 

[Output Video](https://user-images.githubusercontent.com/95871421/151345932-1d4e0e67-10fd-4e10-a3c3-6cbe76097437.mp4)




# Assignments

# Assignment 1 - Night lighting system 
An experiment to create automatic night lamp model using LDR and LED

## Components
* Arduino Uno
* Breadboard
* RED,GREEN LED
* Jumper wire
* Restsor 220 ohm 10 k
* LDR Sensor

## Circuit Diagram

![ass1cd](https://user-images.githubusercontent.com/95871421/150783910-3b2687ec-1ed9-44a2-84a8-573fe9d0a67e.png)


## Code
```ino
#define LDR A0// LDR CONNECT A0
#define LED 11 // LED CONNECT 11
int readData=0;
void setup(){ 
  pinMode(LED,OUTPUT);
  pinMode(LDR,INPUT);
  Serial.begin(9600);
} 
void loop(){
  readData=analogRead(LDR);
  Serial.println(readData);
  if(readData>200)
    digitalWrite(LED,HIGH);
  else
    digitalWrite(LED,LOW);
}
```
## Output

[Output Video](https://user-images.githubusercontent.com/95871421/151346198-f7d252d7-b8f4-4b24-9854-d0128b26989b.mp4)

# Assignment 2 - 6 Number Random Dice
An experiment to create a Digital Dice using 6 LEDs and 1 Push Button

## Components
* Arduino Uno
* Breadboard
* pushbuttion
* Jumper wire
* Restsor 220 ohm
* push buttion

## Circut Diagram

![ass2cd](https://user-images.githubusercontent.com/95871421/150783869-480f780f-d60c-4cf9-ad90-8175b5fa0add.png)


## Code
```ino
#define readPin A0
bool readStatus=0;
int sevenSeg[]={13,12,11,10,9,8,7,6};
void number(int i){
  switch(i){
    case 0: digitalWrite(sevenSeg[0],LOW);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH);
            digitalWrite(sevenSeg[4],HIGH);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
    case 1: digitalWrite(sevenSeg[0],LOW);
            digitalWrite(sevenSeg[1],HIGH);
            digitalWrite(sevenSeg[2],HIGH);
            
            //digitalWrite(sevenSeg[3],HIGH);
            digitalWrite(sevenSeg[4],HIGH);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],HIGH);
            digitalWrite(sevenSeg[7],HIGH);
            break;
    case 2: digitalWrite(sevenSeg[0],LOW);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],HIGH);
            
           // digitalWrite(sevenSeg[3],HIGH); 
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],HIGH);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
    case 3: digitalWrite(sevenSeg[0],HIGH);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH); 
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],HIGH);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
    case 4: digitalWrite(sevenSeg[0],HIGH);
            digitalWrite(sevenSeg[1],HIGH);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH); 
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],HIGH);
            digitalWrite(sevenSeg[7],LOW);
            break;

    case 5: digitalWrite(sevenSeg[0],HIGH);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH); 
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],HIGH);
            break;
   case 6: digitalWrite(sevenSeg[0],LOW);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH); 
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],HIGH);
            break;
    case 7: digitalWrite(sevenSeg[0],HIGH);
            digitalWrite(sevenSeg[1],HIGH);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH);
            digitalWrite(sevenSeg[4],HIGH);
            
            digitalWrite(sevenSeg[5],HIGH);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
   case 8: digitalWrite(sevenSeg[0],LOW);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH);
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
   case 9: digitalWrite(sevenSeg[0],HIGH);
            digitalWrite(sevenSeg[1],LOW);
            digitalWrite(sevenSeg[2],LOW);
            
            //digitalWrite(sevenSeg[3],HIGH);
            digitalWrite(sevenSeg[4],LOW);
            
            digitalWrite(sevenSeg[5],LOW);
            digitalWrite(sevenSeg[6],LOW);
            digitalWrite(sevenSeg[7],LOW);
            break;
      
  }
  
}
void setup(){ 
  Serial.begin(9600);
 
  for(int i=0;i<8;i++){
    pinMode(sevenSeg[i],OUTPUT);
    digitalWrite(sevenSeg[i],HIGH);
  }
  pinMode(readPin,INPUT_PULLUP);
  
  
    
} 
void loop(){
  if(readStatus==0&&digitalRead(readPin)==LOW){
    number(random(1,7));
    readStatus=1;
  }else if(digitalRead(readPin)==HIGH&&readStatus==1){
    readStatus=0;
  }
  delay(50);
}
```
## Output

[Output Video](https://user-images.githubusercontent.com/95871421/151346319-a7156ad7-7eaf-4bc0-8a53-01b122e0b35b.mp4)


                                      **Thank You**
