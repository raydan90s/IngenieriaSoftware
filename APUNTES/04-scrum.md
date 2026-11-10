# Pasos 4 y 5: Scrum (clase + Lectura #1)
*Fuentes: Clase Semana 3b (`03bScrum.pdf`) + **Lectura #1**: *The Scrum Framework* (International Scrum Institute, ISI) y Rubin, *Essential Scrum*, caps. 2, 4 y 5 (resumen de Bookey).*
*Sirve sobre todo para el **control de lectura 1**. Según el usuario, Scrum "en teoría" no entra en el examen 1.*
*🔹 = viene del resumen de Rubin para completar diapositivas que eran solo imagen. ⚠️ = las fuentes dicen cosas distintas: aprende las dos versiones.*

---

## 🎯 La idea en una frase
> Scrum es un **método ágil** donde el trabajo se hace en **iteraciones cortas y de duración fija (sprints)**. Se parte de una **lista priorizada** de lo que hay que construir (product backlog) y al final de cada sprint se entrega algo **potencialmente entregable**.

### Scrum en 30 segundos (el mapa)
```
 PRODUCT BACKLOG ──► SPRINT PLANNING ──► SPRINT BACKLOG ──► SPRINT (1–4 semanas) ──► INCREMENTO
 (lista priorizada,   (¿qué hacemos y      (tareas del         ├─ Daily Scrum            (potencialmente
  la cuida el PO)      cómo?)               sprint)            │  (15 min, cada día)      entregable)
       ▲                                                       │                              │
       │                                                       ▼                              ▼
       └──── GROOMING (refinamiento) ◄──── SPRINT RETROSPECTIVE ◄──── SPRINT REVIEW ◄────────┘
                                          (mejorar el PROCESO)     (revisar el PRODUCTO)
```

**Lo esencial:** **3 roles + 5 eventos + 3 artefactos**, más valores y principios.

---

## 1. ¿Qué es Scrum?
- **Clase:** un **método ágil** donde el trabajo se hace en **iteraciones cortas con tiempo fijo (timeboxed)**, de **una semana a un mes calendario**. Empiezas creando un **product backlog**: una **lista priorizada** de funcionalidades.
- **ISI:** *"un proceso **iterativo** de ingeniería de software para desarrollar y entregar software"*. Es **ligero (lightweight)**: busca aumentar la productividad y reducir el desperdicio.
- ⭐ **No es un proceso estandarizado** de pasos secuenciales que garantice éxito. Es un **framework** basado en **valores, principios y prácticas**, sobre el cual cada organización agrega lo suyo. *"El resultado será una versión de Scrum que es **únicamente tuya**"*.
- **Origen (ISI):** el término lo usaron **Hirotaka Takeuchi e Ikujiro Nonaka** en la **Harvard Business Review, enero de 1986**, en el artículo *"The New New Product Development Game"*. No viene de los años 2000, como cree mucha gente.
- **"Agile Scrum" y "Scrum" son lo mismo**: se dice "ágil" porque Scrum incorporó el **Manifiesto Ágil**.
- **Ideal para (ISI):** proyectos independientes de **un solo equipo**, sean nuevos (*greenfield*) o sobre sistemas existentes (*brownfield*). Con "Scaled Scrum" también sirve para varios equipos.

### Manifiesto Ágil (4 valores, ISI)
| Valoramos más… | …que |
|---|---|
| **Individuos e interacciones** | procesos y herramientas |
| **Software funcionando** | documentación extensiva |
| **Colaboración con el cliente** | negociación de contratos |
| **Responder al cambio** | seguir un plan |
*Lo de la derecha tiene valor, pero se prioriza lo de la izquierda.*

### Dos ideas centrales (ISI)
- **Autoorganización:** el equipo decide **por consenso** qué tareas hacer. **No necesita jefe ni líder**. Se apoya en el sprint backlog, el burndown y el daily scrum.
- **Inspeccionar y adaptar** (viene del **Toyota Improvement Kata** y del *lean*), en 4 pasos:
  1. **Inspeccionar** → equivale a la sprint review y la retrospectiva.
  2. **Adaptar** → equivale a la sprint planning y el refinamiento.
  3. **Aprender** → equivale al daily scrum.
  4. **Reiniciar** → equivale al cierre de un sprint y el inicio del siguiente.

---

