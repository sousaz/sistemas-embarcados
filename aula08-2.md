void setup() {
  // put your setup code here, to run once:
  pinMode(7, INPUT);
  Serial.begin(9600);
}

int led = 0;
void loop() {
  // put your main code here, to run repeatedly
  if(digitalRead(7)== HIGH) {
    led++;
    if(led > 3) led = 0;
    while(digitalRead(7) == HIGH) delay(10);
  }
  Serial.write(led);
}
