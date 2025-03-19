void setup() {
  // put your setup code here, to run once:
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(2, INPUT);
  pinMode(3, INPUT);
}
// Botão de 4 pinos, bota em pé
void loop() {
  // put your main code here, to run repeatedly:
  if(digitalRead(2) == HIGH || digitalRead(3) == HIGH){
    digitalWrite(13, true);
  } else {
    digitalWrite(13, false);
  }

  if(digitalRead(2) == HIGH && digitalRead(3) == HIGH){
    digitalWrite(12, true);
    digitalWrite(11, true);
  } else {
    digitalWrite(12, false);
    digitalWrite(11, false);
  }

  
}
