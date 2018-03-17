# ArduinoReadString
Este código de ejemplo sirve para poder leer cadenas de String enviados a través de Bluetooth por la aplicación ComandArduino (Buscar en el repositorio).


```c
/**
* Bluetooth, utilizando los puertos seriales
* RX(2) y TX(3).
* 
* @author Damián Rincón Cañaveral
**/

#include <SoftwareSerial.h>
//Declarando Bluetooth.
SoftwareSerial input(2,3);
char mander;
String response;
void setup() {
   //Encendemos bluetooth
   input.begin(9600);
}
void loop() { 
  if(input.available()>0){
    mander = input.read();
    response+=mander;
    if(mander==';'){
      Serial.print("Recibido: ");
      Serial.println(response);
      //Tus acciones
      response = "";
    }
  }
}
```
