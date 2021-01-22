#define light A0
#define an A1
int v=7;
int val=0 , value=0,mois=0  ;
void setup() {
 Serial.begin(9600);
 pinMode(v,OUTPUT);
 pinMode(light,INPUT);
}
void loop() {
val=analogRead(light);
value=analogRead(an);
 mois=map(value,1017,100,0,100);
Serial.print("Soil moisture = %");
 Serial.println(mois);
 Serial.print("light sensor : ");
 Serial.println(val);

 if(val>30){
  if(mois<50){
  digitalWrite(v,HIGH);
  }
  else{
    digitalWrite(v, LOW);  
    }
  }
  else
 {
  digitalWrite(v,LOW); 
 }
 delay(1000);
}
