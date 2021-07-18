# fourth-task
برمجة حساس المسافة 
يعمل الليد عندما يقف الشخص امام الحساس لمدة 3 ثواني
كود الأردوينو :
const int trigPin = 5;
const int echoPin = 4;
const int ledPin = 10;
long duration;
int distance;


void setup()
{
pinMode(trigPin, OUTPUT); 
pinMode(echoPin, INPUT); 
pinMode(ledPin, OUTPUT);
Serial.begin(9600); 
}


void loop()
{
  while(getdistance() > 40)  {  }
  int starttime= millis();
  while (getdistance()< 40){
    int currenttime = millis();
   if(currenttime - starttime > 3000 )
   {
   digitalWrite (ledPin, HIGH);
     delay (2000);
      digitalWrite (ledPin, LOW);
     
   break;
   }
 
  }
}

int getdistance()
 {
   digitalWrite(trigPin, LOW);
delayMicroseconds(2);
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);
duration = pulseIn(echoPin, HIGH);
 distance= duration*0.034/2;
return distance;
}

الدائرة في التنكركاد :
https://www.tinkercad.com/things/a3b2cTiiwDj-tremendous-fyyran-allis/editel?sharecode=kRfLhiMK6vCdNfFNVQV-to8W8ZjCniZiuvPTR7BXclc
