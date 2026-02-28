# MR2025 | Registro Experimental de Pruebas de Sensores de Proximidad
### Curso: 
Análisis de Elementos de Mecatrónica
### Práctica: 
Conexión y validación de sensores con Siemens LOGO
### Equipo: 
Niñas ♡
### Integrantes:
Melissa Zúñiga Miranda A00573666 | Alexa Marisol Rodríguez Barajas A00574830 | Karla Ximena Jaime Neri A00573675
### Fecha:
25 de febrero del 2026

------------------------------------------------------------------------
## Ⅰ. Identificación del Sensor 

| Parámetro | Detalle de Configuración |
| :--- | :--- |
| **Tipo de Sensor** | Inductivo |
| **Marca / Modelo** | LJ12A3-4-Z/BX (NPN-NO)|
| **Tipo de Salida** | NPN-NO |
| **Alimentación** | 6-36 VDC |
| **Distancia Nominal** | 4mm (Según Datasheet) |
| **Conexión al LOGO!** | Digital |
| **Observaciones** | • Detecta únicamente objetos metálicos.<br>• Al ser NPN-NO, la salida se conecta a tierra cuando detecta el objeto.<br>• Común en conteo de piezas y automatización básica. |

| Parámetro | Detalle de Configuración |
| :--- | :--- |
| **Tipo de Sensor** | Capacitivo |
| **Marca / Modelo** | LJC18A3-B-Z/BX |
| **Tipo de Salida** | NPN-NO  |
| **Alimentación** | 6-36 VDC |
| **Distancia Nominal** | 8 mm (Según Datasheet) |
| **Conexión al LOGO!** | Digital |
| **Observaciones** | • Detecta tanto materiales metálicos como no metálicos (plásticos, madera, líquidos, granos, etc.).<br>• Ideal para aplicaciones de nivel, presencia de objetos no metálicos y control de procesos donde un sensor inductivo no sería suficiente.|

| Parámetro | Detalle de Configuración |
| :--- | :--- |
| **Tipo de Sensor** | Óptico |
| **Marca / Modelo** | E3F-DS30P1 |
| **Tipo de Salida** | PNP-NO |
| **Alimentación** |10-30 VDC |
| **Distancia Nominal** | 30 cm (Según Datasheet, en modo difuso) |
| **Conexión al LOGO!** | Digital |
| **Observaciones** | • Detecta objetos independientemente del material, siempre que interrumpan o reflejen el haz de luz.<br>• Ideal para conteo de piezas, detección de presencia en cintas transportadoras y aplicaciones donde se requiera mayor distancia de detección que un sensor inductivo o capacitivo. <br>• Puede verse afectado por polvo, suciedad o condiciones de iluminación ambiental.|

| Parámetro | Detalle de Configuración |
| :--- | :--- |
| **Tipo de Sensor** | Magnético |
| **Marca / Modelo** |FESTO SME-8M-DS-24V-K-2,5-OE |
| **Tipo de Salida** | PNP - NO |
| **Alimentación** |24 VDC (tensión nominal) |
| **Distancia Nominal** | Detecta la posición del pistón dentro del cilindro neumático mediante el campo magnético del imán integrado; no tiene “distancia nominal” fija como los inductivos/ópticos, depende de la proximidad al imán del pistón. (Según Datasheet) |
| **Conexión al LOGO!** | Digital |
| **Observaciones** |  • Diseñado específicamente para montaje en cilindros neumáticos FESTO. <br>• Detecta la posición del pistón sin contacto mecánico. <br>• No detecta objetos externos, solo el imán del pistón.|
 

------------------------------------------------------------------------
## Ⅱ. Resultados por Material Evaluado 
> [!NOTE]
> M: Sensor magnético | O: Sensor óptico | C: Sensor capacitivo | I: Sensor inductivo

> **Registro de comportamiento REAL medido en laboratorio.**

