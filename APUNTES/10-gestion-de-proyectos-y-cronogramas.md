# Paso 10: Gestión de proyectos, stakeholders y cronogramas (redes AoA + camino crítico)
*Fuentes: **transcripción de la Sesión 11** (`Session 11.vtt`, clase del Dr. Mera) + diapositivas `06ProjectManagement.pdf` (Semana 6) y `07SchedulingandResourceAllocation.pdf` (Semana 7).*
*Sirve para la **2da "pequeña evaluación" (lección) del miércoles 11-nov-2026** y para el examen final.*
*🎤 = lo dijo el profe en clase (probable pregunta). 📄 = solo está en las diapositivas. 🔹 = lo agregué yo para completar. ⚠️ = cuidado, error típico.*

---

## 🎯 Qué entra en la lección (según el profe)
> 🎤 *"En la segunda parte... vamos a ver time-limited scheduling y resource-limited scheduling; hoy no alcanzamos, lo vemos el día **lunes**. Y con eso ya estamos listos para la segunda pequeña evaluación del **miércoles de la semana que viene**."*

### 🎤 Lo que dijo el profe, palabra por palabra (de la transcripción)
1. **Fecha:** *"Los enfoques de time limited scheduling y resource limited scheduling hoy no vamos a alcanzar, pero eso los vemos el día lunes… Y con eso ya estamos listos para la segunda… mínima evaluación del miércoles de la semana que viene… nos vemos con una pequeña evaluación."* Y al cerrar: *"Estudiemos esta parte, ¿no? Y estemos listos para el día miércoles."*
2. **Mapa de stakeholders:** *"¿Cuál es el tipo de ejercicio que tú deberías esperar para esto en el examen?… a usted se le dé un contexto de un párrafo… en el que se van a mencionar varios stakeholders… son textos de cuatro o 5 líneas… Lo que importa es que usted sí sepa dibujar un mapa de stakeholders y sí sepa identificar a los stakeholders, luego que los sepa ubicar exactamente como key stakeholder o non-key stakeholder."* ⚠️ Pero también dijo: *"en el examen, **ya sea en el final o antes**, vamos a tener un enunciado y usted va a tener que dibujar un mapa de stakeholder"*. O sea, **no garantizó que sea el miércoles**. Puede ser en el examen final.
3. **De dónde saldrá ese ejercicio:** *"Voy a coger un ejercicio que esté de forma abierta en la web… le modifico unas 2 o 3 cositas… y usted sabe que algo parecido va a encontrar en el examen."*
4. **Leyenda y unidades:** *"Las unidades de tiempo vienen dadas en minutos y eso es algo relevante que debemos acordarnos para el examen… En el examen… usted tiene que tener una esquina del dibujo para mostrar la leyenda, qué significa cada elemento del diagrama, a menos que el diagrama obedezca un estándar"* (como UML).
5. **Camino crítico con línea doble:** *"Usualmente en el examen, como no podemos cambiar de color, lo que hacemos es colocar una línea doble"* y *"las actividades marcadas en rojo o con línea doble de pluma en el examen son las actividades críticas"*.
6. **Formato típico del ejercicio de redes:** *"En el examen, una típica configuración es que le den un conjunto de actividades… le dan el identificador… letras mayúsculas… le dan también el staff (la cantidad de gente; eso lo vemos el lunes)… le dan la duración y la unidad de tiempo… y le dan los prerrequisitos."*
7. **Dummies y duración:** *"Cuando usted hace el examen, una de las preguntas que se hacen uno al otro: ¿cuántos dummies había?… Siempre deben ser iguales"* si se usó el mínimo, y *"la otra que nunca cambia… es la duración del proyecto"*.

> ⚠️ Lo que **no** dijo: no detalló el temario del miércoles. Solo dijo "estudiemos esta parte" (la clase de hoy) + lo del lunes. Los puntos 2 a 7 los dijo sobre "el examen" en general.

