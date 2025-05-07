#include <Servo.h>

Servo myservo;

void setup() {
  myservo.attach(9);
  Serial.begin(9600);
}

int pot;
void loop() {
  // put your main code here, to run repeatedly:
  pot = analogRead(A0);

  myservo.write(map(pot, 0, 1023, 0, 180));
}