## 2. Roles ⭐ (3)
⚠️ **Los nombres cambian según la fuente:**
- **Clase y Rubin:** Product Owner, **ScrumMaster**, **Development Team**.
- **ISI:** Product Owner, **Scrum Team (Members)**, Scrum Master.

### 👑 Product Owner (PO): decide QUÉ se construye
- **Clase:** el punto central **empoderado** del liderazgo del producto. Es la **única autoridad** que decide **qué** funcionalidades se construyen y **en qué orden**. Mantiene y comunica una **visión clara**. Es responsable del **éxito global** de la solución.
- **ISI:**
  - **Representa al cliente** y a los stakeholders, y **maximiza el valor** del producto.
  - Es el **único dueño del product backlog**: crea las historias, las prioriza y se asegura de que se entiendan.
  - Gestiona las **releases** y el **ROI**, y muchas veces el **presupuesto**.
  - **Gestiona a los stakeholders**: ellos **no** llevan sus pedidos directo al equipo; pasan por el PO.
  - En la sprint review **acepta o rechaza** lo entregado.

### 🧭 ScrumMaster (SM): cuida el PROCESO
- **Clase:**
  - Ayuda a todos a **entender y adoptar** los valores, principios y prácticas de Scrum.
  - Es un **coach** que lidera el proceso.
  - **Protege al equipo de interferencias externas** y **remueve impedimentos**.
  - ⭐ **No tiene autoridad para controlar al equipo**: **no es un project manager**.
- **ISI:**
  - Es un **líder servidor** (*servant leader*) y un **agente de cambio**.
  - **Modera los 5 eventos**.
  - Protege al equipo de la **falsa urgencia**: las historias nuevas esperan en el product backlog hasta el siguiente sprint planning.
  - **No debe tener autoridad jerárquica** sobre el equipo, porque eso rompería la confianza.
  - Al inicio es un trabajo a tiempo completo; cuando el equipo madura, puede aportar al trabajo.

### 👷 Development Team: CONSTRUYE
- **Clase:**
  - Un grupo **diverso y multifuncional** (*cross-functional*) que **diseña, construye y prueba**. Ya no hay títulos de arquitecto, tester, etc.
  - **Se autoorganiza** para cumplir el objetivo del PO.
  - **Tamaño: de 5 a 9 personas**. Si un proyecto necesita 35 personas, se arman **4 o más equipos** de 9 o menos.
- **ISI:**
  - **Tamaño ideal: 7 ± 2.** Con más de 9 sube mucho el costo de comunicación; con 13, conviene dividir el equipo.
  - Todos se llaman **"Scrum Team Member"**.
  - **Responsable como un todo**: el éxito o el fracaso nunca se atribuye a una sola persona.
  - **Dedicación al 100%** y **co-ubicado**, idealmente en la misma sala.
  - Decide **qué** se compromete a entregar, **cómo** se divide en tareas y **quién** hace cada una.
  - **Modelo de Tuckman** (formación del equipo): **Forming → Storming → Norming → Performing**. Un equipo tarda de **3 a 5 sprints** en madurar.

### ¿Y el project manager? (ISI)
**Scrum no tiene project manager.** Sus funciones se **reparten entre el PO** (funcionalidad, releases, presupuesto) **y el SM** (seguimiento de tareas, impedimentos).
Regla: **un PO trabaja con un equipo**, y **cada equipo tiene su propio SM**. Los roles **no se combinan**.

---

## 3. Eventos ⭐ (5, según ISI)
**Grooming (refinamiento) · Sprint Planning · Daily Scrum · Sprint Review · Sprint Retrospective.**
*(La clase los llama actividades: el sprint empieza con la **planning**, sigue con la **ejecución** y termina con la **review** y la **retrospectiva**.)*

### 🏃 El sprint (el contenedor)
- **Iteración** de trabajo que produce un **incremento potencialmente entregable**. *"Piénsalo como un **mini-proyecto**"* (ISI).
- ⚠️ **Duración:** la **clase** dice de **una semana a un mes calendario**. El **ISI** dice **máximo 4 semanas**, normalmente **2 a 4**, y **1 semana** para *sprints de exploración* (investigar una tecnología o hacer una prueba de concepto).
- **Timeboxed:** fecha de **inicio y fin fijas**. Normalmente todos duran **lo mismo**, y **un sprint empieza apenas termina el anterior**.
- Debe crear algo de **valor tangible** para el cliente.
- No es una carrera: el equipo debe terminar **descansado**, no sin aire.

