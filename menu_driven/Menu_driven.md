
# Menu Driven

Make an easy menu driven code with ESP-32 and Oled Display.
## Code
```cpp
#include  <Wire.h>
#include  <Adafruit_GFX.h>
#include  <Adafruit_SSD1306.h>
#define OLED_RESET -1
Adafruit_SSD1306 display(128,  64,  &Wire, OLED_RESET);
int i =  20;
int val;

void  setup()  {
display.begin(SSD1306_SWITCHCAPVCC,  0x3C);
display.display();
delay(1000);  // Wait for 2 seconds
display.clearDisplay();
pinMode(4,  INPUT_PULLUP);
display.setTextSize(2);
//display.setTextColor(SSD1306_WHITE, SSD1306_BLACK);
//display.setTextColor(SSD1306_WHITE);
display.setTextColor(SSD1306_INVERSE);
display.setCursor(40,  0);
display.println("MENU");
display.setTextSize(1);
display.setTextColor(SSD1306_WHITE);
display.setCursor(0,  20);
display.println(" banana");
display.setCursor(0,  35);
display.println(" apple");
display.setCursor(0,  50);
display.println(" grapes");

display.display();

}
void  loop()  {
val =  digitalRead(4);
delay(20);
while(val !=  1)
{
if(i ==  60  || i >  60)
{
i =  20;
}
display.clearDisplay();
display.setTextSize(2);
display.setTextColor(SSD1306_INVERSE);
display.setCursor(40,  0);
display.println("MENU");
display.setTextSize(1);
display.setTextColor(SSD1306_WHITE);
display.setCursor(0,  20);
display.println(" banana");
display.setCursor(0,  35);
display.println(" apple");
display.setCursor(0,  50);
display.println(" grapes");
display.setCursor(0,i);
display.print(">");
i= i+15;
delay(500);
val =  digitalRead(4);
display.display();
}
//delay(5000); // Delay for 5 seconds
//display.clearDisplay();
}
```
### Simulation Link
[Menu Driven](https://wokwi.com/projects/365445098369199105)
