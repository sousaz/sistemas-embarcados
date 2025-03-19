void setup() {
  // put your setup code here, to run once:
  pinMode(13, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(2, INPUT);
  pinMode(3, INPUT);
  Serial.begin(9600);
}
int pot0;
void loop() {
  // put your main code here, to run repeatedly:
  pot0 = analogRead(A0);
  if(digitalRead(3) == HIGH){
    analogWrite(11, pot0);
    Serial.println("Entrou");
  }
}
