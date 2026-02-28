# Bitácora – Semana 2
## Tema de la semana
(Sensores / Actuadores / Control / HMI)
## Durante la segunda semana, el equipo llevó a cabo la conexión, validación y caracterización experimental de sensores de proximidad (inductivo, capacitivo, óptico y magnético) integrados a un controlador LOGO! Siemens operando a 24 VDC, en el marco del proyecto de automatización de una cortina industrial.

Se realizaron pruebas sistemáticas en laboratorio para evaluar el comportamiento real de cada sensor frente a distintos materiales (acero, aluminio, plástico, madera, vidrio, agua e imán), registrando distancias mínimas, máximas, zonas inestables y falsas detecciones. Paralelamente, se verificó la correcta lectura de las señales digitales en el LOGO!, asegurando compatibilidad eléctrica (NPN/PNP) y coherencia entre el LED del sensor y la entrada lógica del controlador.

Estas pruebas permitieron validar qué sensores son adecuados para detección de obstáculos, límites de carrera, presencia humana y seguridad operativa dentro del sistema de la cortina automatizada.
Describe brevemente lo que trabajó el equipo.
## Decisiones de ingeniería
| Decisión                            | Alternativas                                                                          | Justificación                                                                                                     |
| ----------------------------------- | ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Selección de sensores de proximidad | Usar un solo tipo de sensor vs. **Evaluar inductivo, capacitivo, óptico y magnético** | Comparar tecnologías permitió elegir el sensor correcto según material, distancia y nivel de seguridad requerido. |
| Sensor de seguridad para personas   | Sensor inductivo/capacitivo vs. **Sensor óptico infrarrojo**                          | El sensor óptico ofrece mayor distancia de detección y no depende del material del obstáculo.                     |
| Sensor de límite de carrera         | Temporización por software vs. **Sensor magnético**                                   | El sensor magnético garantiza repetibilidad y evita forzar el motor por errores de tiempo.                        |
| Integración eléctrica               | Conexión directa vs. **Interfaz digital compatible con LOGO!**                        | Asegura confiabilidad, facilidad de programación y cumplimiento del estándar industrial a 24 VDC.                 |

## Problema técnico encontrado
Durante las pruebas experimentales se detectó inestabilidad y falsas detecciones en algunos sensores, principalmente:

Sensor óptico afectado por reflexión, brillo del material y luz ambiental, especialmente con agua, aluminio y superficies brillantes.

Sensor capacitivo sensible a humedad, proximidad de la mano y variaciones de montaje, generando falsas detecciones en madera y agua.

Diferencias notables entre la distancia nominal del datasheet y la distancia efectiva real, particularmente en sensores inductivos y capacitivos.

## Solución aplicada
El problema se resolvió mediante:

Ajuste de distancia de montaje dentro de la zona estable detectada experimentalmente.

Reorientación y alineación del sensor óptico para minimizar reflejos.

Priorización de sensores según su fenómeno físico (óptico para seguridad, magnético para límites, inductivo para metal).

Validación cruzada entre el LED del sensor y la entrada lógica del LOGO!, garantizando detección consistente antes de integrar al sistema final.

## Conexión con el curso
Esta semana se aplicaron directamente conceptos de sensores industriales de proximidad, fenómenos físicos de detección (campo magnético, corrientes inducidas, constante dieléctrica y reflexión óptica) y adquisición de señales digitales en sistemas mecatrónicos.
Asimismo, se reforzó el enfoque de selección de sensores basada en evidencia experimental, criterio fundamental del curso MR2022 para justificar decisiones técnicas dentro de un proyecto real.

## Autoevaluación
- Muy perdido⬜
- Con dudas⬜
- Entendiendo⬜
- Dominando x