| Tema | Visto en | ¿Qué te pueden pedir? |
|---|---|---|
| Roles del equipo (PM, PO, arquitecto, devs, QA) | Sesión 11 | Definiciones, diferencias (dev vs QA) |
| **Stakeholders + mapa de stakeholders** | Sesión 11 | 🎤 Ejercicio anunciado (en el final **o antes**): un párrafo de 4–5 líneas → identificar stakeholders → **dibujar el mapa** (clave / no clave) |
| Scheduling, fases, milestones, baseline | Sesión 11 | Definiciones, ejemplos de milestone |
| Gantt (y sus limitaciones) | Sesión 11 | Ventajas/limitaciones vs. redes |
| **Red activity-on-arrow (AoA)** | Sesión 11 | 🎤 "Típica configuración" del examen: tabla de actividades → dibujar red con **mínimo de dummies** → forward/backward pass → **float** → **camino crítico** → **leyenda** |
| Time-limited / resource-limited scheduling | Lunes 9-nov (virtual) | Ver §8 (adelanto desde diapositivas) |

---

## 1. Proyecto y gestión de proyectos (📄 diapositivas 06, clase anterior)
- **Proceso** = actividades normales del día a día. **Proyecto** = algo **fuera** del día a día: *"una empresa **única**, con **inicio y fin**, llevada a cabo por personas para cumplir objetivos dentro de parámetros de **costo, cronograma y calidad**"* (Buchannan & Body).
- **¿Cómo surgen?** (1) una brecha entre "dónde estamos" y "dónde queremos llegar", (2) un problema que resolver, o (3) una oportunidad de cambio.
- **Gestión de proyectos** = planificar, monitorear y controlar personas, procesos y eventos desde el concepto hasta el despliegue. Se necesita porque el software profesional **siempre** tiene restricciones de **presupuesto y cronograma**.
- **Criterios de éxito:** entregar **a tiempo**, **dentro del presupuesto**, que **cumpla expectativas** del cliente y mantener un **equipo coherente** que funcione bien.
- **¿Por qué es difícil gestionar software?**
  1. **El producto es intangible** (no ves el avance como en un barco o puente; dependes de evidencia de otros).
  2. **Los proyectos grandes son "one-off"** (únicos; la experiencia previa y la tecnología quedan obsoletas).
  3. **Los procesos son variables y propios de cada organización.**

### Actividades del Project Manager (📄)
1. **Planificación** (planificar, estimar, hacer el cronograma, asignar personas, supervisar tiempo y presupuesto).
2. **Gestión de riesgos.**
3. **Gestión de personas.**
4. **Reportes** (a clientes y a gerentes; desde detalle técnico hasta resúmenes ejecutivos).
5. **Redacción de propuestas** (para ganar contratos: objetivos, costo y cronograma).

**4 factores para gestionar personas:** **Consistencia** (trato comparable), **Respeto** (a las diferencias de habilidades), **Inclusión** (escuchar a todos, incluso al menos experimentado), **Honestidad** (sobre lo que va bien y mal, y sobre tu propio nivel técnico).

---

## 2. Roles en el equipo de software (🎤 Sesión 11)
| Rol | Qué hace |
|---|---|
| **Project Manager** | Planifica, estima, hace el cronograma, gestiona riesgos y personas, reporta. |
| **Product Owner** | Representa al **negocio / usuarios**. Es el experto en los procesos de la organización cliente → decide **qué características van en este release**. |
| **Arquitecto de software** | Desarrollador **altamente especializado y siempre actualizado**. Ve "**el bosque**" (diseño de **alto nivel**). Conoce estándares, tendencias, normativas, frameworks, casos de estudio; **compara alternativas** y elige el **stack tecnológico**. Mucha responsabilidad. |
| **Desarrolladores** | Codifican. Hacen **pruebas unitarias**, pero solo para verificar que lo suyo funciona → ⚠️ **eso NO es software testing ni control de calidad**. |
| **QA / testers** | **Expertos en software testing y calidad.** Visión **holística** de todos los entregables (código, documentos de diseño, manuales, scripts). Hacen **pruebas dinámicas** (ejecutar) y **estáticas** (análisis estático de código, inspección de código, revisar requerimientos buscando inconsistencias/ambigüedades). Objetivo: **minimizar errores en producción**. |

---

## 3. Stakeholders (🎤 muy importante)
**Definición:** cualquier persona o grupo que **tiene interés** en el proyecto, que **es afectado** por él o que **puede influir** en su resultado. Incluye:
- a todos aquellos cuyo **trabajo cambia** por el proyecto,
- a todos los que pueden **obstruir, bloquear o retrasar** el proyecto,
- a los **altos directivos que otorgan los recursos**.

