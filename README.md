# 1
IOT Project
#include <LiquidCrystal.h> 
const int rs = 12,en=11,d4=5,d5=4,d6=3,d7=2;
LiquidCrystal lcd(rs,en,d4,d5,d6,d7);
const int ProxSensor=8;
int buzzer=9;
int charger=13;
void setup()
{                
  // initialize the digital pin as an output.
  // Pin 13 has an LED connected on most Arduino boards:
  pinMode(charger, OUTPUT); 
  pinMode(buzzer, OUTPUT); 
  lcd.begin(16,2);    
  //Pin 2 is connected to the output of proximity sensor
  pinMode(ProxSensor,INPUT);
  lcd.setCursor(0,0);
  lcd.print("    COIN BASED ");
  lcd.setCursor(0,1);
  lcd.print("  MOBILE CHARGER");
  delay(5000);
  lcd.clear();
  
}

void loop() 
{
  
  
  if(digitalRead(ProxSensor)==0)      //Check the sensor output
  {
    lcd.clear();
    lcd.print("power port on");
    lcd.setCursor(0,1);
    lcd.println("connect your cell");
    delay(5000);
     lcd.clear();
    lcd.print("1 rupee=5min"); 
    lcd.setCursor(0,1);
    lcd.println("charging...     ");   
    digitalWrite(charger, HIGH);   // set the LED on
    delay(5000);delay(5000);delay(5000);delay(5000);
    delay(5000);delay(5000);delay(5000);delay(5000);
    delay(5000);delay(5000);delay(5000);delay(5000);
    delay(5000);delay(5000);delay(5000);delay(5000);
    lcd.clear();
    digitalWrite(buzzer, HIGH);   // set the LED on
    delay(500);
    digitalWrite(buzzer, LOW); 
    digitalWrite(buzzer, HIGH);   // set the LED on
    delay(500);
    digitalWrite(buzzer, LOW);
  }
  else
  {
     lcd.setCursor(0,0);
     lcd.print("please insert");
     lcd.setCursor(0,1);
     lcd.println("1-rupee coin     ");
    digitalWrite(13, LOW);    // set the LED off
  }
  delay(100);              // wait for a second
}


