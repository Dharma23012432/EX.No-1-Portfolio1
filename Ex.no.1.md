
# NAME:DHARMALINGAM 
# REG NO:212223040037
 
# Aim: 
To design and implement a binary counter using a push button switch as input, a seven-segment display as output, and Arduino Uno as the controller. 
  
# Components Required: 
1.	Arduino Uno R3 board – 1 
 
2.	Common cathode Seven Segment Display – 1 
 
3.	Push Button switch – 1 
 
4.	220Ω resistors – 7 (for limiting current to seven segment LEDs) 
 
5.	Breadboard – 1 
 
6.	Jumper wires – as required 
 
7.	USB cable for Arduino Uno 
 
  
## Theory / Overview of Components: 
1.	Arduino Uno 
 
○ A microcontroller board based on ATmega328P. 
 
○ Provides 14 digital I/O pins and 6 analog inputs. 
 
○ Used here to control the seven-segment display and detect button presses. 
 
2.	Seven Segment Display (Common Cathode) 
 
○ An electronic display device for displaying decimal numbers (0–9). 
 
○ Composed of 7 LEDs (labeled a–g). 
 
○ By turning on/off combinations of LEDs, digits can be displayed. 
 
3.	Push Button Switch 
 
○ A momentary switch that changes state when pressed. 
 
○ Used here as input to increment the counter. 
 
  
# Connection Diagram (Description): 
●	Seven segment pins a–g connected to Arduino digital pins 2–8 via 220Ω resistors. 
 
●	Common cathode connected to GND. 
 
●	Push button one side connected to Arduino digital pin 9, other side to GND, with internal pull-up resistor enabled in code. 
 
 
 
 
 
## CODE:
```
int a = 2, b = 3, c = 4, d = 5, e = 6, f = 7, g = 8;
int switchPin = 9;
int count = 0;

void setup() {
  pinMode(a, OUTPUT);
  pinMode(b, OUTPUT);
  pinMode(c, OUTPUT);
  pinMode(d, OUTPUT);
  pinMode(e, OUTPUT);
  pinMode(f, OUTPUT);
  pinMode(g, OUTPUT);
  pinMode(switchPin, INPUT_PULLUP); 
}

void loop() {
  if (digitalRead(switchPin) == LOW) {  
    count++;
    if (count > 9) count = 0;  
    displayDigit(count);
    delay(300); 
  }
}

void clearDisplay() {
  digitalWrite(a, HIGH);
  digitalWrite(b, HIGH);
  digitalWrite(c, HIGH);
  digitalWrite(d, HIGH);
  digitalWrite(e, HIGH);
  digitalWrite(f, HIGH);
  digitalWrite(g, HIGH);
}

void displayDigit(int num) {
  clearDisplay();
  switch(num) {
    case 0: digitalWrite(a,LOW); digitalWrite(b,LOW); digitalWrite(c,LOW);
            digitalWrite(d,LOW); digitalWrite(e,LOW); digitalWrite(f,LOW); break;
    case 1: digitalWrite(b,LOW); digitalWrite(c,LOW); break;
   case 2: digitalWrite(a,LOW); digitalWrite(b,LOW); digitalWrite(d,LOW);
            digitalWrite(e,LOW); digitalWrite(g,LOW); break;
    case 3: digitalWrite(a,LOW); digitalWrite(b,LOW); digitalWrite(c,LOW);
            digitalWrite(d,LOW); digitalWrite(g,LOW); break;
    case 4: digitalWrite(b,LOW); digitalWrite(c,LOW); digitalWrite(f,LOW);
            digitalWrite(g,LOW); break;
    case 5: digitalWrite(a,LOW); digitalWrite(c,LOW); digitalWrite(d,LOW);
            digitalWrite(f,LOW); digitalWrite(g,LOW); break;
    case 6: digitalWrite(a,LOW); digitalWrite(c,LOW); digitalWrite(d,LOW);
            digitalWrite(e,LOW); digitalWrite(f,LOW); digitalWrite(g,LOW); break;
    case 7: digitalWrite(a,LOW); digitalWrite(b,LOW); digitalWrite(c,LOW); break;
    case 8: digitalWrite(a,LOW); digitalWrite(b,LOW); digitalWrite(c,LOW);
            digitalWrite(d,LOW); digitalWrite(e,LOW); digitalWrite(f,LOW); digitalWrite(g,LOW); break;
    case 9: digitalWrite(a,LOW); digitalWrite(b,LOW); digitalWrite(c,LOW);
            digitalWrite(d,LOW); digitalWrite(f,LOW); digitalWrite(g,LOW); break;
  }
}
 ```
## CIRCUIT DIAGRAM: 
<img width="954" height="659" alt="image" src="https://github.com/user-attachments/assets/ef196603-71e3-4ee8-86fe-d0eb0cd9c911" />

## OUTPUT: 
 <img width="941" height="570" alt="image" src="https://github.com/user-attachments/assets/a5290ebf-a4c7-4be3-841f-4a3563cdd1fd" />
 
## RESULT: 
  program to perform binary counter operation using switch, seven segment and 
Arduino controller is successfully executed 