### 5 categorías (📄 + 🎤)
| Categoría | Quiénes son |
|---|---|
| **Senior managers** | Definen los temas de negocio; **mucha influencia**. Ej.: gerente comercial, financiero, de TI, de talento humano, de operaciones. Hacen **gestión/administración**. |
| **Project (technical) managers** | Perfil **técnico**: planifican, motivan, organizan y **controlan a los practitioners**. |
| **Practitioners** | Los profesionales técnicos que construyen (ingenieros de software, coord. de seguridad de la información…). |
| **Customers (clientes)** | **Especifican los requerimientos** ("qué debe hacer"). |
| **End users (usuarios finales)** | **Usan** el software ya en producción; dicen "¿me hace la vida más fácil, sí o no?". |

⚠️ **Customer ≠ End user**: el cliente pide/especifica; el usuario final lo usa.

### Mapa de stakeholders en capas (Robertson & Robertson, Fig. 3.7) 🎤
Se dibuja como una **cebolla** (círculos concéntricos) con el producto al centro:
```
┌──────────────────────── WIDER ENVIRONMENT (entorno amplio) ─────────────────────────┐
│ consultores EXTERNOS · beneficiario POLÍTICO (ministro, alcalde, concejales)          │
│ beneficiario FINANCIERO (el que invirtió y espera retorno) · clientes                 │
│ REGULADORES (MSP para hospital, Min. Educación, Superintendencia de Bancos)           │
│ ⚠ STAKEHOLDER NEGATIVO (el que quiere que salga mal: identifícalo a tiempo)           │
│   ┌──────────────── CONTAINING BUSINESS (el negocio) ────────────────────────┐        │
│   │ SPONSOR (motivó que el proyecto exista: alinéate con SU visión)          │        │
│   │ consultores INTERNOS (experiencia, su voz pesa)                          │        │
│   │   ┌──────────── THE WORK (capa operativa) ──────────────────┐            │        │
│   │   │ mantenimiento · soporte a usuarios · operadores         │            │        │
│   │   │      ┌──── THE PRODUCT ────┐                            │            │        │
│   │   │      │ gente técnica que   │                            │            │        │
│   │   │      │ desarrolla          │                            │            │        │
│   │   │      └─────────────────────┘                            │            │        │
│   │   └─────────────────────────────────────────────────────────┘            │        │
│   └──────────────────────────────────────────────────────────────────────────┘        │
└───────────────────────────────────────────────────────────────────────────────────────┘
```
🔹 Nombres de las capas en el libro: *The Product → The Work → The Containing Business → The Wider Environment*.

### Mapa de stakeholders sencillo (el que piden en el examen y en el proyecto) 🎤
- El **proyecto va SIEMPRE al centro**.
- Alrededor, los **stakeholders clave** (key). Alrededor de esos (o en otro color/zona), los **no clave** (non-key).
```
                 Junta directiva     Proveedores
                         \              /
   Equipo QA ─── [ Gerente de TI ]  [ Gerentes departamentales ] ─── Colaboradores
                          \           /
                         (  PROYECTO X  )
                          /           \
   Coord. de TI ── [ Gestores de cuentas ]      Equipo de TI
   Leyenda: [ ] = stakeholder CLAVE    sin caja = stakeholder NO clave
```

### 🎤 Cómo será la pregunta
- Te dan un **párrafo de 4–5 líneas** con un contexto donde se mencionan varios stakeholders.
- Debes: (1) **identificarlos todos**, (2) **dibujar el mapa**, (3) ubicar cada uno como **clave o no clave**.
- La clasificación clave/no clave es "**subjetiva hasta cierto punto**" (se te perdona algo), pero **sí o sí** debes saber dibujar el mapa e identificarlos.
- El profe tomará un **ejercicio abierto de la web** y le cambiará "unas 2 o 3 cositas" → practica con las lecturas: *5 Stakeholder Map Examples With Analysis* (projectmanager.com), Mural, NOAA *Stakeholder Analysis Exercise*, UNIR, Miro, Canva, Lucid.
- ¿Por qué importa? 🎤 *"Ahí defines tu **tablero de ajedrez**"*: decides la estrategia con cada stakeholder para **reunir apoyo** al proyecto.
- Lecturas: **cap. 3 de Robertson** (*Scoping the Business Problem*) y **Field & Keller, *Project Management*, caps. 3 y 4**.

