void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(9, OUTPUT);
  pinMode(10, INPUT);
  pinMode(11, INPUT);

}
int luz = 0;
int inc = 1;

void loop() {
  // put your main code here, to run repeatedly:
  if(digitalRead(10) == HIGH){
    while (luz < 255){
      luz = luz + inc;
      if(luz > 255) luz = 255;
      analogWrite(9, luz);
      delay(10); 
    }
  }
  if(digitalRead(11) == HIGH){
    while (luz > 0){
      luz = luz - inc;
      if(luz < 0) luz = 0;
      analogWrite(9, luz);
      delay(10); 
    }
  }
  
  Serial.println(luz);
  analogWrite(9, luz);
}
