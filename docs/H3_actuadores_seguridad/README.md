# Control e Integración
**Curso:** Análisis de Elementos de Mecatrónica  
**Práctica:** Conexión y validación de sensores con Siemens LOGO!  
**Equipo:** Niñas ♡  
**Integrantes:**  
Melissa Zúñiga Miranda A00573666  
Alexa Marisol Rodríguez Barajas A00574830  
Karla Ximena Jaime Neri A00573675  

**Fecha:** 10 de marzo de 2026  

## Descripción de la lógica de control

<img width="994" height="740" alt="image" src="https://github.com/user-attachments/assets/386c1a4e-d162-46c9-917d-99f9cbee2927" />

El sistema inicia en un estado de reposo donde la seguridad es lo más importante. Antes que nada, es importante mencionar que la lógica está condicionada por el sensor inductivo (Entrada I2 en LOGO Siemens) y el sensor óptico (Entrada I3 en LOGO Siemens); mientras estos no detecten ninguna obstrucción (I2' + I3 = 0), el sistema permite el flujo de energía hacia los motores. Debido a que el sensor inductivo opera con lógica inversa, entregando un estado lógico "1" en reposo, se adaptó una negación de señal en la programación. Esto permite estandarizar la lógica de control, asegurando que todas las entradas de seguridad operen bajo el mismo criterio de activación. 
Bajo condiciones normales, cuando la cortina se encuentra en su punto más alto, el sensor magnético ARRIBA (Entrada I4 en LOGO Siemens) se activa con un imán que se encuentra en un extremo de la cortina, lo que a su vez enciende la Lámpara ROJA (Salida Q3 en LOGO Siemens) como señal de advertencia de que el ciclo está listo para comenzar.

<img width="601" height="264" alt="image" src="https://github.com/user-attachments/assets/429d3d07-f43c-42a8-8a74-e0db914806fd" />

En cuanto se presenta un objeto, el sensor capacitivo (Entrada I1 en LOGO Siemens) envía una señal de activación (I1 = 1). Siempre que esta señal coincida con la posición inicial de la cortina (I4), se activa la compuerta AND que permite el encendido del motor de BAJAR (Salida Q1 en LOGO Siemens). A medida que la cortina desciende, esta pasa por el sensor magnético MEDIO (Entrada I5 en LOGO Siemens); a pesar de este cambio de posición, el sistema mantiene encendida la luz ROJA para indicar que el mecanismo sigue en movimiento y el área no está despejada.

<img width="597" height="496" alt="image" src="https://github.com/user-attachments/assets/219d1b40-176e-4b5a-b751-533f1548e02b" />

Posteriormente, una vez que la cortina alcanza el límite inferior, el sensor magnético BAJO (Entrada I6 en LOGO Siemens) detecta su llegada. En ese preciso momento, el motor de BAJAR se detiene (Q1 = 0) y se produce un cambio en la señalización: la luz ROJA se apaga para dar paso a la Lámpara VERDE (Salida Q4 en LOGO Siemens). Cabe destacar que, debido a la programación en LOGO!, se ejecuta un delay de 10 segundos antes de que el sistema procese la siguiente instrucción, permitiendo un tiempo de espera seguro en la posición baja.

<img width="846" height="772" alt="image" src="https://github.com/user-attachments/assets/57dbb63f-2920-458a-a154-c85c1ff2b1bf" />

Finalmente, el sistema entra en su fase de "condición de reversa". Esta secuencia se activa mediante el bloque de memoria RS, el cual activa el Motor SUBIR (Salida Q2 en LOGO Simens) utilizando el sensor magnético MEDIO (I5) y el temporizador interno. No obstante, es importante señalar que existe una condición de paro TOTAL: si en cualquier punto del trayecto el sensor óptico o el inductivo detectan actividad inusual (I2' + I3 = 1), la lógica de control interrumpe inmediatamente el paso de corriente a los actuadores. De esta manera, el sistema garantiza que la cortina se detenga en seco ante cualquier emergencia, protegiendo tanto el mecanismo como al usuario.

## Entradas y salidas
### Diagrama de conexiones eléctricas

![EquipoNiñas_LOGODesign](https://github.com/user-attachments/assets/97eebdc0-8635-49c0-a977-d7aa1c5fbb60)

### Elementos del sistema

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

### Cuadro de funciones lógicas

<img width="630" height="749" alt="image" src="https://github.com/user-attachments/assets/a94ec6b2-10aa-406a-8b3d-0f41a18e0dec" />

## Pruebas realizadas

| Prueba | Resultado esperado | Resultado obtenido |
|------|------------------|------------------|
| Esquema Funcional | Al detectar un objeto con el sensor capacitivo (I1), el motor (Q1) debe iniciar el descenso. Al llegar al sensor magnético BAJO (I6), debe detenerse 10 segundos y luego iniciar la reversa del motor (Q2) hasta llegar al sensor magnético SUBIR (I4). La lámpara debe de cumplir con su funcionamiento al rededor del ciclo. | El sistema realizó el ciclo completo. Se observó el cambio de luces (Rojo a Verde en posición baja) y el temporizador de 10s funcionó correctamente antes de la subida automática. |
| Esquema de Seguridad | Al estar los motores en marcha (ya sea bajando o subiendo), la activación del sensor inductivo (I2) o el óptico (I3) debe interrumpir el suministro eléctrico a los actuadores de forma inmediata. | Se validó que al acercar un objeto metálico al sensor inductivo durante la subida, el motor se detuvo instantáneamente, confirmando la jerarquía de seguridad sobre la lógica de control. Sin embargo, al activar el sensor óptico no surgió ningún efecto. |

### Evidencia Esquema Funcional


https://github.com/user-attachments/assets/05c784cc-6ec5-494d-95d1-6e7b59709915



### Evidencia Esquema de Seguridad


https://github.com/user-attachments/assets/5a990257-511a-4b1e-b2ae-561e3fae1ee3



## Ajustes realizados
| Categoría | Descripción del ajuste técnico | Impacto en el sistema |
| :--- | :--- | :--- |
| **Normalización de Lógica (Inductivo)** | Debido a que el sensor opera de manera predeterminada como Normalmente Cerrado (NC), se implementó una negación lógica en la programación de LOGO! Soft Comfort. | Este ajuste permitió estandarizar la entrada para que el sistema interprete la detección como un "1" lógico, unificando el criterio de activación con el resto de los periféricos. |
| **Revalidación del Sensor Óptico** | Al observar que el sensor óptico no interrumpía el ciclo, se procedió a realizar una revalidación de sus valores detectados en LOGO y la lógica de control. | Se logró que la señal alcanzara el voltaje de conmutación requerido por la entrada del PLC, restableciendo la integridad del lazo de seguridad. |
| **Observación y Monitoreo** | El prototipo se mantuvo en un periodo de observación tras los ajustes para garantizar que la respuesta ante emergencias fuera inmediata y repetible. | Asegura que el motor no reanude su marcha hasta que la condición de obstrucción sea eliminada por completo, validando la confiabilidad del sistema. |