| Material | ¿Detecta? | Dist. Mín. Estable (mm) | Dist. Máx. Estable (mm) | Dist. Prom. Efectiva (mm) | Zona Inestable (mm) | Falsas Detecciones | Observaciones Técnicas |
| :--- | :---: | :--- | :--- | :--- | :--- | :--- | :--- |
| **Acero** | M: No <br> O: Sí <br> C: Sí <br> I: Sí <b>  |  M: - <br> O: 0 mm <br> C: 0 mm <br> I: 0 mm <b> | M: - <br> O: 200 mm <br> C: 1 mm <br> I: 0.5 mm <b> |  M: - <br> O: 100 mm <br> C: 0.5 mm <br> I: 0.25 mm <b> |  M: - <br> O: 200 - 230 mm <br> C: No hay <br> I: No hay <b> |  M: - <br> O: No <br> C: No <br> I: No <b> |  M: - <br> O: - <br> C: - <br> I: - <b> | M: N/A; requiere imán como activador (sensor magnético típico Hall/Reed). <br> O: Estable 0–200 mm; >200 mm sensible a alineación, brillo y luz ambiente. <br> C: Alcance corto (≤1 mm); muy sensible a separación y a cambios de montaje. <br> I: Metal detectado con buen “pick-up”, pero alcance corto (≤0.5 mm); vibración/holgura afecta repetibilidad. <b> |
| **Aluminio** |  M: No <br> O: Sí <br> C: Sí <br> I: Sí <b>  |  M: - <br> O: 160 mm <br> C: 0 mm <br> I: 0 mm <b> | M: - <br> O: 230 mm <br> C: 1 mm <br> I: 2 mm <b> |  M: - <br> O: 195 mm <br> C: 0.5 mm <br> I: 1 mm <b> |  M: - <br> O: 230 - 250 mm <br> C: 1-2 mm <br> I: No hay <b> |  M: - <br> O: No <br> C: No <br> I: No <b> |  M: - <br> O: - <br> C: - <br> I: - <b> | M: N/A; requiere imán como activador. <br> O: Ventana estable 160–230 mm; a distancias cercanas puede “cegarse” por alta reflectividad/saturación; >230 mm cae el retorno y aparece intermitencia. <br> C: Alcance corto (≤1 mm); depende de área efectiva, separación y ajuste de sensibilidad. <br> I: Detecta metal no ferroso; llega hasta 2 mm, dependiente de tamaño/posición del aluminio. <b> |
| **Plástico** | M: No <br> O: Sí <br> C: No <br> I: No <b>  |  M: - <br> O: 0 mm <br> C: - <br> I: - <b> | M: - <br> O: 250 mm <br> C: - <br> I: - <b> |  M: - <br> O: 125 mm <br> C: - <br> I: - <b> |  M: - <br> O: 260-280 mm <br> C: - <br> I: - <b> |  M: - <br> O: No <br> C: - <br> I: - <b> |  M: - <br> O: - <br> C: - <br> I: - <b> | M: N/A. <br> O: Depende de color/acabado (mate suele estabilizar mejor); translúcido/brillante afecta por reflejos y luz ambiente. <br> C: Sin respuesta en la prueba; probable sensibilidad/ajuste insuficiente o separación fuera de rango. <br> I: N/A (material no metálico). <b> |
| **Madera** | M: No <br> O: Sí <br> C: Sí <br> I: No <b>  |  M: - <br> O: 0 mm <br> C: 0 mm <br> I: - <b> | M: - <br> O: 365 mm <br> C: 0.5 mm <br> I: - <b> |  M: - <br> O: 182.5 mm <br> C: 0.25 mm <br> I: - <b> |  M: - <br> O: 370-410 mm <br> C: 1 mm <br> I: No <b> |  M: - <br> O: No <br> C: Sí <br> I: - <b> |  M: - <br> O: - <br> C: Varias por humedad/superficie <br> I: - <b> | M: N/A. <br> O: Muy buen alcance por reflexión difusa; >365 mm cae señal y depende más de alineación. <br> C: Falsas por humedad/porosidad/superficie irregular y proximidad de mano/cables; requiere recalibración y distancia fija. <br> I: N/A (material no metálico). <b> |
| **Vidrio** | M: No <br> O: No confiable <br> C: Sí <br> I: No <b>  |  M: - <br> O: 0 mm <br> C: 0 mm mm <br> I: - <b> | M: - <br> O: 3 mm <br> C: 1-3 mm <br> I: - <b> |  M: - <br> O: 1 mm <br> C: 1-2 mm <br> I: - <b> |  M: - <br> O: Depende de transparencia <br> C: 1-2 mm <br> I: - <b> |  M: No <br> O: No <br> C: No <br> I: No <b> |  M: - <br> O: - <br> C: - <br> I: - <b> | M: N/A. <br> O: Vidrio transparente complica detección por transmisión/reflejo especular; suele requerir reflector, modo barrera o ajuste fino de sensibilidad/ángulo. <br> C: Respuesta depende de espesor y del montaje; si no aparece lectura, suele ser sensibilidad insuficiente o separación fuera de rango. <br> I: N/A. <b> |
| **Agua** | M: No <br> O: Sí <br> C: Sí <br> I: No <b>  |  M: - <br> O: 0 mm <br> C: 0 mm <br> I: - <b> | M: - <br> O: 120 mm <br> C: 1 mm <br> I: - <b> |  M: - <br> O: 60 mm <br> C: 0.5 mm <br> I: - <b> |  M: - <br> O: 120 - 150 mm <br> C: No hay <br> I: - <b> |  M: - <br> O: Sí <br> C: No <br> I: - <b> |  M: - <br> O: Varias por reflejo/ondas <br> C: - <br> I: - <b> | M: N/A. <br> O: Falsas por reflejos, menisco y ondas; mejora controlando iluminación, ángulo y estabilizando superficie. <br> C: Útil para presencia/nivel; depende del recipiente (material/espesor) y objetos cercanos; requiere calibración fija. <br> I: N/A (líquido no metálico). <b> |
| **Imán** | M: Sí <br> O: Sí <br> C: Sí <br> I: Sí <b>  |  M: 0 mm  <br> O: 0 mm <br> C: 0 mm <br> I: - <b> | M: 6 mm <br> O: 148 mm <br> C: 2 mm <br> I: - <b> |  M: 3 mm <br> O: 74 mm <br> C: 1 mm <br> I: - <b> |  M: 7 mm <br> O: 14-163 mm <br> C: No hay <br> I: - <b> |  M: No <br> O: No <br> C: No <br> I: Sí <b> | M: - <br> O: - <br> C: - <br> I: Falsas por metal cercano <b> | M: Rango corto y repetible; polaridad/orientación cambia el disparo. <br> O: Depende de alineación y de la superficie del imán (brillo/ángulo); luz ambiente puede introducir intermitencia. <br> C: Alcance corto (≤2 mm); sensible a proximidad de mano/objetos y a calibración. <br> I: Detecta por masa metálica/entorno; falsas cuando hay otros metales cerca; faltó registrar rango en mm (solo evento ON/OFF). <b> |
------------------------------------------------------------------------
## Ⅲ. Prueba de Distancia Incremental

