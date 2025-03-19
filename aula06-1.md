float temperatura;
float voltagem;
float desejada;

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(13, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  voltagem = analogRead(A1);
  desejada = analogRead(A0) / 10;
  // temperatura = (5 * voltagem * 100) / 1023;
  temperatura = (voltagem * 5 / 1023) / 0.01;
  Serial.print("Temperatura desejada: ");
  Serial.print(desejada);
  Serial.print("° -> ");
  Serial.print("Temperatura real: ");
  Serial.print(temperatura);
  Serial.print("° -> ");
  if(temperatura > desejada){
    digitalWrite(13, HIGH);
    Serial.println("ligado");
  }
  else{
    digitalWrite(13, LOW);
    Serial.println("desligado");
  }
}