**🔹 Rubin (cap. 4, Sprints):**
- **Timeboxed:** limita el trabajo en curso (WIP), obliga a priorizar, muestra el avance, **evita el perfeccionismo**, motiva a cerrar y mejora la predictibilidad.
- **Corta duración:** planificar es más fácil, el feedback llega **rápido**, los errores salen más baratos y el equipo se motiva más.
- **Duración constante:** crea un ritmo y simplifica la planificación.
- **Sprint goal:** el valor de negocio a lograr. **No se cambia el objetivo** a mitad del sprint, salvo que se justifique económicamente. **Aclarar** el objetivo está bien; **cambiarlo** no, porque genera desperdicio y baja la moral.
- **Terminación anormal:** si el objetivo **deja de tener sentido**, el sprint se puede **cancelar**. Luego viene una retrospectiva y se planifica el siguiente.
- **Definición de "Hecho" (DoD):** un checklist que define cuándo el incremento está terminado. **Evoluciona** con el tiempo.
- ⭐ **DoD vs. criterios de aceptación:** la **DoD aplica a todo el incremento**. Los **criterios de aceptación** son **específicos de cada historia**.

### 1️⃣ Sprint Planning: ¿QUÉ hacemos y CÓMO?
- **Clase:** el backlog tiene más trabajo del que cabe en un sprint, así que **el PO, el equipo y el SM** eligen el **subconjunto más importante** que el equipo cree que puede terminar.
- **ISI:** tiene **2 partes**:
  - **WHAT-Meeting:** el PO presenta el **sprint goal** y los candidatos, y **el equipo decide cuántos puede comprometer**.
  - **HOW-Meeting:** el equipo divide las historias en **tareas** (análisis, diseño, desarrollo, pruebas, documentación) y las estima en **horas-persona**.
- La **presencia del PO es obligatoria**. Los stakeholders pueden mirar, pero **no intervienen**.
- El equipo calcula su **capacidad**: descuenta vacaciones, feriados, el tiempo de los eventos y un margen para imprevistos.

### 2️⃣ Daily Scrum (Daily Stand-up): sincronizar
- **Cada día**, a la **misma hora** y en el **mismo lugar**, con **máximo 15 minutos**.
- ⭐ **3 preguntas** que responde cada miembro:
  1. ¿Qué hice desde el último daily?
  2. ¿Qué voy a hacer hasta el próximo?
  3. ¿Qué **impedimentos** tengo?
- **No es para resolver problemas ni tomar decisiones largas**. Eso se hace **después**, solo con los involucrados (ISI).
- Lo **modera el SM**, que también lleva un **registro de impedimentos**. Los stakeholders pueden asistir solo como oyentes.
- ⚠️ **Asistentes:** la **clase** dice "los miembros del development team". El **ISI** dice que van el equipo, el SM **y el PO**.

### 3️⃣ Sprint Review: inspeccionar el PRODUCTO
- Ocurre al **final del sprint** y dura de **1 a 2 horas** (ISI).
- **Objetivo:** **inspeccionar y adaptar el producto**. Se **demuestra** el incremento, **sin PowerPoint** (ISI).
- **Participantes (clase):** el equipo Scrum, los **stakeholders, patrocinadores, clientes** y miembros interesados de otros equipos. Lo importante es la **conversación**.
- El **PO verifica** si se entregó lo comprometido.

### 4️⃣ Sprint Retrospective: inspeccionar el PROCESO
- Ocurre **después de la review** y **antes de la siguiente planning**, y **cierra el sprint**.
- ⭐ **Review = producto. Retrospectiva = proceso.**
- El equipo, el SM y el PO discuten **qué funciona y qué no** de Scrum y de las prácticas técnicas.
- **ISI:** es un *mini post-mortem*. Se hace **sin excepción al final de cada sprint**. Ejemplos de mejoras: adoptar XP o TDD, definir nuevas normas del equipo, que el PO esté más disponible.

### 5️⃣ Grooming (Backlog Refinement)
- **Clase:** la actividad de **crear, refinar, estimar y priorizar** los elementos del product backlog.
- **ISI:** se hace a demanda o programado, **hasta 2 veces por semana, 30 minutos cada una**. En ella se **agregan** historias nuevas, se **eliminan** las que ya no hacen falta, se **reestiman**, se **repriorizan** y se **dividen** las historias gigantes.

---

## 4. Artefactos ⭐ (3)

