# Documentación, Practicas
# Nombre de la practica: Funcionamiento y uso de la compuerta 74ls555
Autores
## Garcia Elvira Pedro Emmanuel
## Barriga Gómez Diego
## Fecha: 5 de Septiembre del 2025
Asignatura: Introducción a la Mecatronica

# Práctica con el Temporizador 555

## Introducción
En esta práctica de la materia **"Introducción a la Mecatrónica"**, se trabajó con el **integrado 555**, un componente que permite **activar o desactivar funciones** dentro de un circuito durante un tiempo determinado.  
Este intervalo puede modificarse ajustando los valores de las **resistencias** y **capacitores** empleados en el diseño.

---

## Objetivo de la práctica
El propósito fue lograr que un **LED** se encendiera durante un periodo de **3 a 5 segundos** y permaneciera **apagado** durante el mismo intervalo de tiempo.  
De esta forma, se buscó comprender cómo el **555** puede controlar la frecuencia de parpadeo en función de los componentes conectados.

---

## Uso de capacitores
Durante la clase se enfatizó en el uso de los **capacitores**, ya que el tema principal era analizar **sus funciones y aplicaciones** dentro de un circuito temporizador.  
Los capacitores se utilizaron para almacenar y liberar energía, permitiendo modificar los tiempos de encendido y apagado del LED.

---

## Cálculos de resistencia
Se nos proporcionó una **calculadora de componentes**, la cual permitía ingresar los valores de dos resistencias y un capacitor.  
Una de las resistencias controlaba el **tiempo de encendido**, mientras que la otra regulaba el **tiempo de apagado** del LED.

Además, la calculadora mostraba el **diagrama de conexión** de los pines del 555 hacia la **protoboard**, lo que facilitó seguir correctamente el esquema del circuito.

---

## Componentes utilizados
En el caso de nuestro equipo, seleccionamos los siguientes valores:

- **Resistencia 1:** 1 kΩ  
- **Resistencia 2:** 20 kΩ  
- **Capacitor:** 330 µF  

Estos componentes permitieron obtener el comportamiento deseado del circuito, con un parpadeo del LED dentro del rango de **3 a 5 segundos** para cada ciclo.

---

## Conclusión
Gracias a esta práctica comprendimos mejor cómo **las resistencias y los capacitores** influyen en el **tiempo de respuesta** de un circuito con el **temporizador 555**.  
Además, reforzamos la habilidad para **interpretar y armar circuitos** basados en diagramas electrónicos.


![Diagrama del sistema](recursos/imgs/Practica 555.png)

