#include <TimerOne.h>

int var = 0;
int ultimo = 0;

void setup() {
  // put your setup code here, to run once:
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(2, INPUT);
  Timer1.initialize(1000000);
  Timer1.attachInterrupt(timer);
  Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
  if(digitalRead(2) == HIGH){
    digitalWrite(12, HIGH);
    Serial.print("Valor: ");
    Serial.print(var);
    Serial.print("s");
    Serial.print(" Ultimo clique à: ");
    Serial.print(var-ultimo);
    Serial.println("s");

    ultimo = var;
    while(digitalRead(2) == HIGH) delay(10);
  }
  digitalWrite(12, LOW);
}

void timer(){
  digitalWrite(13, !digitalRead(13));
  var++;
}