### 📚 Product Backlog
- **Lista priorizada** de funcionalidades y capacidades necesarias para el producto (clase).
- **Dueño:** el **PO**. Los demás contribuyen.
- **Producto nuevo:** contiene las funcionalidades que cumplen la visión del PO. **Producto en marcha:** además incluye **cambios, defectos, mejoras técnicas** y reducción de **deuda técnica**.
- **Atributos (ISI):**
  - Cada historia aporta **valor**.
  - Está **ordenado por prioridad**.
  - El **nivel de detalle depende de la posición**: lo de arriba es detallado y lo de abajo general, y se detalla **"just in time"**.
  - Todo está **estimado**.
  - Es un **documento vivo**.
  - **No contiene tareas** de bajo nivel.
- Responde **qué**, nunca **cómo**: el cómo lo decide el equipo en el sprint backlog.
- Para priorizar se considera el **valor**, el **costo**, los **riesgos** y las **dependencias**.

### 📝 Sprint Backlog
- Son las **historias comprometidas para el sprint más sus tareas** (clase).
- ⭐ **Ninguna tarea debe durar más de 16 horas** (clase).
- Es **vivo**: durante el sprint se pueden agregar **tareas**, pero **no historias nuevas** (ISI).
- Se calcula el **esfuerzo restante** cada día.
- Puede llevarse en un tablero físico con post-its o en Excel o software.

### 📦 Incremento: lo "Hecho"
- El resultado del sprint es un **incremento de producto potencialmente entregable** (*potentially shippable product increment*).
- **Definition of Done (DoD, ISI):**
  - Es el **checklist** que define cuándo algo está **realmente terminado**: requisitos funcionales y no funcionales, diseño, código, pruebas unitarias, validación del usuario, documentación…
  - Existe a varios niveles: **proyecto, release, sprint, historia y tarea**.
  - **No se puede cerrar** una historia que no cumpla su DoD.
  - **No es estática**: se puede mejorar.

### 📉 Burndown charts (herramientas de seguimiento)
- **Clase:** el burndown muestra la **cantidad de requerimientos pendientes** del product backlog **al inicio de cada sprint**. El **sprint burndown** muestra el trabajo pendiente **dentro** del sprint.
- **ISI:**
  - El **Sprint Burndown** se actualiza **cada día** con el esfuerzo restante, y permite predecir si se cumplirá el sprint goal.
  - **Velocity:** los **story points completados por sprint**. ⭐ **Solo cuentan las historias que cumplen su DoD**: las a medias no cuentan.
  - Ejemplo: con una velocidad de 50 puntos por sprint y 300 puntos pendientes, se necesitan **6 sprints**.

---

## 5. Historias de usuario y estimación

### Plantilla (ISI)
> **Como [actor], [quiero | debo] [acción] para [logro].**
> *Ejemplo: "Como estudiante, quiero ver mis notas para saber si aprobé."*
- **Actor:** sé específico (administrador, cliente con sesión, visitante), no solo "usuario".
- **Debo** = obligatorio. **Quiero** = deseable.
- La historia tiene **nombre, narrativa y criterios de aceptación**. Dice **qué** necesita el usuario, no **cómo** hacerlo.

### 🔹 Rubin (cap. 5, Requerimientos e historias de usuario)
- **Tradicional:** los requerimientos son detallados, **no negociables**, se hacen al inicio y **cambiarlos es caro**. **Scrum:** son **flexibles**; se quitan los de poco valor y se agregan los nuevos de alto valor.
- Las historias son **recordatorios** (*placeholders*) que **invitan a conversar**. La **comunicación verbal** aclara más que un documento detallado.
- **Refinamiento progresivo:** los requerimientos grandes se **dividen** en historias pequeñas **solo cuando ya van a hacerse**.
- ⭐ **INVEST**, los criterios de una buena historia:
  - **I**ndependiente: con pocas dependencias.
  - **N**egociable: se discute el qué y el porqué, no el cómo.
  - **V**aliosa: aporta valor al usuario.
  - **E**stimable: el equipo puede calcular su tamaño.
  - Pequeña (**S**mall): cabe en un sprint cuando le toca.
  - **T**esteable: tiene criterios de aceptación.
- Los **RNF** también pueden escribirse como historias, y existen las **historias de adquisición de conocimiento** (investigar o hacer un prototipo).
- **Para recolectar historias:** **talleres de escritura de historias** y **story mapping**, con los usuarios involucrados durante todo el proceso.