---

## 4. Scheduling (elaborar el cronograma)
- **Scheduling = hacer el cronograma.** Es una de las **principales actividades** del director de proyecto (e incluso del gerente de TI).
- Sirve para **visualizar con antelación** todas las actividades, **detectar riesgos** y saber qué **recursos humanos** se necesitan y cuánto tardará cada uno.
- 🎤 **Tamaño de las tareas:** idealmente **≤ 8 horas**; máximo aceptable **16 horas (2 días)**. Más que eso = cronograma mal detallado.
- No es solo una lista: hay que **agrupar** actividades (pruebas, diseño, codificación módulo A, módulo B…).
- **Los proyectos con retraso son caros** para el **cliente** (pierde oportunidad de negocio, p. ej. no llegar primero al mercado — *"el que golpea primero golpea dos veces"*; o multas por no cumplir una regulación) y para el **contratista** (**multas** del contrato). 🎤 Ejemplo: local de ropa que debía abrir en octubre y lo entregan en la 2da quincena de diciembre → pierde la temporada.
- El cronograma se hace en el **día 0** y luego se **monitorea** (en tiempo y, más adelante, en costo) y se ajusta. 📄 Ojo: elaborarlo y monitorearlo **no basta para garantizar** terminar a tiempo.

### Fases, milestones y baseline
| Concepto | Definición | Ejemplos |
|---|---|---|
| **Fase** | Agrupa actividades (fase 1, 2, 3…). 📄 Ej.: diseño, compra, instalación, puesta en marcha. Muchas veces las fases se **traslapan**. | — |
| **Milestone (hito de verificación)** | **Evento de duración CERO**, pero **muy importante/significativo**. Se controla de forma **binaria**: está o no está. **No debe existir duda** de si ocurrió. | Firma de aceptación del documento de requerimientos / de diseño / de manuales / de pruebas · correo de confirmación de entrega en Aula Virtual · lanzar el buque al agua · prueba eléctrica de un edificio · estación de Metrovía terminada |
| **Baseline (línea base)** | **Estado** del proyecto (o de una parte) en un **instante** dado, normalmente al **final de una fase**. La siguiente fase se construye **sobre** el baseline anterior. | "Diseño terminado y aprobado" → sobre eso arranca la construcción · una prueba diagnóstica al inicio del curso |

⚠️ **¿Por qué el milestone controla mejor que una actividad?** Porque una actividad "al 70 %" puede ser 60 o 75 % (subjetivo); el milestone es **1 o 0**.
⚠️ **Todo milestone es un evento, pero no todo evento es un milestone.**

---

## 5. Diagrama de Gantt
- **Izquierda:** lista de actividades. **Derecha:** escala de tiempo horizontal con una **barra** por actividad.
- Puede mostrar: **dependencias** (flechitas), **milestones** (rombos ◇, duración 0: inicio y fin del proyecto), **% de avance** (sombreado más oscuro = hecho), **responsable**.
- 🎤 Ejemplo de clase: actividades A…L, proyecto de **15.5 semanas**; en la semana 7 deberías tener A–E terminadas y estar en F y G.
- ✅ **Ventaja:** **fácil de entender** (se hace hasta en Excel). Por eso es el más usado (*por sencillez, no porque sea el mejor*).
- ❌ **Limitaciones (📄 — memorízalas):**
  1. **No es fácil mostrar las dependencias** entre actividades (solo por inferencia; con muchas dependencias las flechas se vuelven ilegibles y se termina escribiendo "G depende de C, D").
  2. **No se aprecia el camino crítico.**
  3. 🎤 **Necesita una fecha de inicio real** para dibujar las barras.

### Camino crítico (idea)
Cadena de actividades desde el **hito de inicio** hasta el **hito de fin** que **no se pueden retrasar**: si una se demora, **se atrasa todo el proyecto**.
🎤 Analogía ESPOL: reprobar **Cálculo** o **Ingeniería de Software I** te atrasa un semestre (camino crítico); reprobar Física o Diseño de Software quizá no.

---

