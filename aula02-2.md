void setup() {
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
}

int d = 50;
void loop() {
  digitalWrite(11, LOW);
  digitalWrite(13, HIGH);
  delay(d);
  digitalWrite(13, LOW);
  digitalWrite(12, HIGH);
  delay(d);
  digitalWrite(12, LOW);
  digitalWrite(11, HIGH);
  delay(d);
}
