void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(7, INPUT);
}
bool ligado = false;

void loop() {
  // put your main code here, to run repeatedly:
  if(digitalRead(7) == HIGH){
    ligado = !ligado;
    while(digitalRead(7) == HIGH) delay(10);
  }
  Serial.write(ligado);
}
