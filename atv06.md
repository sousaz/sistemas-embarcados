void setup() {
  // put your setup code here, to run once:
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(2, INPUT);
  pinMode(3, INPUT);
  Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
  int pot0 = analogRead(A0);
  int pot1 = analogRead(A1);
  Serial.print("pot0: ");
  Serial.println(pot0);
  Serial.print("pot1: ");
  Serial.println(pot1);
}
