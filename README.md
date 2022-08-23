# internet-of-things





1.led program<br>
https://wokwi.com/projects/333796023666213458<br>
2.hello world LCD<br>
https://wokwi.com/projects/334974852517593683<br>
3.RGB 1 program,<br>
https://wokwi.com/projects/333800114460033619<br>
.RGB 2 program<br>
https://wokwi.com/projects/333804661453619796<br>
4.servo<br>
https://wokwi.com/projects/334978083920544339<br>
5. potentiometer servo<br>
https://wokwi.com/projects/334980717322699348<br>
6.Buzzer  with resistor<br>
https://wokwi.com/projects/335608903281672788<br>
7.Buzzer with push button<br>
https://wokwi.com/projects/335068632179540562<br>
8.ultrasonic senor<br>
https://wokwi.com/projects/335071500453282387<br>
9.ultrasonic using buzzer <br>
https://wokwi.com/projects/335605272348197460<br>
10.ultrasonic sensor with buzzer with bulb with beep in 20  inch distance<br>
https://wokwi.com/projects/335611740136931924<br>
11.potentiometer with LED<br>
https://wokwi.com/projects/335701647955067474<br>




##############################################################################################################################################################################################################################################################################################################################################
According to lab list:


program:  LED WITH BUZZER
https://wokwi.com/projects/337603984278684242

program: LED WITH PUSH BUTTON
https://wokwi.com/projects/337604223773442644

program: DHT 22 sensor
https://wokwi.com/projects/337604223773442644

program 4:  Relay with  aurdino i.e servo motor with button
https://wokwi.com/projects/337604417075282515

program5: LCD DHT 22


program 6: 



program7 :FMS
#include "ThingSpeak.h"
#include <ESP8266WiFi.h>
const int trigPin1 = D1;
const int echoPin1 = D2;
#define redled D3
#define grnled D4
//#define BUZZER D5 //buzzer pin
unsigned long ch_no = 1838852;//Replace with Thingspeak Channel number
const char * write_api = "B09P3G8RR3PGTIT6";//Replace with Thingspeak write API
char auth[] = "mwa0000027193634";
char ssid[] = "m";
char pass[] = "Csdept@1234";
unsigned long startMillis;
unsigned long currentMillis;
const unsigned long period = 10000;
WiFiClient  client;
long duration1;
int distance1;
void setup()
{
  pinMode(trigPin1, OUTPUT);
  pinMode(echoPin1, INPUT);
  pinMode(redled, OUTPUT);
  pinMode(grnled, OUTPUT);
  digitalWrite(redled, LOW);
  digitalWrite(grnled, LOW);
  Serial.begin(115200);
  WiFi.begin(ssid, pass);
  while (WiFi.status() != WL_CONNECTED)
  {
    delay(500);
    Serial.print(".");
  }
  Serial.println("WiFi connected");
  Serial.println(WiFi.localIP());
  ThingSpeak.begin(client);
  startMillis = millis();  //initial start time
}
void loop()
{
  digitalWrite(trigPin1, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin1, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin1, LOW);
  duration1 = pulseIn(echoPin1, HIGH);
  distance1 = duration1 * 0.034 / 2;
  Serial.println(distance1);
  delay(1500);
  if (distance1 <= 10)
  {
    digitalWrite(D3, HIGH);
    //tone(BUZZER, 300);
    digitalWrite(D4, LOW);
    delay(1500);
    //noTone(BUZZER);
  }
  else
  {
    digitalWrite(D4, HIGH);
    digitalWrite(D3, LOW);
  }
  currentMillis = millis();
  if (currentMillis - startMillis >= period)
  {
    ThingSpeak.setField(1, distance1);
    ThingSpeak.writeFields(ch_no, write_api);
    startMillis = currentMillis;
  }
}














































#####################################################################################################################################################################################################################################################################################################################################################################################################################################################################################################################

DONE WITH HARDWAre


1. NORMAL LED<br>
https://wokwi.com/projects/338238862865203794<br>

ESP 32<br>
https://wokwi.com/projects/338239531456135764<br>

2. 3 COLOR  LED<br>
https://wokwi.com/projects/338239027336446546 <br>

ESP32<br>
https://wokwi.com/projects/338239619008037458<br>

3.ULTRA SONIC SENSOR  ### esp22 used ####<br>
https://wokwi.com/projects/338239077744640594<br>

4.DHT22(TEMP AND HUMIDITY SENSAR)  #### library shoud be addded  ####<br>
https://wokwi.com/projects/338239158455632467<br>


###############################################################################################################################################################
pgm1:LED
https://wokwi.com/projects/340778755553231444
pgm2:3LED
https://wokwi.com/projects/340778833486545490
pgm3:RGB LED
https://wokwi.com/projects/340778937020842579
pgm4:LIQUID CRYSTAL
https://wokwi.com/projects/340778997511094868
pgm5:SERVOMOTOR+PUSHBUTTON
https://wokwi.com/projects/340779126089581140
pgm6:SERVOMOTOR +SLIDING POTENTIOMETER
https://wokwi.com/projects/340779191873045074
pgm7:BUZZER+PUSHBUTTON
https://wokwi.com/projects/340779285654536788
pgm8:ULTRASONIC SENSOR+BUZZER
https://wokwi.com/projects/340779345403445842
pgm9:POTENTIOMETER+LED
https://wokwi.com/projects/340779415779672658
pgm10:DHT22(HUMIDITY SENSOR)
https://wokwi.com/projects/340779510866641491
pgm11:LDR
https://wokwi.com/projects/340779572029030994
pgm12:LDR+LED
https://wokwi.com/projects/340779632905159251
pgm13:LDR_CHASER
https://wokwi.com/projects/340779679531139667
