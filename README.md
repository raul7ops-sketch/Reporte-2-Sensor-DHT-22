# Reporte-2-Sensor-DHT-22


## Introduccion
### La ```Esp22``` es utilizada para para la adquisicion y transformacion de datos, en esta practica usaremos un sensor analogico para poder detectar la humedad y temperatura del ambiente. En esta practica se utilizara el sensor ```DHT-11```.
## Equipos y materiales a utilizar:
- Utilizar la pagina web conocida como ```Wokwi```
- Internet
- Una tarjeta de adquisicion de datos (Esp 22)
- Sensor de temperatura DHT11
## Procedimiento
1. Abrir y entrar en la plataforma ```WOKWI```.
2. Una vez habierto seleccionara la opcion  ```ESP 22 ```

![](https://github.com/raul7ops-sketch/Reporte-2-Sensor-DHT-22/blob/main/Reporte%201%20esp%2022.png?raw=true)

4. Una vez dentro seleccionaremos la libreria  ```DHT sensor library for ESPx```
![](https://github.com/raul7ops-sketch/Reporte-2-Sensor-DHT-22/blob/main/Libreria%20reporte%202.png?raw=true)

5. Al terminar copiamos y agregamos el siguiente codigo:

```#include "DHTesp.h"
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
6. Conectamos la tarjeta de adquisicion de datos junto con el DHT-11 como se muestra en la siguiente imagen