## 6. Técnicas de redes: Activity-on-Arrow (AoA)
- Variantes de técnicas de redes: **critical path scheduling, critical path analysis, PERT** (*Project Evaluation and Review Technique*). Herramientas: Lucidchart, EdrawMax. 🔹 Existe también *activity-on-node* (actividad en el nodo).
- **Idea:** representar gráficamente la **relación secuencial** entre actividades.
- **Ventajas sobre Gantt:**
  - ✅ **No necesitas la fecha real de inicio**: usas tiempos relativos (**t = 0**). Si cambia la fecha, la red no cambia.
  - ✅ La red **no cambia mucho** si cambian duraciones o se agrega una actividad.
  - ✅ Ves **gráficamente** dependencias, camino crítico y duración del proyecto.
- **Las 3 preguntas del planificador** para cada actividad:
  1. ¿Qué se debe hacer **antes** de iniciarla? (prerrequisitos; ej.: para diseño detallado → diseño arquitectónico terminado)
  2. ¿Qué se puede hacer **una vez terminada**? (ej.: codificación → pruebas unitarias → integración → sistema)
  3. ¿Qué actividades pueden hacerse **en paralelo**? (ahorra tiempo)

### Reglas de la red AoA (⭐ memorízalas)
1. **Actividades = flechas** (con la **duración debajo** de la flecha). **Eventos = nodos** (círculos numerados).
2. Un **evento** tiene **duración 0** y significa que **TODAS las actividades que llegan a él terminaron**. Recién ahí pueden empezar las que salen.
3. Una actividad se identifica por su **par (nodo inicio, nodo fin)** → ⚠️ **dos actividades NO pueden compartir a la vez el mismo nodo de inicio Y el mismo nodo de fin**. (Compartir solo uno de los dos sí está bien.)
4. Para resolver lo anterior se usan **actividades dummy**: **línea punteada**, **duración 0**, solo crean un nodo extra para identificación. **Usa el MÍNIMO número de dummies.**
5. **No puede haber lazos (ciclos).** Ej. prohibido: crear componente → probar → si falla, rediseñar y volver. Se modela como "make component" + "modify component as necessary".
6. **Un único nodo de inicio** (sin flechas entrantes) y **un único nodo de fin** (sin flechas salientes).
7. A un nodo pueden **llegar** o **salir** **cuantas flechas sean** (no hay límite). El límite es para los dummies (el mínimo).
8. 🎤 **SIEMPRE pon LEYENDA**: unidades de tiempo (min, días, semanas…), qué es el círculo, la flecha, la línea punteada, la línea doble. *"En el campo profesional todo gráfico especifica sus unidades."* Excepción: diagramas estándar (UML).

🎤 **Dos cosas que NUNCA cambian**, sin importar cómo dibujes tu red:
- el **número mínimo de dummies**, y
- la **duración del proyecto**.
(Puedes comparar con tus compañeros después del examen: si alguien tiene distinto número de dummies, alguien no usó el mínimo.)

### Leyenda del nodo (la que usamos en clase, "opción A")
```
        ┌─────┬─────┐
        │     │ EET │   EET = earliest event time (arriba-derecha)
        │  N  ├─────┤   N   = número del evento (izquierda)
        │     │ LET │   LET = latest event time (abajo-derecha)
        └─────┴─────┘
   ───────►  actividad (duración debajo)      - - - ►  dummy (duración 0)
   ════════► actividad CRÍTICA (en el examen: línea DOBLE, porque no hay colores)
   Unidades: ______ (¡escríbelas!)
```

---

## 7. Análisis de la red: forward pass, backward pass, float y camino crítico

### Definiciones
- **Earliest event time (EET):** lo **más pronto** que se puede llegar a un nodo (= cuando **todas** sus actividades predecesoras han terminado).
- **Latest event time (LET):** lo **más tarde** que se puede llegar a un nodo y **aún terminar el proyecto a tiempo**.

### Forward pass (paso hacia adelante) → EET
- Del **único nodo de inicio** (t = 0) al **único nodo de fin**.
- EET(nodo) = EET(nodo anterior) + duración de la actividad.
- ⭐ Si **llegan varias** actividades a un nodo: calcula **cada camino** y pon el **MAYOR** (la que termina última es el cuello de botella).

