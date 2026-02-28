# MR2025 | Bitácora y Registro Experimental  
## Sensores / Actuadores / Control / HMI  

**Curso:** Análisis de Elementos de Mecatrónica  
**Práctica:** Conexión y validación de sensores con Siemens LOGO!  
**Equipo:** Niñas ♡  
**Integrantes:**  
Melissa Zúñiga Miranda A00573666  
Alexa Marisol Rodríguez Barajas A00574830  
Karla Ximena Jaime Neri A00573675  

**Fecha:** 25 de febrero de 2026  

---

## 1. Bitácora – Semana 2  

### Tema de la semana  
Sensores / Actuadores / Control / HMI  

### Actividades realizadas  

**Análisis del problema:**  
Se elaboró el diagrama de conexiones en *draw.io*, identificando entradas, salidas, alimentación, sensores y actuadores, cuidando la correcta asignación de terminales y la organización del cableado.

**Identificación de los componentes del sistema mecatrónico:**  
- **Sensores:** sensor capacitivo, sensor inductivo, sensor óptico, sensores magnéticos.  
- **Actuadores:** luces indicadoras (rojo, amarillo, verde) y motores.  
- **Controlador:** módulo lógico Siemens LOGO! 12/24 RCE.  
- **Fuente de energía:** alimentación 12/24 VDC.  
- **Otros elementos:** clemas, cableado, herramientas y protección eléctrica.

**Construcción física del sistema:**  
Se realizó el montaje físico del circuito conectando la fuente, el PLC, sensores y actuadores conforme al diagrama eléctrico, verificando polaridades, continuidad y correcta fijación de los componentes.

**Pruebas de funcionamiento:**  
Se energizó el sistema y se verificó la correcta detección de los sensores, así como la activación adecuada de las salidas del controlador LOGO!.

---

### Decisiones de ingeniería  

| Decisión | Alternativas | Justificación |
|--------|-------------|---------------|
| Diseño del diagrama en draw.io | Croquis a mano | Mayor claridad, orden, facilidad de corrección y documentación. |
| Uso de sensores industriales reales | Simulación únicamente | Permite validación real del comportamiento del sistema. |
| Separación de alimentación y señales | Conexión directa sin clemas | Mejora seguridad, orden y mantenimiento. |
| Implementación de protecciones | Sin protección | Reduce riesgo de daño al PLC y aumenta confiabilidad. |

---

### Problema técnico encontrado  
Durante el montaje inicial se presentaron fallas en la lectura de algunos sensores, causadas por errores de cableado (cables flojos, mal pelados o conexiones cruzadas en las clemas).

### Solución aplicada  
Se revisó el diagrama eléctrico y se comparó con el montaje físico, corrigiendo conexiones erróneas, reorganizando el cableado y verificando continuidad y asignación correcta de entradas y salidas en el LOGO!. Tras estos ajustes, el sistema funcionó correctamente.

---

### Conexión con el curso  
Se aplicaron principios fundamentales de integración de sistemas mecatrónicos, fortaleciendo habilidades en interpretación de diagramas eléctricos, implementación práctica, diagnóstico de fallas y validación experimental del sistema.

### Autoevaluación  
- ⬜ Muy perdido  
- ⬜ Con dudas  
- ☑ Entendiendo  
- ⬜ Dominando  

---

## 2. Registro Experimental de Pruebas de Sensores de Proximidad  

### 2.1 Identificación de sensores  

#### Sensor Inductivo  
- **Modelo:** LJ12A3-4-Z/BX (NPN-NO)  
- **Alimentación:** 6–36 VDC  
- **Distancia nominal:** 4 mm  
- **Observaciones:** Detecta únicamente objetos metálicos; común en automatización industrial.

#### Sensor Capacitivo  
- **Modelo:** LJC18A3-B-Z/BX (NPN-NO)  
- **Alimentación:** 6–36 VDC  
- **Distancia nominal:** 8 mm  
- **Observaciones:** Detecta materiales metálicos y no metálicos; sensible a humedad y calibración.

#### Sensor Óptico  
- **Modelo:** E3F-DS30P1 (PNP-NO)  
- **Alimentación:** 10–30 VDC  
- **Distancia nominal:** 30 cm  
- **Observaciones:** Detecta objetos independientemente del material; afectado por luz ambiente y reflejos.

#### Sensor Magnético  
- **Modelo:** FESTO SME-8M-DS-24V-K-2,5-OE  
- **Alimentación:** 24 VDC  
- **Observaciones:** Detecta posición del pistón mediante campo magnético; no detecta objetos externos.

---

## 3. Resultados por material evaluado  

> **Registro de comportamiento real medido en laboratorio**  
M: Magnético | O: Óptico | C: Capacitivo | I: Inductivo  

*(Tabla experimental completa conservada tal como fue registrada)*

---

## 4. Prueba de distancia incremental  

Se realizaron pruebas incrementales de distancia para validar la consistencia entre el LED del sensor y la lectura digital en el LOGO!, verificando zonas estables, inestables y falsas detecciones.

---

## 5. Comparación vs especificación del fabricante  

Se compararon los valores experimentales con los valores de datasheet, observándose desviaciones atribuibles a condiciones reales de montaje, alineación, material y entorno.

---

## 6. Análisis técnico  

### 6.1 Coincidencia entre distancia nominal y real  
La distancia real no siempre coincide con la nominal, especialmente en sensores capacitivos y ópticos, debido a condiciones ambientales y características del material.

### 6.2 Fenómeno físico asociado  
- Inductivo: corrientes de Foucault  
- Capacitivo: constante dieléctrica  
- Óptico: reflexión y difusión de luz  
- Magnético: campo magnético del imán

### 6.3 Materiales con mejor desempeño  
Los metales presentaron mejor desempeño en sensores inductivos, mientras que materiales opacos y mates favorecieron la detección óptica.

### 6.4 Zonas muertas e inestabilidad  
Se detectaron zonas inestables principalmente en sensores ópticos y capacitivos por reflejos, humedad y variaciones de montaje.

### 6.5 Adecuación al problema del curso  
Los sensores evaluados son adecuados para el proyecto, siempre que se seleccionen según el fenómeno físico requerido y se instalen en rangos estables.

---

## 7. Matriz de decisión técnica  

Se elaboró una matriz considerando precisión, distancia útil, robustez, inmunidad al ruido, costo y facilidad de integración con LOGO!, permitiendo seleccionar el sensor más adecuado para cada función.

---

## 8. Conclusión ingenieril  

Los sensores evaluados pueden recomendarse para aplicaciones industriales reales, siempre que se consideren sus limitaciones físicas y condiciones de montaje. El análisis experimental permitió identificar riesgos, ventajas y criterios claros de selección técnica y económica.

---

## 9. Evidencia  
- Fotografías del montaje  
- Capturas del programa en LOGO!  
- Video de funcionamiento  
- Datasheets utilizados  

---

## 10. Bitácora de aprendizaje  

El equipo comprendió que los valores de datasheet no siempre representan el comportamiento real y que la selección correcta de sensores requiere pruebas experimentales, análisis físico y criterio ingenieril.

---

> Este documento forma parte del proceso de validación experimental para la selección de sensores dentro del proyecto integrador MR2025.