**Pagina**
(https://www.digikey.com.mx/es/resources/conversion-calculators/conversion-calculator-555-timer?srsltid=AfmBOopExlAJ0hL2w6AKdoyEliUHPJePR_9zs5x8V6Y6rbOffRCSPgXM)

---
---
---

# Nombre de la practica: Funcionamiento y uso de la compuerta 74ls555
Autores
## Garcia Elvira Pedro Emmanuel
## Barriga Gómez Diego
## Fecha: 12 de Septiembre del 2025

# Descripción
En esta práctica se trabajó con diversos **componentes electrónicos** —entre ellos el **ESP32**, **jumpers** y una **protoboard**— con el objetivo de implementar un circuito capaz de **encender y apagar un diodo LED** mediante la **programación del microcontrolador ESP32** desde un entorno computacional.

---

# Objetivos

## General
En esta segunda practica de la asignatura **"Introducción a la Mecatrónica"**, se buscó diseñar e implementar un circuito controlado por un **ESP32**, programado para **activar y desactivar un LED** de acuerdo con las instrucciones definidas en el código desarrollado durante la sesión.

## Específicos
- **Objetivo 1:** Superar el desempeño obtenido en la primera practica, consolidando los conocimientos adquiridos y aplicándolos de manera más eficiente.  
- **Objetivo 2:** Profundizar en la comprensión del funcionamiento del **ESP32**, así como en la lógica de control digital mediante programación estructurada.  
- **Objetivo 3:** Fortalecer las habilidades en el **ensamblaje de circuitos electrónicos** y la **implementación de retardos temporales (delay)** dentro de un programa.

---

# Alcance y Exclusiones

- **Incluye:**  
  - Los **códigos fuente** empleados para la ejecución de cada circuito.  
  - **Evidencias fotográficas** de las conexiones realizadas en la protoboard.  


---

# Procedimiento 1
1. **Revisión de materiales:** Se verificó la disponibilidad y correcto funcionamiento de los componentes electrónicos requeridos para la práctica.  
2. **Configuración inicial:** Se realizó una breve introducción al uso del **microcontrolador ESP32**, abordando su conexión con la computadora y su programación mediante un entorno de desarrollo compatible.  
3. **Diseño del circuito:** Se implementó un circuito básico en la **protoboard**, conectando un **LED** a uno de los **pines digitales de salida** del ESP32, junto con la resistencia correspondiente para limitar la corriente.  
4. **Programación:** Se desarrolló un **script en lenguaje C/C++**, el cual controla el encendido y apagado del LED utilizando la función `delay()` para generar intervalos de tiempo visibles entre ambos estados.  
5. **Ejecución y verificación:** Finalmente, se cargó el programa al ESP32 y se comprobó su correcto funcionamiento, verificando que el LED alternara su estado de encendido y apagado de acuerdo con el código implementado.

### Codigo

```cpp
const int led = 33; // Puerto del ESP32 al que está conectado el LED

void setup() {
  Serial.begin(115200);
  pinMode(led, OUTPUT);
}

void loop() {  // Repetición constante del encendido y apagado
  digitalWrite(led, 1); // Encendido
  delay(1000);          // Retraso del encendido y apagado del LED
  digitalWrite(led, 0); // Apagado
  delay(1000);
}
```
---
# Procedimiento 2
Partiendo del código y circuito desarrollados en la primera práctica, se realizaron **modificaciones tanto en el hardware como en el software**.  

En esta ocasión, se añadió un **botón pulsador** al circuito con el propósito de **controlar manualmente el encendido y apagado del LED** al presionarlo.  
El botón se conectó al **pin 34 del ESP32**, configurado como **entrada digital**.  

Para implementar esta nueva funcionalidad, se declaró una **nueva constante** en el código correspondiente al pin del botón, y se agregaron **estructuras condicionales** que permiten determinar el estado del LED en función de la lectura del pulsador:  
- Cuando el botón es presionado, el **LED se enciende**.  
- Cuando el botón no está presionado, el **LED permanece apagado**.  

Estas modificaciones permitieron ampliar el control del sistema, pasando de un funcionamiento automático a uno **interactivo**, donde la acción del usuario influye directamente en el comportamiento del circuito.

```
const int led=33; // LED

const int btn=34; // BOTON

void setup() {

  Serial.begin(115200);

  pinMode(led, OUTPUT); // SALIDA

  pinMode(btn, INPUT); // ENTRADA


}

void loop() {

  int estado = digitalRead(btn); 

  if(estado == 1){

     digitalWrite(led,1);  // PRENDIDO
  }

  else {

    digitalWrite(led,0); // APAGADO

  }

}
```

# Procedimiento 3
Para este tercer ejercicio se utilizó la aplicación **"Serial Bluetooth Terminal"**, la cual permite **comunicarse con el ESP32 vía Bluetooth**. Mediante la terminal de la aplicación, se pueden enviar señales al microcontrolador para **controlar el encendido y apagado del LED** de acuerdo con el código programado.  

Partiendo del **código desarrollado en el Procedimiento 2**, se realizaron las siguientes modificaciones:  

1. Se añadió la librería **`#include "BluetoothSerial.h"`** para habilitar la comunicación Bluetooth en el ESP32.  
2. Se eliminó la constante y configuración del botón físico, reemplazando la entrada por la **conexión Bluetooth**, que se denominó **LR23** en el código.  
3. Las estructuras condicionales fueron adaptadas para funcionar con la aplicación:  
   - Si la terminal envía el mensaje `"Prende"`, el **LED se enciende**.  
   - Si se recibe cualquier otro mensaje, el **LED permanece apagado o se apaga**.  

Estas modificaciones permitieron controlar el LED de manera **remota mediante Bluetooth**, demostrando cómo integrar comunicaciones inalámbricas con sistemas embebidos.

```
"#"include "BluetoothSerial.h"

BluetoothSerial SerialBT;

const int led=33;


void setup() {

  Serial.begin(115200);

  SerialBT.begin("LR23"); // Dipositivo bluetooth

  pinMode(led, OUTPUT);

}

void loop() {

  if(SerialBT.available()){

    String mensaje = SerialBT.readString();

    Serial.println("Recibido: " + mensaje);

    if(mensaje == "Prende"){

     digitalWrite(led,1);

    }

    else {

      digitalWrite(led,0);
    }

  }

  delay(100);

 }
```

# Conclusión
La práctica permitió fortalecer la comprensión sobre la interacción entre **hardware y software** en sistemas embebidos, aplicando distintos métodos de control de un **LED** utilizando el **ESP32**.  

En el **Procedimiento 1**, se desarrolló un circuito básico con encendido y apagado automático mediante retardos temporales, lo que reforzó la comprensión del **control temporal** en programación.  

En el **Procedimiento 2**, se integró un **botón físico** como entrada digital, permitiendo el control manual del LED mediante estructuras condicionales, lo que amplió la experiencia en **interacción hardware-software** y en la gestión de entradas digitales.  

Finalmente, en el **Procedimiento 3**, se implementó **comunicación inalámbrica vía Bluetooth** utilizando la librería `BluetoothSerial.h`, logrando controlar el LED de manera remota desde una aplicación móvil, lo que permitió explorar la integración de **sistemas embebidos con comunicaciones inalámbricas**.  

En conjunto, estas prácticas consolidaron conocimientos en **configuración del ESP32**, **control de salidas digitales**, **gestión de entradas y condicionales**, así como en la **interfaz con dispositivos externos** mediante Bluetooth.




[Enlace directo](https://www.iberopuebla.mx/)

[Texto del enlace de referencia][doc-ref]

[doc-ref]: https://www.iberopuebla.mx//docs "Título opcional"
```

[Enlace directo](https://www.iberopuebla.mx/)

[Texto del enlace de referencia][doc-ref]

[doc-ref]: https://www.iberopuebla.mx//docs "Título opcional"

---

# Listas: viñetas, numeradas y de tareas

``` codigo

- Item A
    * Subitem A.1
    * Subitem A.2
- Item B
    - Subitem B.1
    - Subitem B.2

1.  Paso 1
    1.  Paso 1.1
    2.  Paso 1.2
        1.  Paso 1.2.1
        2.  Paso 1.2.2
        
- [x] Hecho
- [ ] Pendiente

```

- Item A
    * Subitem A.1
    * Subitem A.2
- Item B
    - Subitem B.1
    - Subitem B.2

---

1.  Paso 1
    1.  Paso 1.1
    2.  Paso 1.2
        1.  Paso 1.2.1
        2.  Paso 1.2.2
        
- [x] Hecho
- [ ] Pendiente

---

# Tablas

``` codigo
| Componente | Cant. | Nota        |
|-----------:|:-----:|-------------|
| Sensor X   | 2     | I2C         |
| MCU Y      | 1     | WiFi/BLE    |
```

| Componente | Cant. | Nota        |
|-----------:|:-----:|-------------|
| Sensor X   | 2     | I2C         |
| MCU Y      | 1     | WiFi/BLE    |

---

# Imágenes

``` codigo
![Diagrama del sistema](recursos/imgs/ibero.jpeg)

<!-- Control de tamaño usando HTML (cuando se requiera) -->
<img src="../recursos/imgs/ibero.jpeg" alt="Diagrama del sistema" width="420">
```

![Diagrama del sistema](recursos/imgs/ibero.jpeg)

<img src="../recursos/imgs/ibero.jpeg" alt="Diagrama del sistema" width="420">

---

# PDFs (enlace y embebido)

``` codigo
[Descargar especificación (PDF)](recursos/archivos/Calendario.pdf)

<!-- Embed (requiere navegador compatible) -->
<object data="recursos/archivos/Calendario.pdf" type="application/pdf" width="100%" height="600">
  <p>No se pudo mostrar el PDF. <a href="../recursos/archivos/Calendario.pdf">Descargar</a></p>
</object>
```

[Descargar especificación (PDF)](recursos/archivos/Calendario.pdf)

<object data="../recursos/archivos/Calendario.pdf" type="application/pdf" width="100%" height="600">
  <p>No se pudo mostrar el PDF. <a href="../recursos/archivos/Calendario.pdf">Descargar</a></p>
</object>

---

# Admonitions (Material)

``` codigo
!!! note "Nota"
    Esto es una nota informativa.

!!! tip "Sugerencia"
    Un consejo breve para el usuario.

!!! warning "Advertencia"
    Precauciones o riesgos a considerar.

??? info "Más información (colapsable)"
    Contenido adicional que se puede expandir.
```

!!! note "Nota"
    Esto es una nota informativa.

!!! tip "Sugerencia"
    Un consejo breve para el usuario.

!!! warning "Advertencia"
    Precauciones o riesgos a considerar.

??? info "Más información (colapsable)"
    Contenido adicional que se puede expandir.

---

# Código con resaltado

``` codigo
```python
def medir(canal: int) -> dict:
    # Simulación de lectura
    return {"canal": canal, "valor": 523, "unidad": "mV"}

print(medir(1))
```
```

```python
def medir(canal: int) -> dict:
    # Simulación de lectura
    return {"canal": canal, "valor": 523, "unidad": "mV"}

print(medir(1))
```

---

# Separador horizontal

``` codigo
---
```

---

---

# Listas anidadas con código y notas

``` codigo
- **Módulo A**
  - Función: `procesar()`
  - Entrada:
    - `signal` (float)
    - `freq` (Hz)
  - Salida:
    - JSON con `valor`, `unidad`
  - !!! note
        Documenta rangos válidos y casos borde.
```

- **Módulo A**
  - Función: `procesar()`
  - Entrada:
    - `signal` (float)
    - `freq` (Hz)
  - Salida:
    - JSON con `valor`, `unidad`
  - !!! note
        Documenta rangos válidos y casos borde.

---

# Bloques de cita con código (pseudo-logs)

``` codigo
> **Log:**
> ```
> [12:00:00] Init OK
> [12:00:01] Conectando a I2C...
> [12:00:02] Lectura: 523 mV
> ```
```

> **Log:**
> ```
> [12:00:00] Init OK
> [12:00:01] Conectando a I2C...
> [12:00:02] Lectura: 523 mV
> ```
