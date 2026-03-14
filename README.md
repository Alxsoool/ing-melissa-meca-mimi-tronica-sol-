# Cortina industrial

# Proyecto Mecatrónico – MR2022

## Problema
El problema que resuelve este sistema es la falta de seguridad y precisión en el manejo de cortinas industriales de grandes dimensiones. Su operación manual es lenta y propensa a errores humanos pero el sistema automatiza todo este proceso para eliminar la dependencia de la fuerza física y la intervención humana constante, asegurando que la cortina se mueva siempre en los tiempos exactos configurados por el operario. Además, soluciona el riesgo de accidentes al integrar sensores de seguridad que se detienen ante cualquier obstáculo.

## Arquitectura del sistema
https://drive.google.com/file/d/1O8LXJmrG0dRfRadI6zm2griqDGyhsf4p/view?usp=drivesdk

[Sensores] → [Siemens LOGO] → [Relés] → [Motor DC]

## Componentes utilizados
- Sensor inductivo
- Sensor capacitivo
- Sensor óptico
- Sensor magnético
- Siemens LOGO
- Relés
- Motor DC 24V
- Torre de luces

## Lógica de control
El sistema opera mediante un programa cargado en el Siemens LOGO! que monitorea constantemente las entradas digitales. El ciclo se inicia únicamente cuando el sensor capacitivo envía una señal de arranque. A partir de ese momento, el controlador activa el motor para el descenso de la cortina, manteniendo un monitoreo permanente de los sensores magnéticos para definir las etapas del recorrido (arriba, en medio y abajo).

La lógica integra dos niveles de seguridad fundamentales: primero, los interlocks proporcionados por el sensor inductivo y el sensor óptico, los cuales tienen prioridad absoluta y detienen el motor instantáneamente ante cualquier riesgo. Segundo, una secuencia de temporización configurada a 10 segundos que garantiza que la cortina permanezca en la posición inferior antes de invertir automáticamente el sentido de giro para el ascenso. Finalmente, la lógica de salida gestiona el semáforo, alternando entre rojo durante el movimiento y verde al alcanzar la posición de seguridad, informando en todo momento al operador sobre el estado operativo a través de la HMI.

## Resultados de pruebas
| I1 Sensor Capacitivo | I2 Sensor Inductivo | I3 Sensor Óptico (Negado) | I4 Sensor Magnético (Arriba) | I5 Sensor Magnético (Medio) | I6 Sensor Magnético (Bajo) | Q1 Motor (Bajar) | Q2 Motor (Subir) | Q3 Lámpara Roja | Q4 Lámpara Verde | Descripción del escenario |
|---|---|---|---|---|---|---|---|---|---|---|
| 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | El sistema está en reposo; encendido, pero detenido |
| 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 1 | 0 | Inicia el sistema con la posición inicial de la cortina arriba y enciende la luz roja |
| 1 | 1 | 0 | 1 | 0 | 0 | 1 | 0 | 1 | 0 | Con el sensor capacitivo y el sensor magnético (ARRIBA) se activa el motor para bajar y enciende la luz roja |
| 0 | 1 | 0 | 0 | 1 | 0 | 0 | 0 | 1 | 0 | Con el sensor magnético (MEDIO), la cortina pasa por el nivel medio aún con la luz roja |
| 0 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1 | Con el sensor magnético (BAJO) se activa la luz verde y hay un delay de 10 segundos |
| 0 | 1 | 0 | 0 | 1 | 0 | 0 | 1 | 1 | 0 | Inicia el sistema de condición reversa, donde sube, con el sensor inductivo y óptico activados, junto con el sensor magnético (MEDIO) también enciende la luz roja |
| 0 | 1 | 1 | *Cualquiera esté activado* | *Cualquiera esté activado* | *Cualquiera esté activado* | *Cualquiera esté activado* | *Cualquiera esté activado* | *Cualquiera esté activado* | El sistema se detiene en caso de que el sensor óptico detecte actividad |
| 0 | 0 | 0 | *Cualquiera esté activado* | *Cualquiera esté activado* | *Cualquiera esté activado* | *Cualquiera esté activado* | *Cualquiera esté activado* | *Cualquiera esté activado* | El sistema se detiene en caso de que el sensor inductivo detecte actividad |
https://drive.google.com/drive/folders/1QBbG9HqKYnWGPE4Xqif0JBU8gSKpY1Pl?usp=sharing

## Videos demo
[(link al video)](https://drive.google.com/drive/folders/1lik6apuUVEtddtcRXBrtY1zWGIBRSAvZ?usp=sharing)

## Integrantes del proyecto
Melissa Zúñiga Miranda A00573666 | Alexa Marisol Rodríguez Barajas A00574830 | Karla Ximena Jaime Neri A00573675