### Backward pass (paso hacia atrás) → LET
- Del nodo de fin hacia el inicio.
- En el nodo de fin: si te dan un **plazo** (p. ej. "máximo 15"), LET = **ese plazo**; si **no te dicen nada**, LET = **el EET del fin** (mínimo tiempo posible).
- LET(nodo) = LET(nodo siguiente) − duración.
- ⭐ Si **salen varias** actividades de un nodo: calcula cada una y pon el **MENOR**.
- Truco: si no hay plazo, el LET del nodo de inicio **debe dar 0** → sirve para verificar que no te equivocaste.

| | Forward pass | Backward pass |
|---|---|---|
| Calcula | EET (arriba) | LET (abajo) |
| Dirección | inicio → fin | fin → inicio |
| Operación | **+** duración | **−** duración |
| Varias flechas… | **entrantes** → el **MAYOR** | **salientes** → el **MENOR** |

### Tiempos de cada actividad (de nodo i a nodo j)
| Sigla | Nombre | Fórmula |
|---|---|---|
| **EST** | Earliest Start Time | EET del nodo **inicio** (i) |
| **EFT** | Earliest Finish Time | EET(i) **+ duración** |
| **LST** | Latest Start Time | LET del nodo **fin** (j) **− duración** |
| **LFT** | Latest Finish Time | LET del nodo **fin** (j) |

### Float (holgura / flotación)
- **Float** = exceso de tiempo disponible en una actividad sobre su duración estimada. Una actividad con float "**flota**": se puede **retrasar o alargar** y el proyecto igual termina a tiempo.
- ⭐ **Total float = LET(nodo fin) − EET(nodo inicio) − duración** = LFT − EST − duración.
- **Path** = cualquier secuencia de actividades del nodo de inicio al nodo de fin siguiendo las flechas.
- ⭐ **Camino crítico = el path con MENOS float.** (Si no hay plazo extra, su float es **0**; si te dan un plazo mayor, todas tienen float y el crítico es el de **menor** float.)

---

### ✍️ Ejemplo 1: el lápiz y el papel (unidades: **minutos**)
Actividades: **Find pencil** (1) y **Find paper** (2) arrancan juntas; **Make drawing** (10) depende de las dos.
Como pencil y paper empezarían y terminarían en los mismos nodos → se necesita **1 dummy**.

**Forward:** nodo 3 = max(0+1, 0+2) = **2**; fin = 2 + 10 = **12 min** (duración mínima).

**Backward sin plazo (LET fin = 12):** nodo 3 = 12 − 10 = 2 → inicio = min(2−1, 2−2) = **0** ✔.
- Float pencil = 2 − 0 − 1 = **1** (puede demorarse 1 min). Paper = 2−0−2 = 0. Drawing = 12−2−10 = 0.
- **Camino crítico: Find paper → Make drawing.**

**Backward con plazo "máximo 15 min" (LET fin = 15):** nodo 3 = 15 − 10 = **5**; por el lado del lápiz 5 − 1 = 4, por el del papel 5 − 2 = 3 → inicio = **min(4, 3) = 3**.
- Float pencil = 5 − 0 − 1 = **4 min** (📄 este es el ejemplo de la diapositiva). Paper = 5−0−2 = 3. Drawing = 15−2−10 = 3.
- El camino crítico sigue siendo **paper → drawing** (el de **menor** float = 3).

### ✍️ Ejemplo 2: red de 3 actividades + 1
Nodo 1 → 2 (40), 2 → 3 (20), 1 → 3 (50), 3 → 4 (10).
- Forward: nodo 2 = 40; nodo 3 = max(40+20, 0+50) = **60**; fin = **70**.
- Backward: 70 → nodo 3 = 60 → nodo 2 = 40 → inicio = min(40−40, 60−50) = **0**.
- Floats: 40 → 0; 20 → 60−40−20 = 0; 10 → 70−60−10 = 0; **50 → 60−0−50 = 10**.
- **Camino crítico: 40 → 20 → 10.** La actividad de 50 flota 10 unidades.

### ✍️ Ejemplo 3: el típico del examen (🎤 "una típica configuración")
Te dan una tabla con **identificador (letra mayúscula)**, **staff** (personas; se usa en resource scheduling), **duración + unidad** y **prerrequisitos**:

