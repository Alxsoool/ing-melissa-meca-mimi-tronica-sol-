# Bitácora – Semana 4
## Tema de la semana
(Sensores / Actuadores / Control / HMI)

## Actividades realizadas
### Programación y Depuración
Se migró de una lógica de control básica a una más robusta para corregir errores de detección en el sistema óptico
### Carga de Software
Se realizaron las primeras pruebas de transferencia de datos desde LOGO! Soft Comfort hacia el módulo físico de Siemens, superando la curva de aprendizaje inicial sobre la comunicación del hardware.
### Montaje Mecánico
Instalación de soportes impresos en 3D para la cortina y ajuste fino de la alineación de sensores

## Decisiones de ingeniería
| Decisión | Alternativas | Justificación |
|--------|-------------|---------------|
| Rediseño de Lógica de Control | Mantener el sistema de control original. | El sistema inicial no gestionaba correctamente los tiempos o señales del sistema óptico, lo que generaba fallos en la automatización. |
| Reubicación de Sensores Magnéticos | Re-imprimir soportes o nivelar toda la estructura. | Debido a una ligera inclinación de la cortina, los sensores no detectaban correctamente. Se decidió sobresalir los sensores magnéticos para asegurar el cierre del circuito sin reconstruir la base. |

## Problema técnico encontrado
Inicialmente no se comprendía el proceso de enlace y carga (Ethernet/IP) del software al PLC físico. Los soportes impresos en 3D quedaron demasiado exactos ("justos"), dificultando el ensamble. La inclinación de la cortina impedía que los sensores magnéticos hicieran contacto visual/físico con su contraparte.

## Solución aplicada
Se investigó el protocolo de comunicación para el traslado de información al LOGO! Siemens, y se solicito apoyo directo del profesor encargado Camilo René Duque Becerra, logrando una carga exitosa del programa. Se ajustó la posición física de los sensores magnéticos, haciéndolos sobresalir de su posición original para compensar la inclinación de la cortina y garantizar que la señal llegue al PLC.

## Conexión con el curso
Se aplicó el concepto de comunicación industrial y protocolos de transferencia, además de la integración de sensores discretos (magnéticos y ópticos) dentro de un entorno de control lógico (MR2022). También se experimentó la importancia de las tolerancias de manufactura en el diseño de piezas para ensamble.

## Autoevaluación
- Muy perdido
- Con dudas
- Entendiendo✅
- Dominando
