# Bitácora – Semana X
## Tema de la semana
En estas últimas 3 sesiones (semana 3 - semana 5) se abordó la integración y sincronización de periféricos industriales mediante un controlador lógico programable (PLC). El proyecto se enfocó en los siguientes pilares técnicos:
### Sensores (Entradas)
Implementación de una red de sensores multitecnología, incluyendo sensores capacitivos e inductivos para detección de presencia, sensores ópticos para barreras de seguridad y sensores magnéticos (Efecto Hall) para el control de límites de carrera y posicionamiento.
### Actuadores (Salidas)
Gestión de potencia mediante relés e interfaces de acoplamiento para controlar un motor de corriente continua (DC) en ambos sentidos de giro, además de la señalización visual de estados a través de una torre de iluminación (semáforo).
### Control (Lógica Programable)
Desarrollo de la lógica de control en el ecosistema LOGO! Soft Comfort, utilizando compuertas lógicas (AND, OR, NOT), bloques de memoria (RS) y temporizadores para automatizar un ciclo de movimiento con protocolos de seguridad prioritarios.
  
## Actividades realizadas
Durante estas sesiones, el equipo se enfocó en la integración técnica del sistema y la resolución de fallas en el hardware. Se contó con una asesoría especializada para validar el funcionamiento general y despejar dudas sobre la conexión de los periféricos. 

<img width="1170" height="640" alt="image" src="https://github.com/user-attachments/assets/f854beac-044e-4be8-90f4-bb08c539aa24" />

<img width="1170" height="622" alt="image" src="https://github.com/user-attachments/assets/311b9879-6c72-41ba-b2f0-c2303b6d1c1d" />


A lo largo de las prácticas, se realizaron pruebas constantes en colaboración con otros equipos, enfrentando dificultades iniciales para interpretar la lógica de bloques en el software LOGO! Soft Comfort.

<img width="908" height="1600" alt="image" src="https://github.com/user-attachments/assets/336f8511-c78c-4a54-8219-4b6ce56cf2ce" />

<img width="1170" height="866" alt="image" src="https://github.com/user-attachments/assets/c60d29dc-6ed3-4ad0-aefe-7f4a8bd5bc81" />


Uno de los puntos críticos fue la corrección del cableado; debido a que las conexiones de los sensores que realizamos no coincidían con el diagrama base propuesto en clase, se decidió reestructurar el cableado para ajustarlo al diseño original. En este proceso, se identificó que el sensor inductivo operaba con lógica inversa, lo que requirió una modificación en el programa para normalizar la señal. Asimismo, fue necesario sustituir el controlador LOGO! Siemens por uno con la configuración adecuada y reemplazar la fuente de voltaje para asegurar la estabilidad eléctrica del sistema.

En la parte de gestión de software, el equipo enfrentó problemas para actualizar a la versión 8.3. Debido a la incompatibilidad de los puertos de las computadoras con el cable de transferencia del PLC, se recurrió a la colaboración con otros equipos para lograr la carga del programa. Finalmente, se validó la lógica de las bobinas del motor para asegurar el cambio de giro y se realizaron ajustes en las conexiones de potencia, logrando que el ciclo de operación y seguridad funcionara según lo previsto.

<img width="1169" height="624" alt="image" src="https://github.com/user-attachments/assets/d7577034-c1ee-4fca-bcc9-56574b13ac82" />


## Decisiones de ingeniería
| Decisión | Alternativas | Justificación |
| :--- | :--- | :--- |
| **Inversión lógica del sensor inductivo** | Cambiar el sensor físicamente por uno Normalmente Abierto (NO). | Se optó por la negación mediante software en LOGO! para ahorrar costos y tiempo, estandarizando la señal de seguridad sin modificar el hardware. |
| **Reestructuración del cableado físico** | Adaptar el programa de LOGO! a las conexiones existentes. | Se decidió regresar al diagrama original de clase para facilitar el diagnóstico de fallas y asegurar que el equipo pudiera seguir una documentación estandarizada. |
| **Sustitución del controlador PLC** | Intentar un "reset" de fábrica o reconfiguración profunda del primer LOGO!. | Al detectar que el primer PLC no respondía a la configuración requerida, se cambió por otro modelo operativo para no retrasar las pruebas de los actuadores. |
| **Reemplazo de la fuente de voltaje** | Ajustar el potenciómetro de la fuente original. | La fuente inicial presentaba inestabilidad bajo carga; se cambió por una unidad de mayor confiabilidad para asegurar que los motores tuvieran el par necesario para el movimiento. |
| **Colaboración inter-equipos para carga de programa** | Comprar adaptadores de puerto o intentar actualizaciones individuales de firmware. | Debido a la incompatibilidad de puertos en las laptops del equipo, la colaboración permitió validar la lógica del programa de forma inmediata y cumplir con los tiempos de entrega. |

## Problema técnico encontrado
El principal obstáculo técnico fue la imposibilidad de transferir la lógica de control desde las estaciones de trabajo hacia el PLC LOGO! Siemens. Este problema se originó por la combinación de dos factores críticos: la falta de actualización del software LOGO! Soft Comfort a la versión 8.3 en la mayoría de los equipos y la incompatibilidad física de los puertos de las laptops con el cable de comunicación industrial requerido por el controlador.

A pesar de que una integrante del equipo logró realizar la actualización del software, la diferencia entre los puertos disponibles en las computadoras y el conector del PLC impidió establecer el enlace de datos necesario para cargar el programa. Esto bloqueó inicialmente la fase de pruebas dinámicas, ya que, aunque la lógica estaba correctamente diseñada en el simulador, no podía ejecutarse en el hardware real para validar el movimiento de los motores y la respuesta de los sensores.

## Solución aplicada
Para resolverlo, se optó por una estrategia de colaboración inter-equipos y una asesoría con el profesor encargado Camilo René Duque Becerra, utilizando estaciones de trabajo compatibles para realizar la transferencia de información. Una vez superada la barrera de comunicación, se procedió con el ajuste de voltajes y la corrección de la lógica inversa del sensor inductivo, logrando finalmente la operatividad del sistema de la cortina.

## Conexión con el curso
Aplicamos la lógica de control programable en un PLC LOGO! Siemens, pasando de la teoría del álgebra de Boole a una implementación física real. Utilizamos sensores de diversas tecnologías (capacitivos, inductivos, ópticos y magnéticos) para gestionar un ciclo automatizado, reforzando el concepto de seguridad industrial (Fail-Safe) al programar paradas de emergencia que priorizan la integridad del equipo. También pusimos en práctica la separación de etapas de control y potencia mediante el uso de relés y fuentes externas para los motores, validando que la automatización depende tanto de una lógica bien estructurada como de la compatibilidad técnica entre el software (v8.3) y el hardware.

## Autoevaluación
- Muy perdido ⬜
- Con dudas ⬜
- Entendiendo ✅
- Dominando ⬜

Nota: Logramos que el sistema funcione y comprendemos cómo interactúan las funciones lógicas con los sensores físicos. Aunque ya podemos diseñar la secuencia, todavía nos estamos familiarizando con la interfaz y las configuraciones específicas de la plataforma LOGO!.
