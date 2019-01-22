# doppler
#include <SoftwareSerial.h>
int doppler; // sensor MV podpiety do digpina#5
int senster = 1; // nasz senster podpiety kabelkiem do tx1
float dopplerVals[] = {0,0}; // tabela zbierająca odczyty z sensorów i przekazująca je do proc


void setup() {
  Serial.begin(9600);
  pinMode(senster, OUTPUT);//senster bd dostawal info od dopplera
  pinMode(5, INPUT);
}


void loop() {
  doppler = digitalRead(5);
  if (doppler == HIGH) { // sensor MV wysyla do arduino wart 0 gdy wykryje ruch
       Serial.println("szukam...");
       //Serial.print(",");
       delay(300);
       doppler_ruch();
       digitalWrite(senster, HIGH);
       dopplerVals[0] == digitalRead(5); // zapisuje wart LOW jako element 0 w tabeli 
    }
  else // brak ruchu 
    {
       Serial.println("wykryto ruch!");
       //Serial.print(",");
       delay(300);
       dopplerVals[1] == digitalRead(5); // zapisuje wart inne niż LOW jako element 1 w tabeli
    }
    
  }

  void doppler_ruch() {
    
  }
