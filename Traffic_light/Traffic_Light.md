# Traffic Light

To make a simulation of Traffic Light with 3 LED's and a push button.
Each time the push button is pressed next LED will Turn ON.

## Code
```cpp
 void setup()
{
  pinMode(7,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(5,OUTPUT);
  //pinMode(4,INPUT);
  pinMode(8,INPUT_PULLUP);
}

void loop()
{
  while(digitalRead(8) == HIGH)
  {
    digitalWrite(7,HIGH);
    digitalWrite(6,LOW);
    digitalWrite(5,LOW);
   }
  delay(1000);
  digitalWrite(7,LOW);
  digitalWrite(6,LOW);
  digitalWrite(5,LOW);
  
  
  while(digitalRead(8) == HIGH)
  {
    digitalWrite(7,LOW);
    digitalWrite(6,HIGH);
    digitalWrite(5,LOW);
  }
  delay(1000);
  digitalWrite(7,LOW);
  digitalWrite(6,LOW);
  digitalWrite(5,LOW);
  
  while(digitalRead(8) == HIGH)
  {
    digitalWrite(7,LOW);
    digitalWrite(6,LOW);
    digitalWrite(5,HIGH);
  }
  delay(1000);
  digitalWrite(7,LOW);
  digitalWrite(6,LOW);
  digitalWrite(5,LOW);
  }
```
### Simulation Link
[Traffic Light](https://www.tinkercad.com/things/aTaVTlAkoNB-traffic-light)
