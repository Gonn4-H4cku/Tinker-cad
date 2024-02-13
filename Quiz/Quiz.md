
# Simple Quiz

To make a Quiz with 4 push buttons and a LCD display.
## Code
```cpp
#include <LiquidCrystal.h>
int sw1;
int sw2;
int sw3;
int sw4;

int crct = 0;
int wrng = 0;

const int rs = 12, en = 11, d4 = 10, d5 = 9, d6 = 8, d7 = 7;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);

void setup() 
{
  Serial.begin(9600);
  lcd.begin(16,2);
  
  pinMode(5,INPUT_PULLUP); //1st
  pinMode(3,INPUT_PULLUP); //2nd
  pinMode(4,INPUT_PULLUP); //3rd
  pinMode(2,INPUT_PULLUP);

  lcd.clear();

  lcd.print("Q1. what is 1+1?");
  delay(2000);
  lcd.clear();
  delay(1000);
  lcd.setCursor(0,0);
  lcd.print("1. 2");
  delay(1000);
  lcd.setCursor(11,0);
  lcd.print("2. 1");
  delay(1000);
  lcd.setCursor(0,1);
  lcd.print("3. 4");
  delay(1000);
  lcd.setCursor(11,1);
  lcd.print("4. 3");
  
  delay(3000);
  
  //lcd.clear();
  

  sw1 = digitalRead(5);
  sw2 = digitalRead(3);
  sw3 = digitalRead(4);
  sw4 = digitalRead(2);

  while(sw1 && sw2 && sw3 && sw4 != 0)
  {
     sw1 = digitalRead(5);
     sw2 = digitalRead(3);
     sw3 = digitalRead(4);
     sw4 = digitalRead(2);
  }
  
  if(sw1 == 0)
  {
    
    lcd.clear();
    delay(1000);
    lcd.setCursor(0,0);
    lcd.print("Correct answer!");
    crct++;
  }

  else
  {
    lcd.clear();
    delay(1000);
    lcd.setCursor(0,0);
    lcd.print("wrong answer!");
    wrng++;
  }
  
  delay(2000);

  lcd.clear();

  lcd.print("Q2. what is 2+2?");
  delay(2000);
  lcd.clear();
  delay(1000);
  lcd.setCursor(0,0);
  lcd.print("1. 5");
  delay(1000);
  lcd.setCursor(11,0);
  lcd.print("2. 4");
  delay(1000);
  lcd.setCursor(0,1);
  lcd.print("3. 7");
  delay(1000);
  lcd.setCursor(11,1);
  lcd.print("4. 8");
  
  delay(3000);
  
  
  sw1 = digitalRead(5);
  sw2 = digitalRead(3);
  sw3 = digitalRead(4);
  sw4 = digitalRead(2);

  while(sw1 && sw2 && sw3 && sw4 != 0)
  {
    sw1 = digitalRead(5);
    sw2 = digitalRead(3);
    sw3 = digitalRead(4);
    sw4 = digitalRead(2);
  }
  
  if(sw2 == 0)
  {
    lcd.clear();
    delay(1000);
    lcd.setCursor(0,0);
    lcd.print("Correct answer!");
    crct++;
  }

  else
  {
    lcd.clear();
    delay(1000);
    lcd.setCursor(0,0);
    lcd.print("Wrong answer!");
    wrng++;
  }

  delay(2000);

  lcd.clear();
  delay(1000);
  lcd.setCursor(0,0);
  lcd.print("Crct:");
  lcd.setCursor(6,0);
  lcd.print(crct);

  delay(1000);

  lcd.setCursor(0,1);
  lcd.print("Wrng:");
  lcd.setCursor(6,1);
  lcd.print(wrng);
}

     
void loop() 
{
// Any addition code 
}
```
### Simulation Link
[Quiz challenge](https://www.tinkercad.com/things/3xS25C5XWBW-tremendous-curcan)
