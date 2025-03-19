void setup() {
  // put your setup code here, to run once:
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(2, INPUT);
  pinMode(3, INPUT);
  Serial.begin(9600);
}
int interval = 0;
void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(13, true);
  delay(interval);
  digitalWrite(13, false);
  delay(interval);

  if(digitalRead(2) == HIGH && digitalRead(3) == LOW){
    interval += 100;
    Serial.println(interval);
    while(digitalRead(2) == HIGH) delay(10);
  }

  if(digitalRead(3) == HIGH && digitalRead(2) == HIGH){
    interval -= 100;
    Serial.println(interval);
    while(digitalRead(2) == HIGH) delay(10);
  }

  if(digitalRead(2) == HIGH && digitalRead(3) == HIGH){
    interval = 1000;
    Serial.println(interval);
    while(digitalRead(2) == HIGH) delay(10);
  }
}
