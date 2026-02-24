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

Con la base técnica definida en clase, el equipo se dividió la elaboración del Entregable H1, asignando la redacción de requisitos a Marisol y Ximena, la tabla de I/O a Marisol y Melissa, y el diagrama de bloques a Melissa.

Finalmente, integramos el inventario de materiales proporcionado por la Escuela de Ingenierías del Tecnológico de Monterrey, vinculando cada componente con su función lógica y eléctrica. Este proceso de análisis y experimentación inicial nos permitió validar la viabilidad técnica del diseño y avanzar en la documentación formal de los requisitos funcionales y de seguridad del sistema.

## Decisiones de ingeniería
| Decisión | Alternativas | Justificación |
|--------|-------------|---------------|

## Problema técnico encontrado
Describe un problema concreto.

## Solución aplicada
Explica cómo se resolvió.

## Conexión con el curso
¿Qué concepto de MR2022 aplicaste esta semana?

## Autoevaluación
- ⬜ Muy perdido
- ⬜ Con dudas
- ⬜ Entendiendo
- ⬜ Dominando

