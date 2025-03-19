void setup() {
  // put your setup code here, to run once:
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(2, INPUT);
  pinMode(3, INPUT);

}

void apagar(){
  digitalWrite(13, LOW);
  digitalWrite(12, LOW);
  digitalWrite(11, LOW);
  digitalWrite(10, LOW);
  digitalWrite(9, LOW);
  digitalWrite(8, LOW);
  digitalWrite(7, LOW);
}

void zero(){
  apagar();
  digitalWrite(13, HIGH);
  digitalWrite(12, HIGH);
  digitalWrite(11, HIGH);
  digitalWrite(10, HIGH);
  digitalWrite(9, HIGH);
  digitalWrite(8, HIGH);
}

void um(){
  apagar();
  digitalWrite(12, HIGH);
  digitalWrite(11, HIGH);
}

void dois(){
  apagar();
  digitalWrite(13, HIGH);
  digitalWrite(12, HIGH);
  digitalWrite(7, HIGH);
  digitalWrite(9, HIGH);
  digitalWrite(10, HIGH);
}

void tres(){
  apagar();
  digitalWrite(13, HIGH);
  digitalWrite(12, HIGH);
  digitalWrite(11, HIGH);
  digitalWrite(10, HIGH);
  digitalWrite(7, HIGH);

}

void quatro(){
  apagar();
  digitalWrite(12, HIGH);
  digitalWrite(11, HIGH);
  digitalWrite(7, HIGH);
  digitalWrite(8, HIGH);
}

void cinco(){
  apagar();
  digitalWrite(13, HIGH);
  digitalWrite(8, HIGH);
  digitalWrite(7, HIGH);
  digitalWrite(11, HIGH);
  digitalWrite(10, HIGH);
}

void seis(){
  apagar();
  digitalWrite(13, HIGH);
  digitalWrite(8, HIGH);
  digitalWrite(7, HIGH);
  digitalWrite(9, HIGH);
  digitalWrite(10, HIGH);
  digitalWrite(11, HIGH);
}

void sete(){
  apagar();
  digitalWrite(13, HIGH);
  digitalWrite(12, HIGH);
  digitalWrite(11, HIGH);
}

void oito(){
  apagar();
  digitalWrite(13, HIGH);
  digitalWrite(12, HIGH);
  digitalWrite(11, HIGH);
  digitalWrite(10, HIGH);
  digitalWrite(9, HIGH);
  digitalWrite(8, HIGH);
  digitalWrite(7, HIGH);
}

void nove(){
  apagar();
  digitalWrite(13, HIGH);
  digitalWrite(12, HIGH);
  digitalWrite(11, HIGH);
  digitalWrite(8, HIGH);
  digitalWrite(7, HIGH);
}

int counter = 0;

void loop() {
  // put your main code here, to run repeatedly:
  if(digitalRead(2) == HIGH){
    counter++;
    if(counter > 9) counter = 9;
    while (digitalRead(2) == HIGH) delay(10);
  }

  if(digitalRead(3) == HIGH){
    counter--;
    if(counter < 0) counter = 0;
    while (digitalRead(3) == HIGH) delay(10);
  }

  switch(counter){
    case 0:
      zero();
      break;
    case 1:
      um();
      break;
    case 2:
      dois();
      break;
    case 3:
      tres();
      break;
    case 4:
      quatro();
      break;
    case 5:
      cinco();
      break;
    case 6:
      seis();
      break;
    case 7:
      sete();
      break;
    case 8:
      oito();
      break;
    case 9:
      nove();
      break;
  }

}