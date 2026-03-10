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
| Componente | Entrada en LOGO Siemens | Función |
| :--- | :--- | :--- |
| Sensor Capacitivo | I1 | Detecta la presencia del objeto para iniciar el ciclo de bajada del sistema. |
| Sensor Inductivo | I2 | Seguridad de área; su detección (valor 0) bloquea los motores inmediatamente. |
| Sensor Optico | I3 | Seguridad por barrera; detecta obstrucciones y detiene el movimiento de la cortina. |
| Sensor Magnético Arrriba | I4 | Final de carrera superior; indica que la cortina está en su posición inicial. |
| Sensor Magnético Media | I5 | Sensor de posición intermedia; gestiona la iluminación roja y el cambio a reversa. |
| Sensor Magnético Baja | I6 | Final de carrera inferior; detiene el motor de bajada y activa la luz verde. |
| Lámpara Semáforo | Q3 y Q4 | Indicador visual de estado: Rojo (En movimiento/Arriba) y Verde (Posición final). |
| Motor | Q1 y Q2 | Actuador principal encargado de realizar el movimiento de Bajar (Q1) o Subir (Q2). |

# Cuadro de funciones lógicas
<img width="630" height="749" alt="image" src="https://github.com/user-attachments/assets/a94ec6b2-10aa-406a-8b3d-0f41a18e0dec" />

## Pruebas realizadas
| Prueba | Resultado esperado | Resultado obtenido |
|------|------------------|------------------|
|  |  |  |

## Ajustes realizados
Describe cambios hechos tras las pruebas.

