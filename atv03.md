void setup() {
  // put your setup code here, to run once:
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(2, INPUT);
  pinMode(3, INPUT);
  Serial.begin(9600);
}
// Botão de 4 pinos, bota em pé
int direction = -1;
void loop() {
  // put your main code here, to run repeatedly:
  if(digitalRead(2) == HIGH){
    direction = 1;
    Serial.println(direction);
  }
  if(digitalRead(3) == HIGH){
    direction = -1;
    Serial.println(direction);
  }
  if(direction == 1){
    digitalWrite(11, false);
    digitalWrite(13, true);
    delay(300);
    digitalWrite(13, false);
    digitalWrite(12, true);
    delay(300);
    digitalWrite(12, false);
    digitalWrite(11, true);
    delay(300);
  }

  if(direction == -1){
    digitalWrite(11, true);
    digitalWrite(13, false);
    digitalWrite(12, false);
    delay(300);
    digitalWrite(12, true);
    digitalWrite(11, false);
    delay(300);
    digitalWrite(13, true);
    digitalWrite(12, false);
    delay(300);
  }

}
