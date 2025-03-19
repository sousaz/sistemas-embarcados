void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(9, OUTPUT);

}
int ent;
int sai;

void loop() {
  // put your main code here, to run repeatedly:
  ent = analogRead(A0);
  sai = map(ent, 0, 1023, 0, 255);
  analogWrite(9, sai);
}