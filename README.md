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
According to lab list:<br>


program:  LED WITH BUZZER<br>
https://wokwi.com/projects/337603984278684242<br>

program: LED WITH PUSH BUTTON<br>
https://wokwi.com/projects/337604223773442644<br>

program: DHT 22 sensor<br>
https://wokwi.com/projects/337604223773442644<br>

program 4:  Relay with  aurdino i.e servo motor with button<br>
https://wokwi.com/projects/337604417075282515<br>

program5: LCD DHT 22<br>


program 6: <br>



program7 :FMS<br>
#include "ThingSpeak.h"<br>
#include <ESP8266WiFi.h><br>
const int trigPin1 = D1;<br>
const int echoPin1 = D2;<br>
#define redled D3<br>
#define grnled D4<br>
//#define BUZZER D5 //buzzer pin<br>
unsigned long ch_no = 1838852;//Replace with Thingspeak Channel number<br>
const char * write_api = "B09P3G8RR3PGTIT6";//Replace with Thingspeak write API<br>
char auth[] = "mwa0000027193634";<br>
char ssid[] = "m";<br>
char pass[] = "Csdept@1234";<br>
unsigned long startMillis;<br>
unsigned long currentMillis;<br>
const unsigned long period = 10000;<br>
WiFiClient  client;<br>
long duration1;<br>
int distance1;<br>
void setup()<br>
{<br>
  pinMode(trigPin1, OUTPUT);<br>
  pinMode(echoPin1, INPUT);<br>
  pinMode(redled, OUTPUT);<br>
  pinMode(grnled, OUTPUT);<br>
  digitalWrite(redled, LOW);<br>
  digitalWrite(grnled, LOW);<br>
  Serial.begin(115200);<br>
  WiFi.begin(ssid, pass);<br>
  while (WiFi.status() != WL_CONNECTED)<br>
  {<br>
    delay(500);<br>
    Serial.print(".");<br>
  }<br>
  Serial.println("WiFi connected");<br>
  Serial.println(WiFi.localIP());<br>
  ThingSpeak.begin(client);<br>
  startMillis = millis();  //initial start time<br>
}<br>
void loop()<br>
{<br>
  digitalWrite(trigPin1, LOW);<br>
  delayMicroseconds(2);<br>
  digitalWrite(trigPin1, HIGH);<br>
  delayMicroseconds(10);<br>
  digitalWrite(trigPin1, LOW);<br>
  duration1 = pulseIn(echoPin1, HIGH);<br>
  distance1 = duration1 * 0.034 / 2;<br>
  Serial.println(distance1);<br>
  delay(1500);<br>
  if (distance1 <= 10)<br>
  {<br>
    digitalWrite(D3, HIGH);<br>
    //tone(BUZZER, 300);<br>
    digitalWrite(D4, LOW);<br>
    delay(1500);<br>
    //noTone(BUZZER);<br>
  }<br>
  else<br>
  {<br>
    digitalWrite(D4, HIGH);<br>
    digitalWrite(D3, LOW);
  }
  currentMillis = millis();
  if (currentMillis - startMillis >= period)
  {
    ThingSpeak.setField(1, distance1);
    ThingSpeak.writeFields(ch_no, write_api);
    startMillis = currentMillis;
    }<br>
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

#############################LAB EXAM PROGRAMS#################################################################################################################
###############################################################################################################################################################
pgm1:LED<br>
https://wokwi.com/projects/340778755553231444<br>
pgm2:3LED<br>
https://wokwi.com/projects/340778833486545490<br>
pgm3:RGB LED<br>
https://wokwi.com/projects/340778937020842579<br>
pgm4:LIQUID CRYSTAL<br>
https://wokwi.com/projects/340778997511094868<br>
pgm5:SERVOMOTOR+PUSHBUTTON<br>
https://wokwi.com/projects/340779126089581140<br>
pgm6:SERVOMOTOR +SLIDING POTENTIOMETER<br>
https://wokwi.com/projects/340779191873045074<br>
pgm7:BUZZER+PUSHBUTTON<br>
https://wokwi.com/projects/340779285654536788<br>
pgm8:ULTRASONIC SENSOR+BUZZER<br>
https://wokwi.com/projects/340779345403445842<br>
pgm9:POTENTIOMETER+LED<br>
https://wokwi.com/projects/340779415779672658<br>
pgm10:DHT22(HUMIDITY SENSOR)<br>
https://wokwi.com/projects/340779510866641491<br>
pgm11:LDR<br>
https://wokwi.com/projects/340779572029030994<br>
pgm12:LDR+LED<br>
https://wokwi.com/projects/340779632905159251<br>
pgm13:LDR_CHASER<br>
https://wokwi.com/projects/340779679531139667<br>
