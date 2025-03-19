void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(2, INPUT);
}

int a;

void loop() {
  Serial.println(a);
  if (digitalRead(2) == HIGH) {
    a++;
    // flip flop
    while (digitalRead(2) == HIGH) delay(10);
  }
}