### Estimación (ISI)
- No se estima en horas ni en días, sino en **unidades abstractas** (**story points**): números del 1 al 10, **tallas de camiseta** (XS–XXXL) o **Fibonacci** (0, 1, 2, 3, 5, 8, 13, 21…).
- **¿Por qué Fibonacci?** Refleja la **incertidumbre** de las historias grandes: es fácil decidir entre 13 y 21, pero discutir si algo vale 19 o 20 es perder el tiempo.
- **Planning Poker:**
  1. El PO presenta la historia.
  2. Cada miembro elige una carta **en secreto**.
  3. Todos las revelan a la vez.
  4. Explican sus números **el más alto y el más bajo**.
  5. Se repite hasta llegar a un **consenso**.
- Una estimación **alta** puede significar que la historia **no se entendió** o que **hay que dividirla**.
- El **PO no debe presionar** al equipo con las estimaciones.

---

## 6. Valores ⭐
⚠️ **Las listas difieren según la fuente:**
| Clase (8) | ISI (5) |
|---|---|
| Honestidad, **Apertura**, **Coraje**, **Respeto**, **Foco**, Confianza, Empoderamiento, Colaboración | **Coraje, Foco, Compromiso, Respeto, Apertura** |

🧠 Las comunes son **Coraje, Foco, Respeto y Apertura**. La lista del ISI es la "oficial" de 5; agrégale **Compromiso**.
**Detalles del ISI:**
- **Coraje:** tomar decisiones difíciles.
- **Foco:** trabajar en lo correcto y en el orden correcto.
- **Compromiso:** *"piensa en **obsesión**"* por el objetivo.
- **Respeto:** a todos, sin importar edad, experiencia u opinión.
- **Apertura:** transparencia, y no tener miedo a equivocarse.

## 7. Principios (🔹 Rubin; las diapositivas eran imagen)
1. **Variabilidad e incertidumbre:** acepta la variabilidad útil, usa desarrollo **iterativo e incremental**, y aprovecha la inspección, la adaptación y la transparencia.
2. **Predicción y adaptación:** mantén las opciones abiertas, acepta que no todo saldrá bien desde el inicio, y equilibra el trabajo previo con el trabajo *just in time*.
3. **Aprendizaje validado:** valida rápido los supuestos importantes y organiza el flujo para obtener **feedback rápido**.
4. **Trabajo en curso (WIP):** tamaños de lote razonables, fíjate en el **trabajo detenido**, no en las personas desocupadas, y considera el **costo del retraso**.
5. **Progreso:** se mide por **entregables validados** que funcionan, no por cumplir un plan.
6. **Desempeño:** *"ve rápido, pero nunca con prisa"*, **calidad integrada** desde el inicio y **ceremonia mínima suficiente**.

---

## 8. Beneficios y limitaciones (clase) ⭐
| ✅ Beneficios | ❌ Limitaciones |
|---|---|
| Se entrega un producto **potencialmente entregable** al final de cada sprint | Es **más difícil en proyectos grandes** |
| El producto se divide en partes **comprensibles y manejables** | Requiere un equipo con **habilidades transversales** |
| Los **requerimientos inestables** se identifican **pronto** | Supone un **cliente muy activo**, involucrado todo el tiempo |
| **Todo el equipo conoce el estado** del proyecto | **No genera cierta documentación** que piden los estándares internacionales |
| Se construye **confianza** entre cliente y desarrolladores | |

### Extras del ISI (por si preguntan)
- **Triángulo de gestión de proyectos:** antes había que sacrificar **tiempo, presupuesto o calidad**. Con Scrum, el triángulo es **presupuesto, tiempo y funcionalidad**, porque **la calidad ya no es negociable**.
- **3 frustraciones antes de Scrum:**
  1. Planificar todo el proyecto **antes de entenderlo** (cascada). En proyectos grandes cerca del **60% de los requerimientos cambia**, y la cascada fue factor de fracaso en más del **80%** de los proyectos fallidos estudiados.
  2. Organización **matricial** en **silos**: equipos prestados, sin compromiso.
  3. **Decisiones autocráticas** por encima de las del equipo.