| Distancia (mm) | LED del sensor (ON/OFF) | Entrada en LOGO (1/0) | ¿Detección consistente? (Sí/No) | Comentarios |
| :---: | :--- | :--- | :--- | :--- |
| 0  | M: ON <br> O: ON <br> I: ON <br> C: ON | M: 1 <br> O: 1 <br> I: 1 <br> C: 1 | M: Sí <br> O: Sí <br> I: Sí <br> C: Sí | Todos detectan en contacto directo. |
| 2  | M: ON <br> O: ON <br> I: ON <br> C: ON | M: 1 <br> O: 1 <br> I: 1 <br> C: 1 | M: Sí <br> O: Sí <br> I: Sí <br> C: Sí | Magnético aún dentro de rango, inductivo y capacitivo en su límite nominal; óptico estable. |
| 4  | M: ON <br> O: ON <br> I: ON <br> C: OFF | M: 1 <br> O: 1 <br> I: 1 <br> C: 0 | M: Sí <br> O: Sí <br> I: Sí <br> C: No | Capacitivo pierde detección y el inductivo aún responde. |
| 6  | M: ON <br> O: ON <br> I: OFF <br> C: OFF | M: 1 <br> O: 1 <br> I: 0 <br> C: 0 | M: Sí <br> O: Sí <br> I: No <br> C: No | Inductivo fuera de rango, capacitivo ya no detecta y óptico sigue estable. |
| 8  | M: ON <br> O: ON <br> I: OFF <br> C: OFF | M: 1 <br> O: 1 <br> I: 0 <br> C: 0 | M: Sí <br> O: Sí <br> I: No <br> C: No | Solo magnético y óptico mantienen detección. |
| 10 | M: ON <br> O: ON <br> I: OFF <br> C: OFF | M: 1 <br> O: 1 <br> I: 0 <br> C: 0 | M: Sí <br> O: Sí <br> I: No <br> C: No | Óptico aún dentro de rango. |
| 12 | M: ON <br> O: ON <br> I: OFF <br> C: OFF | M: 1 <br> O: 1 <br> I: 0 <br> C: 0 | M: Sí <br> O: Sí <br> I: No <br> C: No | Magnético estable si hay imán, óptico sigue detectando. |
| 14 | M: ON <br> O: ON <br> I: OFF <br> C: OFF | M: 1 <br> O: 1 <br> I: 0 <br> C: 0 | M: Sí <br> O: Sí <br> I: No <br> C: No | Igual comportamiento: solo magnético y óptico activos. |
| 16 | M: ON <br> O: ON <br> I: OFF <br> C: OFF | M: 1 <br> O: 1 <br> I: 0 <br> C: 0 | M: Sí <br> O: Sí <br> I: No <br> C: No | Óptico aún en rango; inductivo y capacitivo fuera. |

