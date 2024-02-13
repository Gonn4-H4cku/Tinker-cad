
# Stop Watch

To make a simple Stop watch with a start and stop button.
## Code
```cpp
#include <LiquidCrystal.h>
int minute = 0;
int seconds=0;
int d2,d3;

const int rs = 12, en = 11, d4 = 10, d5 = 9, d6 = 8, d7 = 7;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);

void setup()
{
  Serial.begin(9600);
  lcd.begin(16,2);
  pinMode(3,INPUT_PULLUP);//start
  pinMode(2,INPUT_PULLUP);//stop
  lcd.clear();
  lcd.setCursor(0,0);
  lcd.print("Stop Watch : ");
}

void loop()
{
  d2 = digitalRead(2);
  d3 = digitalRead(3);
  
  if(digitalRead(3) !=1)
  {
    while(d2 ==1)
    {
      d2 = digitalRead(2);
      
      lcd.setCursor(0,1);
      lcd.print("00:00");
    //delay(100);
    if(seconds == 60)
    {
        
        minute++;
        seconds = 0;
          
        if(minute<10)
      {
        
        lcd.setCursor(1,1);
        lcd.print(minute);
        lcd.setCursor(4,1);
        lcd.print(0);  
        //delay(10);  
        if(seconds<10) 
        {
        
        lcd.setCursor(4,1);
        lcd.print(seconds);
        //delay(1);  
        }
      
        else
        {
        lcd.setCursor(3,1);
        lcd.print(seconds);
        //delay(1);
        }
        
      }
      
      else
      {
        
        lcd.setCursor(0,1);
        lcd.print(minute);
        lcd.setCursor(4,1);
        lcd.print(0);
        //delay(10);
        if(seconds<10) 
        {
        
        lcd.setCursor(4,1);
        lcd.print(seconds);
        //delay(1);  
        }
      
        else
        {
        lcd.setCursor(3,1);
        lcd.print(seconds);
        //delay(1);  
        }
      }
        
    }

    else
    {
      d2 = digitalRead(2);
      if(minute<10)
      {
        
        lcd.setCursor(1,1);
        lcd.print(minute);
        lcd.setCursor(4,1);
        lcd.print(0);
        //delay(10);
        if(seconds<10) 
        {
        
        lcd.setCursor(4,1);
        lcd.print(seconds);
        //delay(1);  
        }
      
        else
        {
        lcd.setCursor(3,1);
        lcd.print(seconds);
        //delay(1);  
        }
        
      }
      
      else
      {
        lcd.setCursor(0,1);
        lcd.print(minute);
        lcd.setCursor(4,1);
        lcd.print(0);
        //delay(10);
        if(seconds<10) 
        {
        
        lcd.setCursor(4,1);
        lcd.print(seconds);
        //delay(1);  
        }
      
        else
        {
        lcd.setCursor(3,1);
        lcd.print(seconds);
        //delay(1);  
        }
      }
            
    }
      
      seconds++;
      
      d2 = digitalRead(2);
      delay(1000);
     
    }   
  }
}
```
### Simulation Link
[Stop Watch](https://www.tinkercad.com/things/4kJY8CWSFIS-exquisite-blad-albar)
