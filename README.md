# Servo shield
Shield para servo motores em Arduino UNO R3

Trata-se de uma reprodução da PCB montada no vídeo a seguir: 

https://www.youtube.com/watch?v=vVOyWQZ25M8&

Anteriormente à realização desse documento, fiz a montagem da placa, porém, sem utilizar as footprints corretas, utilizando o software Kicad:

[vou colocar uma imagem da placa]

Alguas falhas ocorreram nas trilhas, impedindo continuidade trechos importantes. O problema foi contornado soldando estanho nessas locais.

<h3>Esquemático</h3>

![](images/esquematico.png)


[colocar a imagem do modelo 3D do kicad]


<h3>Teste</h3>

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