| Actividad | Duración (sem) | Depende de |
|---|---|---|
| A | 12 | — |
| B | 8 | — |
| C | 5 | — |
| D | 10 | A, B |
| E | 10 | C, D |
| F | 5 | A, B |

*(Duraciones reconstruidas de los cálculos que el profe hizo en voz alta.)*

**Red con el mínimo de dummies (1):**
```
              A (12)               D (10)               E (10)
   ( 1 ) ════════════► ( 2 ) ════════════► ( 3 ) ════════════► ( 4 FIN )
     │ \                 ▲  \                 ▲                   ▲
     │  \ B (8)          ┊   \                │                   │
     │   ►( 5 )┄┄┄┄┄┄┄┄┄┄┘    └────────────── F (5) ──────────────┘
     │        dummy (0)                       │
     └─────────────────── C (5) ──────────────┘
   Leyenda: ═══ crítica · ─── normal · ┄┄┄ dummy · unidades: semanas
```
Flechas: A 1→2 · B 1→5 · dummy 5→2 · D 2→3 · F 2→4 · C 1→3 · E 3→4.
(A y B deben llegar al mismo nodo, del que salen D y F; como A y B también empiezan en el mismo nodo, una de ellas necesita **un dummy**. C va directo del inicio al nodo 3, donde también llega D, y de ahí sale E.)

**Forward:** nodo tras A/B = max(0+12, 0+8) = **12**; nodo antes de E = max(12+10, 0+5) = **22**; fin = max(22+10, 12+5) = **32 semanas**.
**Backward (sin plazo, LET fin = 32):** nodo antes de E = 32−10 = **22**; nodo tras A/B = min(22−10, 32−5) = min(12, 27) = **12**; inicio = min(12−12, 12−8, 22−5) = min(0, 4, 17) = **0** ✔.

| Act. | Dur | EST | EFT | LST | LFT | Float |
|---|---|---|---|---|---|---|
| A | 12 | 0 | 12 | 0 | 12 | **0** ⭐ |
| B | 8 | 0 | 8 | 4 | 12 | 4 |
| C | 5 | 0 | 5 | 17 | 22 | 17 |
| D | 10 | 12 | 22 | 12 | 22 | **0** ⭐ |
| E | 10 | 22 | 32 | 22 | 32 | **0** ⭐ |
| F | 5 | 12 | 17 | 27 | 32 | 15 |

**Camino crítico: A → D → E (32 semanas). Mínimo de dummies: 1.** (Si el dummy cuelga de A, también es parte del camino crítico.)

---

## 8. Recursos y scheduling (📄 se ve el **lunes 9-nov**; adelanto desde las diapositivas)
- Los recursos son **finitos** (personas, instalaciones, flujo de caja) → a veces conviene programar las actividades no "lo antes posible", sino cuando se **usen mejor los recursos**.

| | **Time-limited scheduling** | **Resource-limited scheduling** |
|---|---|---|
| Fijo | **La fecha de entrega** | **Los recursos** |
| Recursos | Se asumen **ilimitados** (contratar, horas extra, rentar) | **No** hay más personal, ni horas extra, ni servicios |
| Consecuencia | Se cumple la fecha | Puede **alargarse** la fecha |
| Técnica | **Resource smoothing** (nivelar la carga) | **Reglas elementales** (serial o paralelo) |

Si tienes **ambas** limitaciones: aplica un enfoque y luego el otro buscando algo compatible; si no se puede, **negociar** con el cliente.

### Time-limited: pasos
1. Dibujar la red. 2. Tabla con recurso, duración, **EST, float, LFT** por actividad. 3. Ordenar por **float creciente** (empate → por LFT). 4. Graficar el **resource loading chart inicial** con cada actividad en su **EST** (las más críticas abajo). 5. **Mover actividades dentro de su float** para nivelar (sin cambiar duraciones ni romper dependencias). 6. Usar criterio: replantear dependencias, horas extra en el pico. Objetivo: **reducir el recurso pico**.

### Resource-limited: reglas elementales ⭐
- **Parallel scheduling:** las actividades elegibles se consideran en paralelo. **Serial scheduling:** en un orden predefinido (p. ej., float creciente).
- **Regla 1:** entre las elegibles, elige la de **menor LST**. Empate → la de **menor duración**. Si sigue el empate → p. ej. la que **más recursos** requiere.
- **Regla 2:** una actividad iniciada **no se interrumpe** hasta terminar.
- **Regla 3:** **nunca** dejar un recurso **ocioso** si hay una actividad elegible que puede empezar.
- **Regla 4:** **no** se puede iniciar una actividad con **recursos parciales**.

