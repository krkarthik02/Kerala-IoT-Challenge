# Experiment 2 : Traffic Light

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

