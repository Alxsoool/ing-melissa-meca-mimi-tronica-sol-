# Hito 3 – Control e Integración
**Curso:** Análisis de Elementos de Mecatrónica  
**Práctica:** Conexión y validación de sensores con Siemens LOGO!  
**Equipo:** Niñas ♡  
**Integrantes:**  
Melissa Zúñiga Miranda A00573666  
Alexa Marisol Rodríguez Barajas A00574830  
Karla Ximena Jaime Neri A00573675  

**Fecha:** 07 de marzo de 2026  

## Descripción de la lógica de control
Explica la secuencia o lógica implementada en LOGO.

## Entradas y salidas
# Elementos del sistema
| Componente | Tipo | Función |
| :--- | :--- | :--- |
| Sensor Capacitivo | Digital / Analógico | Descripción de tarea |
| Sensor Inductivo | Digital / Analógico | Descripción de tarea |
| Sensor Optico | Digital / Analógico | Descripción de tarea |
| Sensor Magnético Arrriba | Digital / Analógico | Descripción de tarea |
| Sensor Magnético Media | Digital / Analógico | Descripción de tarea |
| Sensor Magnético Baja | Digital / Analógico | Descripción de tarea |
| Lámpara Semáforo | Digital (Relé) | Iluminación de área |
| Motor | PWM / DC | Actuador de movimiento |
| Relés | PWM / DC | Actuador de movimiento |

# Cuadro de funciones lógicas
| ENTRADAS | | | | | | SALIDAS | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Descripción del escenario** | **[I1] Sensor Capacitivo** | **[I2] Sensor Inductivo (Negado)** | **[I3] Sensor Óptico** | **[I4] Sensor Magnético (Arriba)** | **[I5] Sensor Magnético (Medio)** | **[I6] Sensor Magnético (Bajo)** | **[Q1] Motor (Bajar)** | **[Q2] Motor (Subir)** | **[Q3] Lámpara Roja** | **[Q4] Lámpara Verde** |
| El sistema está en reposo; encendido, nada detectado | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| Inicia el sistema con la posición inicial de la cortina arriba y enciende la luz roja. | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 1 | 0 |
| Con el sensor capacitivo y el sensor magnético (ARRIBA) activa el motor para bajar y enciende la luz roja. | 1 | 1 | 0 | 1 | 0 | 0 | 1 | 0 | 1 | 0 |
| Con el sensor magnético (MEDIO), la cortina pasa por el nivel medio aun con la luz roja. | 0 | 1 | 0 | 0 | 1 | 0 | 0 | 0 | 1 | 0 |
| Con el sensor magnético (BAJO) se activa la luz verde y hay un delay de 10 segundos. | 0 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1 |
| Inicia el sistema de condición reversa, donde sube, con el sensor inductivo y óptico activados, junto con el sensor magnético (MEDIO) también enciende la luz roja. | 0 | 1 | 0 | 0 | 1 | 0 | 0 | 1 | 1 | 0 |
| El sistema se detiene en caso de que el sensor óptico detecte actividad. | 0 | 1 | 1 | *Cualquiera esté activado* | *Cualquiera esté activado* | *Cualquiera esté activado* | 0 | 0 | 0 | 0 |
| El sistema se detiene en caso de que el sensor inductivo detecte actividad. | 0 | 0 | 0 | *Cualquiera esté activado* | *Cualquiera esté activado* | *Cualquiera esté activado* | 0 | 0 | 0 | 0 |

## Pruebas realizadas
| Prueba | Resultado esperado | Resultado obtenido |
|------|------------------|------------------|

## Ajustes realizados
Describe cambios hechos tras las pruebas.

