# Experiment 3 : LED Chasing Effect
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

