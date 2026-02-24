# Bitácora – Semana 1

## Tema de la semana
Durante esta primer semana, revisamos los temas de la situación problema. En conreto, este proyecto consiste en el diseño e integración de un sistema mecatrónico para automatizar una cortina industrial de hule termo-formado con dimensiones y peso variables. El sistema debe integrar sensores para definir límites de carrera y detectar obstáculos por seguridad, así como actuadores capaces de operar a velocidades variables (alta al arranque y baja al cierre) para cumplir con tiempos de apertura configurables de 3 a 5 segundos. La solución requiere una interfaz de usuario (HMI) que permita gestionar dos perfiles: un operador, encargado de la supervisión de alarmas y el control en modos manual o automático; y un supervisor, con privilegios para calibrar límites de movimiento, tiempos de espera y parámetros técnicos de velocidad. Finalmente, el control debe garantizar un ciclo automático de apertura, espera y cierre seguro, el cual se reinicia si los sensores detectan el paso de personas o vehículos durante el descenso.

La automatización de la cortina industrial se realizará mediante un sistema mecatrónico controlado por un módulo LOGO! de Siemens, que gestiona sensores de posición y seguridad junto a un actuador de velocidad variable. Este dispositivo permite programar ciclos automáticos con tiempos de apertura (3-5 s) y espera configurables, garantizando la seguridad al revertir el movimiento ante obstáculos. Finalmente, el software facilita la simulación del proyecto y la creación de una interfaz (HMI) con niveles de acceso para operador (manejo y alarmas) y supervisor (ajuste de parámetros técnicos), optimizando el control en un formato compacto y profesional.

Aprendimos a utilizar el software LOGO!. Nos enfocamos en comprender la estructura del Siemens LOGO! 12/24RCE, un relevador programable versátil que cuenta con alimentación de 12/24 V DC, 8 entradas digitales (donde 4 pueden funcionar como analógicas de 0-10V) y 4 salidas digitales de tipo relé. Entre sus capacidades técnicas exploramos su memoria de hasta 400 bloques, conectividad vía Ethernet, servidor web integrado y la interfaz para gestión de datos mediante tarjeta Micro SD.

Durante la sesión práctica [18 de febrero de 2026], se nos proporcionó el kit de materiales para el proyecto, el cual incluye: 

### Inventario de Materiales - Proyecto Cortina Industrial

| Cantidad | Material | Descripción Técnica | Función en el Proyecto |
| :---: | :--- | :--- | :--- |
|10| Clemas Grises | Bornes de conexión para riel DIN. | Organización de terminales de señal y neutros. |
|7| Clemas Beige | Bornes de conexión para riel DIN. | Organización de líneas de voltaje positivo (24V). |
|1| Clema Porta Fusible | Bloque con protección eléctrica. | Protección del PLC LOGO! y sensores contra cortocircuitos. |
|1| Fuente DC 24V / 14.5 A | Fuente conmutada de 350 W. | Suministrar energía a todo el sistema (conversión AC a DC). |
|3| Sensores Festo SME-8M | Sensores magnéticos de proximidad. | Detectar los límites de carrera magnéticos del eje. |
|1| Sensor Capacitivo | LJC18A3-B-Z/BX (NPN-NO). | Detectar la presencia del material de la cortina (hule). |
|1| Sensor Inductivo | LJ12A3-4-Z/BX (NPN-NO). | Detectar las barras metálicas de tensión en la base. |
|1| Sensor Infrarrojo | E3F-DS30P1 (PNP-NO). | Sistema de seguridad para detectar obstáculos/personas. |
|1| Lámpara ANDON | Torre de 3 colores. | Señalización visual del estado del sistema (Stop/Wait/Go). |
|1| Motor con Engrane | Actuador de 24VDC. | Proporcionar el torque para levantar el peso de la cortina. |
|2| Relevador Industrial | HH54P (MY4NJ). | Conmutación de potencia entre el LOGO! y el motor. |
|1| Riel DIN | Perfil perforado 35x7.5mm. | Base de montaje para los componentes eléctricos. |
|1| Tubo de PVC | Tubería para agua caliente. | Eje rotatorio para el enrollado de la malla. |
|1| Malla Sintética | Tela color naranja. | Simulación del cuerpo de la cortina industrial. |
|1| Tablero MDF | Base de 30x30 cm. | Soporte estructural para el montaje del prototipo. |

