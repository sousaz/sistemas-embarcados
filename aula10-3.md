#include <Servo.h>

Servo myservo;
Servo myservo1;

void setup() {
  myservo.attach(9);
  myservo1.attach(10);
  Serial.begin(9600);
  pinMode(13, INPUT);
}

int pot = 0;
int but = 0;
void loop() {
  // put your main code here, to run repeatedly:
  pot = analogRead(A0);

  myservo.write(map(pot, 0, 1023, 0, 180));

  if(digitalRead(13) == HIGH){
    but += 20;
    if(but > 180) but = 0;
    myservo1.write(but);
    while(digitalRead(13) == HIGH) delay(100);
  }
}
