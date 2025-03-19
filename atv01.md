void setup() {
  // put your setup code here, to run once:
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(2, INPUT);
  pinMode(3, INPUT);
}
// Botão de 4 pinos, bota em pé
int leds = 0;
void loop() {
  // put your main code here, to run repeatedly:
  if(digitalRead(3) == HIGH){
    leds++;
    if(leds > 3)
      leds = 3;
    while(digitalRead(3) == HIGH) delay(10);
  }
  if(digitalRead(2) == HIGH){
    leds--;
    if(leds < 0)
      leds = 0;
    while(digitalRead(2) == HIGH) delay(10);
  }
  if(leds == 0){
    digitalWrite(13, false);
    digitalWrite(12, false);
    digitalWrite(11, false);
  }

  if(leds == 1){
    digitalWrite(13, true);
    digitalWrite(12, false);
    digitalWrite(11, false);
  }

  if(leds == 2){
    digitalWrite(13, true);
    digitalWrite(12, true);
    digitalWrite(11, false);
  }

  if(leds == 3){
    digitalWrite(13, true);
    digitalWrite(12, true);
    digitalWrite(11, true);
  }
}
