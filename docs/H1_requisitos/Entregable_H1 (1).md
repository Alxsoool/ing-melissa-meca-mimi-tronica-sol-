# Hito 1 – Análisis y Requerimientos

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
<img width="856" height="600" alt="image" src="https://github.com/user-attachments/assets/0f7ca0ea-cdc0-40d4-bb28-5f71179039e7" />

## Conclusiones del análisis
Breve reflexión técnica.