- **Scrum escalado:**
  - **Scrum of Scrums:** un daily entre equipos; cada equipo manda un representante y se responden las mismas 3 preguntas, pero **por equipo**.
  - **Chief Product Owner** y un equipo de POs.
  - **Equipos de componentes vs. de funcionalidades (*feature teams*):** los de funcionalidades entregan historias completas y tienen visión de todo el sistema.
  - **Sprints sincronizados** (todos empiezan y terminan el mismo día; es lo preferido) **vs. asíncronos**.
  - Un **backlog global** y backlogs locales.

---

## ✅ Autotest
<details><summary>1. ¿Qué es Scrum y por qué se dice que no es un "proceso estandarizado"?</summary>
Es un método ágil con iteraciones cortas y de duración fija (sprints). No es una secuencia de pasos que garantice el éxito, sino un framework de valores, principios y prácticas que cada organización adapta.</details>

<details><summary>2. ¿Cuáles son los 3 roles y qué hace cada uno?</summary>
Product Owner: decide qué se construye y en qué orden, y es dueño del product backlog. ScrumMaster: coach del proceso, protege al equipo y remueve impedimentos, sin autoridad sobre el equipo. Development Team: multifuncional y autoorganizado, de 5 a 9 personas, diseña, construye y prueba.</details>

<details><summary>3. ¿Por qué el ScrumMaster no es un project manager?</summary>
Porque no tiene autoridad para controlar al equipo. Es un líder servidor o coach. Las funciones del project manager se reparten entre el PO y el SM.</details>

<details><summary>4. ¿Cuáles son los 5 eventos?</summary>
Grooming (refinamiento del backlog), Sprint Planning, Daily Scrum, Sprint Review y Sprint Retrospective.</details>

<details><summary>5. Sprint review vs. retrospectiva.</summary>
La review inspecciona y adapta el producto (se demuestra el incremento a los stakeholders). La retrospectiva inspecciona y adapta el proceso (qué funciona y qué no). La retrospectiva va después de la review y cierra el sprint.</details>

<details><summary>6. ¿Cuáles son las 3 preguntas del Daily Scrum y cuánto dura?</summary>
¿Qué hice desde el último daily? ¿Qué haré hasta el próximo? ¿Qué impedimentos tengo? Dura máximo 15 minutos, todos los días a la misma hora y en el mismo lugar.</details>

<details><summary>7. Product backlog vs. sprint backlog.</summary>
Product backlog: la lista priorizada de todo lo que necesita el producto; su dueño es el PO y responde qué. Sprint backlog: las historias comprometidas para el sprint más sus tareas (cada tarea de 16 horas o menos); lo maneja el equipo y responde cómo.</details>

<details><summary>8. ¿Qué es la Definition of Done y en qué se diferencia de los criterios de aceptación?</summary>
La DoD es el checklist que define cuándo algo está realmente terminado (código, pruebas, documentación…) y aplica a todo el incremento. Los criterios de aceptación son específicos de cada historia.</details>

<details><summary>9. ¿Qué es la velocity y qué historias cuentan?</summary>
Los story points completados por sprint. Solo cuentan las historias que cumplen su DoD; las a medias no.</details>

<details><summary>10. ¿Qué significa INVEST?</summary>
Independiente, Negociable, Valiosa, Estimable, Pequeña (Small), Testeable.</details>

<details><summary>11. ¿Cuánto dura un sprint y qué significa timeboxed?</summary>
Según la clase, de 1 semana a 1 mes calendario; según el ISI, normalmente de 2 a 4 semanas y máximo 4. Timeboxed significa que tiene fechas de inicio y fin fijas, y que no se extiende.</details>

<details><summary>12. Menciona 3 beneficios y 3 limitaciones de Scrum.</summary>
Beneficios: un incremento entregable en cada sprint, los requerimientos inestables se detectan pronto, todos conocen el estado del proyecto, se genera confianza con el cliente. Limitaciones: es difícil en proyectos grandes, requiere habilidades transversales, exige un cliente muy activo y no genera cierta documentación que piden los estándares.</details>

<details><summary>13. ¿Quién acuñó el término Scrum y cuándo?</summary>
Takeuchi y Nonaka, en la Harvard Business Review de 1986, con el artículo "The New New Product Development Game".</details>

<details><summary>14. ¿Qué pasa si el PO quiere meter una historia nueva a mitad del sprint?</summary>
No se puede: el equipo ya se comprometió en el sprint planning. El SM la guarda en el product backlog para el siguiente sprint. Si el objetivo del sprint deja de tener sentido, el sprint se puede cancelar.</details>
