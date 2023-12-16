# Práctica-No.2-ESP32-con-DHT11
Dentro de este repositorio se muestra la manera de programar una ESP32 con el sensor DHT11.
## Introducción
### Descripción
La **ESP32** se utiliza en un entorno de adquisición de datos, por lo cual en esta práctica utilizaremos un sensor **DHT11** para obtener registros de temperatura y humedad del entorno. Para esta practica se hace uso de un simulador llamado [WOKWI](https://wokwi.com/projects/new/esp32).
## Material necesario
Para realizar esta práctica necesitas lo siguiente

- [WOKWI](https://wokwi.com/projects/new/esp32)
- Tarjeta ESP32
- Sensor DHT11
## Instrucciones
### Requisitos previos
Para poder hacer uso de este repositorio se requiere entrar a la plataforma de [WOKWI](https://wokwi.com/projects/new/esp32).
### iNSTRUCCIONES DE PREPARACIÓN DEL ENTORNO
1. Abrir la terminal de programación y colocar el siguiente código:

```
#include "DHTesp.h"
#include <LiquidCrystal_I2C.h>

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}

```
2. Instalar la libreria de **DHT Sensor library for ESPx** como se muestra en la siguiente imagen
![](https://github.com/AbrahamCH1/Pr-ctica-No.1-ESP32-con-DHT11/blob/main/Captura%20de%20pantalla%20(290).png?raw=true)

3. Hacer la conexion de **DHT11** con la **ESP32** como se muestra en la siguente imagen.
![](https://github.com/AbrahamCH1/Pr-ctica-No.1-ESP32-con-DHT11/blob/main/Captura%20de%20pantalla%20(291).png?raw=true)
### INSTRUCCIONES DE OPERACIÓN
1. Iniciar simulador.
2. Visualizar los datos en el monitor serial.
3. Colocar la temperatura y humedad dando *doble click* al sensor **DHT11** 
## Resultados
Cuando haya funcionado, se podrán observar los valores dentro del monitor serial como se muestra en la siguente imagen.
![]()

