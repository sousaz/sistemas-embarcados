<<<<<<< HEAD
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
=======
#include <Servo.h>

Servo myservo;

void setup() {
  myservo.attach(9);

>>>>>>> 02cf72f96292bc8398414f6d161d5e0de9c8b4ac
}

void loop() {
  // put your main code here, to run repeatedly:
<<<<<<< HEAD
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
=======
  myservo.write(180);
  delay(1000);
  myservo.write(90);
  delay(1000);
  myservo.write(0);
  delay(1000);
>>>>>>> 02cf72f96292bc8398414f6d161d5e0de9c8b4ac
}
