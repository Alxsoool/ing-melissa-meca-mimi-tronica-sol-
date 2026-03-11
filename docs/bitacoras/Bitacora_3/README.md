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
|--------|-------------|---------------|
|  |  |  |
## Problema técnico encontrado
Describe un problema concreto.
## Solución aplicada
Explica cómo se resolvió.
## Conexión con el curso
¿Qué concepto de MR2022 aplicaste esta semana?
## Autoevaluación
- Muy perdido⬜
- Con dudas⬜
- Entendiendo⬜
- Dominando
