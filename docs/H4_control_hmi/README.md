# Hito 4 – Validación Funcional y HMI

## Objetivo del hito
Validar el funcionamiento integrado del sistema mecatrónico y la interacción con el usuario mediante HMI.

---

## Estado general del sistema
Marca el estado actual del sistema:

- No funcional ⬜  
- Parcialmente funcional ⬜  
- Funcional con fallas ⬜  
- Funcional estable ☑  

El sistema realiza correctamente la secuencia de apertura y cierre de la cortina, responde al sensor de inicio y cumple con las condiciones de seguridad implementadas.

---

## Secuencia de operación validada
Describe paso a paso cómo opera el sistema completo:

1. El sistema se activa cuando el usuario toca el **sensor capacitivo**, enviando la señal de inicio al controlador.
2. El motor comienza a girar en el sentido de descenso de la cortina. Cuando el **sensor magnético superior** detecta el imán, se enciende la **luz roja** del semáforo indicando movimiento.
3. Al pasar por el **sensor magnético intermedio**, se vuelve a encender la **luz roja** y el motor continúa bajando la cortina.
4. Cuando el **sensor magnético inferior** detecta el imán, el motor se detiene y se enciende la **luz verde**. El sistema permanece en esta posición durante **10 segundos**, después el motor invierte su sentido de giro y la cortina comienza a subir repitiendo la lógica de detección de sensores.

---

## Validación de sensores

| Sensor | Condición probada | Resultado esperado | Resultado obtenido |
|------|------------------|------------------|------------------|
| Sensor capacitivo | Tocar el sensor una vez | Iniciar la secuencia de movimiento de la cortina | La cortina inicia correctamente |
| Sensor magnético superior | Detección del imán | Encender luz roja y permitir movimiento | Luz roja se enciende correctamente |
| Sensor magnético intermedio | Detección del imán | Encender luz roja momentáneamente | Funciona correctamente |
| Sensor magnético inferior | Detección del imán | Detener motor y encender luz verde | Motor se detiene y luz verde se activa |
| Sensor inductivo | Detectar objeto metálico | Bloquear movimiento de la cortina | Movimiento detenido correctamente |
| Sensor óptico | Detectar presencia frente a la cortina | Impedir avance de la cortina | Sistema bloquea movimiento correctamente |

---

## Validación de actuadores

| Actuador | Acción | Resultado esperado | Resultado obtenido |
|--------|--------|------------------|------------------|
| Motor | Giro para bajar cortina | Cortina desciende correctamente | Movimiento correcto |
| Motor | Giro inverso para subir cortina | Cortina asciende después de 10 s | Funciona correctamente |
| Semáforo rojo | Activación al detectar sensores superior y medio | Indicar movimiento de la cortina | Señalización correcta |
| Semáforo verde | Activación al detectar sensor inferior | Indicar posición final | Funciona correctamente |

---

## Validación del controlador (LOGO)

Describe:

**Temporizaciones**
- Se implementó un temporizador de **10 segundos** cuando la cortina alcanza el sensor inferior antes de iniciar el movimiento de subida.

**Condiciones lógicas**
- El sistema solo inicia cuando se activa el **sensor capacitivo**.
- El motor cambia de estado dependiendo de la detección de los **sensores magnéticos**.

**Interlocks o seguridades implementadas**
- Si el **sensor inductivo detecta un objeto**, el movimiento del motor se bloquea.
- Si el **sensor óptico detecta presencia frente a la cortina**, el sistema impide el movimiento.
- Estas condiciones aseguran que la cortina no avance cuando existe un posible riesgo.

---

## HMI – Interfaz Humano-Máquina

Describe:

**Pantallas implementadas**
- Pantalla principal de monitoreo del sistema.
- Pantalla de estado de sensores y actuadores.

**Variables mostradas**
- Estado de sensores (capacitivo, magnéticos, óptico e inductivo).
- Estado del motor (subiendo, bajando o detenido).
- Estado del semáforo (rojo o verde).

**Acciones disponibles para el usuario**
- Visualización del estado del sistema.
- Supervisión del proceso de apertura y cierre de la cortina.

Adjunta captura(s) de pantalla del HMI.

---

## Fallas detectadas

1. Retraso leve en la detección del sensor magnético cuando la cortina pasa rápidamente por la posición del sensor.
2. Pequeña variación en el tiempo de respuesta del semáforo al activarse los sensores.
3. Ajuste necesario en la posición del sensor óptico para mejorar la detección de presencia.

---

## Ajustes realizados

| Falla | Ajuste realizado | Resultado |
|----|-----------------|----------|
| Detección tardía del sensor | Ajuste en la posición del sensor magnético | Mejora en la detección |
| Retraso en señalización | Ajuste en lógica de activación de luces | Respuesta más inmediata |
| Sensibilidad del sensor óptico | Reposicionamiento y calibración | Detección más confiable |

---

## Preparación para demostración final

Indica qué está listo y qué falta por afinar:

- Lógica de control ☑  
- HMI ☑  
- Cableado ☑  
- Seguridad ☑  
- Evidencias (video/fotos) ☑  

---

## Reflexión breve del equipo

La parte más crítica de esta etapa fue lograr la correcta sincronización entre los sensores, el motor y la lógica de control en el controlador. También fue importante verificar que los sensores de seguridad bloquearan correctamente el movimiento de la cortina para evitar posibles riesgos durante la operación del sistema.