**Ejemplo de la diapositiva (Ejemplo 5, 2 personas disponibles):** A 10 sem (1 p), B 5 (2 p), C 10 (2 p, dep. A y B), D 10 (1 p, dep. C), E 5 (1 p, dep. C). LST: A 0, B 5, C 10, D 20, E 25. Sin límite de recursos duraría **30**.
| t | Libres | Elegibles (por LST) | Decisión |
|---|---|---|---|
| 0 | 2 | A (1p, LST 0), B (2p, LST 5) | A ✔ (regla 1); B ✘ solo queda 1 persona (**regla 4**) |
| 10 | 2 | B | B ✔ |
| 15 | 2 | C | C ✔ |
| 25 | 2 | D (LST 20), E (LST 25) | D ✔ y E ✔ (1 p c/u) |
→ termina en **35 semanas** (5 más que sin restricción).

---

## 🧠 Autotest (respuestas abajo, tápalas)
1. ¿Qué diferencia a un desarrollador que hace pruebas unitarias de un QA?
2. Diferencia entre *customer* y *end user*.
3. Nombra 4 stakeholders de la capa *wider environment* y 2 del *containing business*.
4. ¿Qué va al centro de un mapa de stakeholders sencillo?
5. ¿Cuánto dura un milestone? ¿Por qué controla mejor que una actividad?
6. ¿Qué es un baseline? Da un ejemplo.
7. Dos limitaciones del Gantt.
8. ¿Por qué una red AoA no necesita fecha real de inicio?
9. ¿Cuándo se necesita un dummy? ¿Cuánto dura y cómo se dibuja?
10. En el forward pass, si llegan 2 flechas a un nodo, ¿qué valor pones? ¿Y en el backward pass con 2 salientes?
11. Fórmula del total float.
12. ¿Qué es el camino crítico?
13. ¿Qué dos valores no cambian aunque dos personas dibujen la red distinto?
14. ¿Qué no puede olvidarse en el diagrama del examen?
15. Regla 4 del resource-limited scheduling.

<details><summary>Respuestas</summary>

1. El dev prueba solo para ver que su código funciona; el QA es experto en testing y calidad con visión holística (pruebas dinámicas y estáticas sobre código, documentos, manuales…).
2. El customer especifica los requerimientos; el end user usa el sistema en producción.
3. Wider: consultores externos, beneficiario político, beneficiario financiero, reguladores, clientes, stakeholder negativo. Containing business: sponsor, consultores internos.
4. El proyecto.
5. Cero. Porque es binario (está o no está); el % de avance de una actividad es subjetivo.
6. El estado del proyecto en un instante, normalmente al final de una fase; ej.: diseño terminado y aprobado.
7. No muestra fácilmente dependencias; no se ve el camino crítico (y necesita fecha real de inicio).
8. Porque trabaja con tiempos relativos (t = 0).
9. Cuando dos actividades compartirían a la vez el nodo de inicio y el de fin. Dura 0, línea punteada.
10. Forward: el mayor. Backward: el menor.
11. LET(nodo fin) − EET(nodo inicio) − duración.
12. El path (del inicio al fin) con menos float; si una de sus actividades se demora, se atrasa todo el proyecto.
13. El número mínimo de dummies y la duración del proyecto.
14. La leyenda: unidades de tiempo y significado de círculos, flechas, punteadas y línea doble (camino crítico).
15. No se puede iniciar una actividad con recursos parciales.
</details>

---

## ✅ Checklist para el miércoles
- [ ] Practicar **2–3 mapas de stakeholders** con los enlaces de la diapositiva (projectmanager.com "5 stakeholder map examples", NOAA).
- [ ] Rehacer los **Ejemplos 1–3** a mano: red → mínimo de dummies → forward → backward → float → camino crítico → **leyenda**.
- [ ] Ver la clase del **lunes 9-nov** (time/resource-limited) y completar §8 con lo que diga el profe.
- [ ] Leer Field & Keller caps. 3 y 4, y Robertson cap. 3 (si los consigues).
