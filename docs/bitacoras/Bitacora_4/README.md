# Bitácora – Semana 4
## Tema de la semana
(Sensores / Actuadores / Control / HMI)

## Actividades realizadas
### Programación y Depuración
Se migró de una lógica de control básica a una más robusta para corregir errores de detección en el sistema óptico
### Carga de Software
Se realizaron las primeras pruebas de transferencia de datos desde LOGO! Soft Comfort hacia el módulo físico de Siemens, superando la curva de aprendizaje inicial sobre la comunicación del hardware.
### Montaje Mecánico
Instalación de soportes impresos en 3D para la cortina y ajuste fino de la alineación de sensores.
<img width="900" height="1600" alt="image" src="https://github.com/user-attachments/assets/3ae18be2-92bf-4541-bfb8-825f18702688" />
<img width="900" height="1600" alt="image" src="https://github.com/user-attachments/assets/f3c1d59c-54d6-4788-bf4e-b572e724cb4e" />


## Decisiones de ingeniería
| Decisión | Alternativas | Justificación |
|--------|-------------|---------------|
| Rediseño de Lógica de Control | Mantener el sistema de control original. | El sistema inicial no gestionaba correctamente los tiempos o señales del sistema óptico, lo que generaba fallos en la automatización. |
| Reubicación de Sensores Magnéticos | Re-imprimir soportes o nivelar toda la estructura. | Debido a una ligera inclinación de la cortina, los sensores no detectaban correctamente. Se decidió sobresalir los sensores magnéticos para asegurar el cierre del circuito sin reconstruir la base. |

<img width="900" height="1600" alt="image" src="https://github.com/user-attachments/assets/00a5b266-49ee-4158-9ab3-bc95e16fd2aa" />

## Problema técnico encontrado
Inicialmente no se comprendía el proceso de enlace y carga (Ethernet/IP) del software al PLC físico. Los soportes impresos en 3D quedaron demasiado exactos ("justos"), dificultando el ensamble. La inclinación de la cortina impedía que los sensores magnéticos hicieran contacto visual/físico con su contraparte. Se safó un cable del motor de 12V.
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/3f64e01c-5b99-4dda-b518-fa63cde03280" />


## Solución aplicada
Se investigó el protocolo de comunicación para el traslado de información al LOGO! Siemens, y se solicito apoyo directo del profesor encargado Camilo René Duque Becerra, logrando una carga exitosa del programa. Se ajustó la posición física de los sensores magnéticos, haciéndolos sobresalir de su posición original para compensar la inclinación de la cortina y garantizar que la señal llegue al PLC. Se cambió el tipo de motor, de 12V a 24V, modificando las conexiones de alimentación a las clemas del sistema y retirando el apoyo alternativo de alimentación al motor.
<img width="900" height="1600" alt="image" src="https://github.com/user-attachments/assets/8fefa7dc-7548-4a59-9ada-d19421948756" />


## Conexión con el curso
Se aplicó el concepto de comunicación industrial y protocolos de transferencia, además de la integración de sensores discretos (magnéticos y ópticos) dentro de un entorno de control lógico (MR2022). También se experimentó la importancia de las tolerancias de manufactura en el diseño de piezas para ensamble.

## Autoevaluación
- Muy perdido
- Con dudas
- Entendiendo✅
- Dominando
