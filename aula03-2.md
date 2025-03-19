void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(2, INPUT);
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
}

int a = 0;

void loop() {
  Serial.println(a);
  if (digitalRead(2) == HIGH) {
    a++;
    while (digitalRead(2) == HIGH) delay(10);
  }
  if(a == 1) digitalWrite(11, HIGH);
  if(a == 2) digitalWrite(12, HIGH);
  if(a == 3) digitalWrite(13, HIGH);
  if(a > 3){
    digitalWrite(11, LOW);
    digitalWrite(12, LOW);
    digitalWrite(13, LOW);
    a = -1;
  }

}