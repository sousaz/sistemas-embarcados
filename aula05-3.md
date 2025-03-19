float pot;
float volt;

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  pot = analogRead(A0);
  volt = pot * 100 / 1023;
  for(int i=0; i<int(volt); i++){
    Serial.print(" ");
  }
  Serial.println("*");
}