## Actividades realizadas
El equipo realizó un análisis profundo de la situación problema, identificando actores, modos de operación y protocolos de seguridad. Tras consultar los estándares del proyecto en el módulo del reto, iniciamos la gestión en GitHub, donde configuramos el Project Board, abrimos los primeros Issues para la distribución de tareas y participamos en el foro de Discussions para formalizar el arranque del equipo.

En la sesión práctica 1 [11 de febrero 2026], desarrollamos el ejercicio "Hola Mundo" en LOGO!, logrando implementar una secuencia básica de luces y relevadores. Esta actividad nos permitió dominar el ciclo de editar, cargar y probar el controlador, generando como evidencia un video de simulación de 50 segundos. 
Configuramos el entorno de trabajo en LOGO!, seleccionando el modelo 12/24RCE para asegurar la compatibilidad con el hardware del laboratorio. Diseñamos un programa de control secuencial utilizando bloques de tiempo para activar tres salidas en intervalos de 5, 1 y 4 segundos respectivamente, configurando un bucle de repetición indefinida. Finalmente, ejecutamos el ciclo de carga y prueba vía Ethernet, verificando el funcionamiento físico de los relevadores y documentando el éxito de la lógica mediante un video de simulación de 50 segundos.

<img width="1490" height="909" alt="image" src="https://github.com/user-attachments/assets/752eee68-b941-465c-878f-4dde87d3ff02" />


Con la base técnica definida en clase, el equipo se dividió la elaboración del Entregable H1, asignando la redacción de requisitos a Marisol y Ximena, la tabla de I/O a Marisol y Melissa, y el diagrama de bloques a Melissa.

Finalmente, integramos el inventario de materiales proporcionado por la Escuela de Ingenierías del Tecnológico de Monterrey, vinculando cada componente con su función lógica y eléctrica. 

<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/0178d6f4-4b12-465c-91c4-a53012f007d4" />


<img width="778" height="860" alt="image" src="https://github.com/user-attachments/assets/62f72de3-371f-44b4-9aa2-fc2959f3a7ed" />


## Decisiones de ingeniería

| Decisión | Alternativas | Justificación |
| :--- | :--- | :--- |
| **Cerebro del Sistema** | Arduino/PC vs. **LOGO! Siemens** | Usamos LOGO! por ser estándar industrial, resistente y fácil de programar para proyectos de automatización. |
| **Eje de Enrollado** | Metal/Madera vs. **Tubo de PVC** | El PVC es ligero, fácil de cortar y se adapta perfecto al motor para el prototipo. |
| **Material de Cortina** | Hule real vs. **Malla naranja** | La malla simula la transparencia y flexibilidad de la cortina industrial sin añadir peso excesivo al prototipo. |
| **Protección** | Conexión directa vs. **Clema con fusible** | Decidimos proteger el LOGO! y los sensores con un fusible para evitar daños por errores de conexión. |
| **Seguridad de Paso** | Paro manual vs. **Sensor Infrarrojo** | Elegimos el sensor IR para que la cortina suba automáticamente si alguien pasa, cumpliendo con la seguridad del cliente. |
| **Control de Carga** | Salida directa vs. **Relevadores HH54P** | Los relevadores actúan como interruptores de potencia para no forzar las salidas internas del LOGO!. |
| **Orden del Tablero** | Cables sueltos vs. **Riel DIN y Clemas** | Usar riel DIN y clemas de colores (gris/beige) ayuda a no confundir las señales y que el tablero se vea profesional. |
| **Aviso de Estados** | Pantalla vs. **Lámpara ANDON** | La lámpara permite saber si la cortina está funcionando o en falla desde lejos, sin tener que leer la pantalla. |
| **Detección de Tope** | Solo tiempo vs. **Sensores Magnéticos** | Usamos sensores físicos para que la cortina se detenga exactamente en los límites y no se fuerce el motor. |
| **Gestión de Tareas** | Mensajes vs. **GitHub Issues/Projects** | Decidimos usar GitHub para dividirnos el trabajo (Marisol, Ximena, Melissa) y que todos supieran qué falta por hacer. |
| **Validación Lógica** | Probar directo vs. **Simulación previa** | Grabamos un video de 50s de la simulación para estar seguras de que la lógica funcionaba antes de conectar el hardware. |
| **Acceso de Usuarios** | Acceso libre vs. **Contraseñas en HMI** | Definimos niveles (Operador/Supervisor) para que solo el encargado pueda cambiar velocidades y tiempos técnicos. |

