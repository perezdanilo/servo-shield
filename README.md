# Servo shield
Shield para servo motores em Arduino UNO R3

Reprodução da PCB montada no vídeo a seguir, do canal Brincando com Ideias: 

https://www.youtube.com/watch?v=vVOyWQZ25M8&

<h3>Esquemático</h3>
![esquematico](images/esquematico.png)



<h3>Resultado</h3>
Alguas falhas ocorreram nas trilhas, impedindo continuidade em alguns trechos. O problema foi contornado soldando estanho nessas lugares.

<h3>Testando</h3>
Foi utilizado o exemplo Knob, da biblioteca Servo, realizando algumas adaptações. 


(ainda vou mudar o código, adicionando os outros motores e potenciômetros)
```c
#include <Servo.h>

Servo myservo;  // create servo object to control a servo

int potpin = 0;  // analog pin used to connect the potentiometer
int val;    // variable to read the value from the analog pin

void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
}

void loop() {
  val = analogRead(potpin);            // reads the value of the potentiometer (value between 0 and 1023)
  val = map(val, 0, 1023, 0, 180);     // scale it to use it with the servo (value between 0 and 180)
  myservo.write(val);                  // sets the servo position according to the scaled value
  delay(15);                           // waits for the servo to get there
}
```





A utilização dos botões ficará para outra oportunidade.