*(Ajustar rango según especificación del sensor)*
------------------------------------------------------------------------
## Ⅳ. Comparación vs Especificación del Fabricante
| Parámetro                  | Valor Datasheet                          | Valor Experimental                  | Error (%) |
|-----------------------------|------------------------------------------|-------------------------------------|-----------|
| **Distancia nominal**       | I: 4 mm <br> C: 8 mm <br> O: 300 mm <br> M: 2–6 mm | I: 0–4 mm estable <br> C: 0–1 mm estable <br> O: 200–250 mm estable <br> M: 0–6 mm estable | I: 0–25% <br> C: 75–90% <br> O: 20–30% <br> M: dentro de rango |
| **Tiempo de respuesta**     | I: ≤2 ms <br> C: ≤10 ms <br> O: ≤1 ms <br> M: ≤1 ms | No medido directamente; percepción visual estable | N/A |
| **Tipo de material recomendado** | I: Metales <br> C: Metales y no metálicos <br> O: Cualquier objeto opaco o reflejante <br> M: Imán | I: Detectó acero y aluminio <br> C: Detectó madera, agua, aluminio <br> O: Detectó acero, aluminio, plásticos, madera, agua <br> M: Solo imán | Coincidente con especificación |

------------------------------------------------------------------------
# Análisis Técnico del Equipo5️⃣
## 5.1 ¿Coincide la distancia real con la nominal?
Respuesta:
------------------------------------------------------------------------
## 5.2 ¿Qué fenómeno físico explica el comportamiento observado?
(Ejemplo: corrientes de Foucault, constante dieléctrica, reflexión
óptica, campo magnético)
Respuesta:
------------------------------------------------------------------------
## 5.3 ¿Qué materiales generan mejor desempeño? ¿Por qué?
Respuesta:
------------------------------------------------------------------------
## 5.4 ¿Detectaron zonas muertas o inestabilidad?
Respuesta:
------------------------------------------------------------------------
## 5.5 ¿Este sensor sería adecuado para la situación problema del curso?
Justificar técnica y económicamente.
Respuesta:
------------------------------------------------------------------------
# Matriz de Decisión Técnica6️⃣
----------------------------------------------------------------------------
Criterio Peso (1--5) Evaluación del sensor (1--5) Resultado ponderado
------------- ------------ ---------------------------- --------------------
Precisión
Distancia
útil
Robustez
industrial
Inmunidad a
ruido
Costo
Facilidad de
integración
con LOGO
**TOTAL**
----------------------------------------------------------------------------
------------------------------------------------------------------------
# Conclusión Ingenieril7️⃣
Redactar una conclusión técnica defendible:
- ¿Recomendarían este sensor?
- ¿En qué condiciones sí?
- ¿En qué condiciones no?
- ¿Qué riesgos industriales identifican?
Conclusión:
------------------------------------------------------------------------
# Evidencia8️⃣
- Fotografías del montaje:
- Capturas del programa en LOGO:
- Video corto de funcionamiento:
- Datasheet utilizado (link o archivo en repositorio):
------------------------------------------------------------------------
# Bitácora de Aprendizaje9️⃣
¿Qué aprendieron técnicamente sobre sensores de proximidad que no sabían
antes?
Respuesta:
------------------------------------------------------------------------
> Este documento forma parte del proceso de validación experimental⚙️
> para la selección de sensores dentro del proyecto integrador MR2022.
