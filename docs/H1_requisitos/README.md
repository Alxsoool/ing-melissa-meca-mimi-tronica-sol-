# Análisis y Requerimientos

## Descripción del problema
Se diseñará y automatizará una cortina industrial de hule termoformado el cual su sistema debe permitir mediante un actuador motorizado el control para abrirla y cerrarla, podrá ajustar la velocidad, configurar tiempos de espera y contará con sensores de seguridad para detenerse si detecta un obstáculo.

Los actores son: el operador (controla la cortina en modo manual o automático y revisa cuántas veces se ha abierto y cerrado), el supervisor (configura los límites de movimiento, ajusta los tiempos de respuesta y define si es velocidad rápida o lenta) y el técnico (se encarga del mantenimiento y de calibrar los sensores de límite).

## Requerimientos del sistema
### Funcionales
- El sistema debe tener la capacidad de abrir y cerrar tanto de manera automática como manual.
- El sistema debe estar automatizado al momento de detectar una persona deteniendo el sistema por completo.
- Se debe indicar los ciclos de cada que se abre o cierra para informar al supervisor los ciclos.

### Técnicos
- Todo el sistema de control y sensores debe operar estrictamente a 24V DC.
- Salidas independientes para Velocidad Alta y Baja.
- El contador de ciclos no debe borrarse si se corta la luz.

### Seguridad
- Acción de actuadores cuando se mantiene presencia humana alejada de la interfaz de la ventana.
- Inicializar el sistema cuando se mantenga la distancia entre cada mitad de la ventana completamente cerrada.
- Uso indispensable de un clema de seguridad con un fusible para evitar peligros de corriente que lleguen a perjudicar el sistema completo y la integridad.
- Creación de leyenda de seguridad, con indicaciones de las conexiones correctas en cada elemento para un correcto flujo de energía.  

## Diagrama de bloques
<img width="1134" height="531" alt="image" src="https://github.com/user-attachments/assets/68522329-111c-428d-ae46-a2b36715a216" />
<img width="703" height="483" alt="Captura de pantalla 2026-02-24 160345" src="https://github.com/user-attachments/assets/f10c0c06-4d0e-4f2c-91e8-50bcba9c872b" />


## Conclusiones del análisis
De acuerdo al análisis realizado se pudo establecer todos los requerimientos funcionales, técnicos y de seguridad para automatizar la cortina de manera adecuada, identificar la energía necesaria para activar el sistema, el modo de operación y el propósito principal para completar la tarea adecuadamente. Definir cómo actúa cada elemento. Así como la supervisión de cada ciclo, con una base que ayude a desarrollar el diseño final. 

## Video Práctica 1: 
https://youtu.be/1nEdXdGO3dk
