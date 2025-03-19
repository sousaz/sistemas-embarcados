void setup() {
  // put your setup code here, to run once:
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(2, INPUT);
  pinMode(3, INPUT);
  Serial.begin(9600);
}
int pot0;
int pot1;
int sai0;
int sai1;
void loop() {
  // put your main code here, to run repeatedly:
  pot0 = analogRead(A0);
  pot1 = analogRead(A1);
  sai0 = map(pot0, 0, 1023, 0, 255);
  sai1 = map(pot1, 0, 1023, 0, 255);
  analogWrite(10, sai0);
  analogWrite(11, sai1);
}
