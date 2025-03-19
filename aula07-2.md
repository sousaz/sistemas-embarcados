void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(9, OUTPUT);
  pinMode(10, INPUT);
  pinMode(11, INPUT);

}
int luz = 0;
int inc = 50;

void loop() {
  // put your main code here, to run repeatedly:
  if(digitalRead(10) == HIGH){
    luz = luz + inc;
    if(luz > 255) luz = 255;
    while (digitalRead(10) == HIGH) delay(10);
  }
  if(digitalRead(11) == HIGH){
    luz = luz - inc;
    if(luz < 0) luz = 0;
    while (digitalRead(11) == HIGH) delay(10);
  }
  
  Serial.println(luz);
  analogWrite(9, luz);

}
