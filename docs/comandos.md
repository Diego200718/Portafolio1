# Documentación, practicia 1
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

# Énfasis y código en línea

``` codigo
**negritas**, *cursivas*, ~~tachado~~, `código en línea`
```

**negritas**, *cursivas*, ~~tachado~~, `código en línea`

---

# Citas (blockquote)

``` codigo
> Esta es una cita destacada.
> Puede tener múltiples líneas.
```

> Esta es una cita destacada.
> Puede tener múltiples líneas.

---

# Enlaces

``` codigo
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
