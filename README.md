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

![](https://github.com/raul7ops-sketch/Reporte-2-Sensor-DHT-22/blob/main/Conexion%20reporte%202.png?raw=true)

7. Por ultimo le presionamos en el boton de ```Play``` para correr el simulador.
8. Analizar y variar la temperatura anasalizando el monitor serial del simulador.

## Resultados y conclusion
Si realizamos paso a paso las instrucciones de este reporte el simulador trabajara de la siguiente manera:

![](https://github.com/raul7ops-sketch/Reporte-2-Sensor-DHT-22/blob/main/Imagen%20final%20de%20reporte%202.png?raw=true)

Donde a mano izquierda tendremos el codigo que introdujimos en el simulador (el codigo antes copiado en este reporte) a mano derecha veremos las conexiones realizadas de la tarjeta de adquiscion de datos y el sensor de temperatura DHT-11, tambien justo abajo veremos el monitor serial que ira mostrando los valores de temperatura y humeda solicitados.

# Creditos
Este reporte fue realizado por Raul Aguilar Lagunas.
