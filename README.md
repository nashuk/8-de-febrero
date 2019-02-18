# 8-de-febrero
Encendido y apagado de LEDs con delay controlado por entrada del usuario a monitor serial

int ledrojo = 4; 
int ledverde = 5; 
int ledazul = 3;
int t1;
int t2; 
int t3;

void setup() {
Serial.begin(9600);
Serial.println("¿Cuanto tiempo led rojo?");
while (Serial.available() == 0) {
}
t1=Serial.parseInt();
while (Serial.available()>0){
Serial.read();  
}
pinMode(ledrojo, OUTPUT);
  
Serial.println("¿Cuanto tiempo led azul?");
while (Serial.available() == 0) {
}
t2=Serial.parseInt();
while (Serial.available()>0){
Serial.read();  
}
pinMode(ledazul, OUTPUT);
  
Serial.println("¿Cuanto tiempo led verde?");
while (Serial.available() == 0) {
}
t3=Serial.parseInt();
while (Serial.available()>0){
Serial.read();  
}
pinMode(ledverde, OUTPUT);
}

void loop() {
digitalWrite(ledrojo,HIGH);
delay (t1);
digitalWrite(ledrojo,LOW);
delay (t1);
digitalWrite(ledverde,HIGH);
delay (t2);
digitalWrite(ledverde,LOW);
delay (t2);
digitalWrite(ledazul,HIGH);
delay (t3);
digitalWrite(ledazul,LOW);
delay (t3);

}
