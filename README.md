# Practica 1: BLINK 
En esta primera práctica junto con el microcontrolador ESP32 y un led, tendremos como objetivo producir el parpadeo del LED.

# 1.Codigo Básico:
```c++
#define LED_BUILTIN 2
#define DELAY 500

void setup() {
 pinMode(LED_BUILTIN, OUTPUT);
}
void loop() {
 digitalWrite(LED_BUILTIN, HIGH);
 delay(DELAY);
 digitalWrite(LED_BUILTIN, LOW);
 delay(DELAY);
}
```
# 2. Modificar el programa (ON, OFF)

```c++
#include <Arduino.h>

#define LED_BUILTIN 23
#define DELAY 1000 //ms


void setup() {
Serial.begin(115200); 
pinMode(LED_BUILTIN, OUTPUT);

}

void loop() {
    
digitalWrite(LED_BUILTIN, HIGH);

Serial.println("ON"); 
delay(DELAY);
digitalWrite(LED_BUILTIN, LOW);

Serial.println("OFF"); 
delay(DELAY);
}
```
En este código modificado hemos añadido los puertos de salida ON y OFF, con las funciones sugeridas en la práctica (Serial.printIN), aparte de esta modificación tambien se ha cambiado el tiempo de espera de 500 a 1000 milisegundos.

# 3. Modificar programa para que actue en los registros de entrada de salida.

Diagrama codi basic:
Los diagramas de flujo y estado solo se hacen del código básico

*** Poner en código el código básico que da y el que hay ponerlo aquí

```mermaid
stateDiagra
```
# 4. Medir frecuencia máxima 
```
