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
# Ⅱ. Resultados por Material Evaluado 
> [!NOTE]
> M: Sensor magnético | O: Sensor óptico | C: Sensor capacitivo | I: Sensor inductivo

> **Registro de comportamiento REAL medido en laboratorio.**

| Material | ¿Detecta? | Dist. Mín. Estable (mm) | Dist. Máx. Estable (mm) | Dist. Prom. Efectiva (mm) | Zona Inestable (mm) | Falsas Detecciones | Observaciones Técnicas |
| :--- | :---: | :--- | :--- | :--- | :--- | :--- | :--- |
| **Acero** | M: No <br> O: No <br> C: No <br> I: No <b>  |  M: No <br> O: No <br> C: No <br> I: No <b> | M: No <br> O: No <br> C: No <br> I: No <b> |  M: No <br> O: No <br> C: No <br> I: No <b> |  M: No <br> O: No <br> C: No <br> I: No <b> |  M: No <br> O: No <br> C: No <br> I: No <b> |  M: No <br> O: No <br> C: No <br> I: No <b> |
| **Aluminio** |  M: No <br> O: No <br> C: No <br> I: No <b>  |  M: No <br> O: No <br> C: No <br> I: No <b> | M: No <br> O: No <br> C: No <br> I: No <b> |  M: No <br> O: No <br> C: No <br> I: No <b> |  M: No <br> O: No <br> C: No <br> I: No <b> |  M: No <br> O: No <br> C: No <br> I: No <b> |  M: No <br> O: No <br> C: No <br> I: No <b> |
| **Cobre** | | | | | | | |
| **Plástico** | | | | | | | |
| **Madera** | | | | | | | |
| **Vidrio** | | | | | | | |
| **Agua** | | | | | | | |
| **Imán** | | | | | | | |

------------------------------------------------------------------------
# Ⅲ. Prueba de Distancia Incremental
> Mover el objeto en incrementos regulares y registrar comportamiento
> del LED y del LOGO.
-------------------------------------------------------------------------------
Distancia LED del sensor Entrada en ¿Detección Comentarios
(mm) (ON/OFF) LOGO (1/0) consistente? (Sí/No)
----------- ---------------- -------------- --------------------- -------------
0
2
4
6
8
10
12
14
16
-------------------------------------------------------------------------------
*(Ajustar rango según especificación del sensor)*
------------------------------------------------------------------------
# Ⅳ. Comparación vs Especificación del Fabricante
Parámetro Valor Datasheet Valor Experimental Error
(%)
--------------------------------- ----------------- --------------------
-----------
Distancia nominal
Tiempo de respuesta (si aplica)
Tipo de material recomendado
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
