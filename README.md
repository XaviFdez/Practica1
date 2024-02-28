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
En este código modificado hemos añadido los puertos de salida ON y OFF, con las funciones sugeridas en la práctica (Serial.printIN), aparte de esta modificación tambien se ha cambiado el tiempo de espera del LED de 500 a 1000 milisegundos.

# 3. Modificar programa para que actue en los registros de entrada de salida.
```c++
#include <Arduino.h>

#define LED_BUILTIN 23
#define DELAY 1000

#define GPIO_OUT_REG 0x3FF4400C

void setup() {
  Serial.begin(115200);
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  volatile uint32_t *gpio_out = (volatile uint32_t *)GPIO_OUT_REG;

  *gpio_out |= (1 << LED_BUILTIN);
  digitalWrite(LED_BUILTIN, HIGH);

  Serial.println("ON");
  
  delay(DELAY);

  *gpio_out ^= (1 << LED_BUILTIN);
  digitalWrite(LED_BUILTIN, LOW);

  Serial.println("OFF");

  delay(DELAY);
}
```
En este código proporcionado, se ha modificado respecto a los anteriores, para que haga la función de actuar sobre los regsitros de entrada y salida, el código ha sido diseñado con las sugerencias añadidas que hacen referencia a *gpio_out*


# 4. Medir frecuencia máxima 
En este cuarto apartado de la práctica modificaremos el Pin de la salida a otro que esté libre i con la ayuda de un osciloscopio mediremos la frecuencia máxima de apagado y encendido que nos marque. 
Mediremos la frecuencia en 4 ocasiones distintas:

## Medit
```
----Añadir lo del osciloscopio gráfica y comentarla


Diagrama codi basic:
Los diagramas de flujo y estado solo se hacen del código básico

*** Poner en código el código básico que da y el que hay ponerlo aquí

```mermaid
stateDiagra
```