## Problema técnico encontrado

**Descripción del problema:**
Durante el desarrollo del **Entregable H1**, el equipo enfrentó una serie de obstáculos críticos relacionados con la gestión de la plataforma **GitHub** y la interpretación de los lineamientos del curso. El problema principal fue la falta de alineación entre las expectativas técnicas y el conocimiento previo del equipo sobre herramientas de control de versiones y gestión de proyectos.

**Desafíos y Dificultades Detectadas:**

* **Confusión Normativa e Instructiva:** Al momento de elaborar la documentación, se generó un conflicto de interpretación entre la sección de **"Estándares del Proyecto"** (que define la organización técnica del repositorio) y las instrucciones específicas del **Entregable H1**. No lográbamos identificar un orden jerárquico claro, lo que resultó en incertidumbre sobre cómo estructurar las carpetas y los archivos `.md` de manera que cumplieran con ambos criterios simultáneamente.
* **Limitaciones de Acceso en GitHub Projects:** Experimentamos una barrera técnica importante al intentar organizar el flujo de trabajo. La creación de **Issues** y su vinculación al **Project** del equipo fue una situación de alta dificultad, ya que desconocíamos la necesidad de contar con permisos de **Editor/Administrador** dentro de las funciones avanzadas de GitHub para poder mover tarjetas, asignar responsables y conectar los avances con el tablero general.
* **Incertidumbre en la Comunicación (Discussions):** El requisito de realizar un **Kickoff** a través de las discusiones del repositorio causó confusión, debido a que no existía un formato preestablecido o una guía clara sobre el nivel de formalidad y la estructura de información que se esperaba para este primer registro oficial del equipo.
* **Curva de Aprendizaje en la Documentación:** El proceso de transformar el análisis de la situación problema en requisitos verificables bajo los estándares solicitados fue complejo, especialmente al intentar navegar la interfaz de GitHub mientras simultáneamente tratábamos de descifrar la ruta lógica de la documentación requerida.

## Solución aplicada
Para superar los obstáculos técnicos y de organización, el equipo ejecutó un plan de acción basado en dos pilares principales:

1. **Asesoría Técnica Especializada:**
   Se organizó una sesión de consultoría directa con el **Profesor Asesor Camilo René Duque Becerra** [19 de febrero de 2026]. Durante esta reunión, el equipo presentó las dudas específicas sobre la jerarquía de los documentos y las contradicciones detectadas entre los "Estándares del Proyecto" y las rúbricas del Hito 1. Además de aclarar el principal uso de los archivos README.md dentro de cada carpeta. El profesor aclaró los criterios de evaluación y la estructura de organización esperada en el repositorio, lo que nos permitió unificar la visión del equipo y establecer una ruta de trabajo clara para la documentación.

2. **Capacitación Técnica en GitHub:**
   De forma paralela, cada integrante del equipo realizó una fase de autoaprendizaje mediante **tutoriales de GitHub**. Este proceso fue fundamental para:
   * **Entendimiento de Roles:** Comprender que se requerían permisos de "Administrador/Editor" para que todas las integrantes pudieran interactuar con el *Project Board*.
   * **Dominio de Herramientas:** Aprender a vincular correctamente los *Issues* con el progreso del proyecto y a utilizar la sección de *Discussions* para el registro formal del Kickoff.
   * **Estandarización:** Aplicar las mejores prácticas de Markdown para que la documentación fuera profesional y fácil de leer.

## Conexión con el curso
Esta semana aplicamos el concepto de Lógica de Control Programada mediante la configuración de un relevador inteligente LOGO!, lo que nos permitió materializar la arquitectura de un sistema automatizado que integra señales de entrada, procesamiento lógico y etapas de salida. Al desarrollar la lógica de bloques para gestionar el movimiento de la cortina, pusimos en práctica la teoría de temporización y secuenciamiento industrial, además de reforzar el uso de interfaces de potencia mediante relevadores para aislar físicamente el circuito de control del de fuerza. Esta implementación técnica fue fundamental para comprender cómo proteger el controlador ante cargas inductivas y asegurar un flujo de operación robusto, cumpliendo con los estándares de seguridad y eficiencia analizados en el curso.

## Autoevaluación
- [ ] Muy perdido
- [ ] Con dudas
- [x] Entendiendo 💡
- [ ] Dominando

