# Paso 1: Ingeniería de Software y Procesos de Software
*Fuente: Clase Semana 1 (Lecture 1b) + transcripción sesión 2 (Dr. Mera)*

---

## 🎯 La idea en una frase
> La ingeniería de software existe porque construir software **profesional** (para otros, en equipo, que vive años) es muy distinto a programar por tu cuenta, y necesita un **proceso sistemático** que controle costo, tiempo y calidad.

---

## 1. Programación individual vs. sistemas grandes (profesionales)

| Programación individual | Desarrollo profesional |
|---|---|
| Lo hago para **mí** (macro de Excel, script de un experimento, hobby) | Lo hago para **otra persona** (un cliente o un tercero) |
| Lo hago **solo** | Se hace en **equipo** (hay especialidades: requerimientos, front, back, seguridad, pruebas…) |
| Lo uso 1–2 veces; si falla, yo lo arreglo | Vive **años** en operación → hay que **mantenerlo y cambiarlo** |
| No necesita especificación, diseño ni gestión de evolución | **Sí** los necesita → ahí entra la ingeniería de software |

💡 **Las 3 diferencias clave:** (1) es para otros, (2) lo hace un equipo, (3) se mantiene y cambia durante toda su vida.

---

## 2. Origen: la "crisis del software"
- **1968, Conferencia de la OTAN (NATO) en Garmisch, Alemania.**
- **Crisis del software:** el problema de construir sistemas **grandes y confiables** de forma **controlada y costo-efectiva** (que el beneficio supere al costo).
- ¿Por qué pasó? Los sistemas se volvieron muy complejos. Quienes hacían el software eran los mismos del **hardware**, que sabían de electrónica pero **casi nada de procesos, métodos y herramientas** de software.
- Consecuencia: se reconoce que la IS es **más que teoría de computación y eficiencia de código** → nace la investigación en IS.

### ¿Por qué la IS es una disciplina **empírica** (y no igual a Ciencias de la Computación)?
1. El software es **inmaterial**: no obedece leyes físicas.
2. El software lo escriben **personas para personas**.

### Línea del tiempo (corta)
| Década | Palabra clave |
|---|---|
| 1970s | **Programación estructurada** (agrupar código en procedimientos y librerías para que sea mantenible) |
| 1980s | **Ramificación**: lenguajes y métodos por un lado; el resto se enfoca en la **gestión** de proyectos grandes |
| 1990s | **Orientación a objetos** (OOA/OOD; Smalltalk-80 como precursor) |
| 2000s | Buzzwords: ubicuo/pervasivo, auto-organizado/autonómico → hoy se ven como **móvil, cloud, IoT** |

---

## 3. ¿Qué es software?
### Doble rol
- Para el **ingeniero**: es un **producto** (programas, datos, documentación).
- Para el **usuario**: es un **vehículo/herramienta** para obtener algo (una orden de compra, una venta, el inventario).
- Lo que finalmente entrega es **información**.

> 📌 **Dato → Información → Conocimiento → Sabiduría** (lo preguntó en clase)
> - Dato: lo bruto.
> - Información: datos con sentido, útiles para decidir.
> - Conocimiento: la información ya comprendida por una persona.
> - Sabiduría (*wisdom*): decidir con base en ese conocimiento interiorizado.

### Definición (Pressman): software = 3 cosas
1. **Instrucciones** (programas) que al ejecutarse dan funciones, características y desempeño.
2. **Estructuras de datos** que permiten manipular la información.
3. **Información descriptiva** (documentación) sobre la operación y uso.

👉 **Código + datos + documentación.** Mucha gente olvida la documentación, y el profe insistió en que también es software.

### Un buen software
Entrega la **funcionalidad y desempeño** requeridos y es **mantenible, confiable (dependable) y usable**.
- Lo que hace = **requerimientos funcionales**.
- Cómo lo hace (rápido, seguro, fácil de usar, mantenible) = **requerimientos no funcionales**.
- 🥾 *Ejemplo del zapato:* dos zapatos cumplen la misma función (cubrir el pie, jugar fútbol), pero uno es más cómodo. La comodidad es un atributo **no funcional**.

### Categorías dominantes
- **WebApps** (Web semántica / Web 3.0, APIs, enlaces).
- **Apps móviles** (aprovechan la interacción de iOS/Android).

---

## 4. ¿Qué es Ingeniería de Software? ⭐ (pregunta segura de examen)
**Ingeniería:** usar el entendimiento científico para **inventar, diseñar y construir** cosas que resuelvan problemas.

### Definiciones que debes saber
- **SWEBOK:** *"La aplicación de un enfoque **sistemático, disciplinado y cuantificable** al **desarrollo, operación y mantenimiento** del software; es decir, la aplicación de la ingeniería al software."*
- **Sommerville:** *"Disciplina de ingeniería que se ocupa de **todos los aspectos** de la producción de software, desde la **especificación** inicial hasta el **mantenimiento** cuando ya está en uso."*
- (Otra de las slides): enfoque sistemático que considera **costo, cronograma y confiabilidad**, además de las necesidades de clientes y productores.

> 🗣️ El profe dijo: "Pregunta de cajón: ¿qué es IS?". Puedes usar tu propia definición, pero **cita la fuente**.
> **Sistemático** = no hacer las cosas al azar ni por instinto, sino seguir pasos definidos.
> Fíjate en que SWEBOK dice **operación y mantenimiento**, no solo desarrollo. "No somos solo desarrolladores".

### IS como tecnología en capas (Pressman) 🧱
```
        [ Herramientas ]   → soporte automatizado (Git, IDE, JUnit, herramientas de diagramas)
        [   Métodos    ]   → el "cómo" técnico (requerimientos, diseño, construcción, pruebas; p.ej. patrones, Scrum, XP, TDD)
        [   Proceso    ]   → la BASE: el marco que une todo
[ Enfoque en la CALIDAD ]  → los cimientos (compromiso organizacional)
```
Para recordarlo, de abajo hacia arriba: **Calidad → Proceso → Métodos → Herramientas**.

### ¿Qué es calidad de software?
- La capacidad del producto de **satisfacer necesidades declaradas e implícitas** bajo condiciones especificadas.
- El grado en que cumple los requerimientos establecidos, **pero** eso solo vale si esos requerimientos reflejan bien lo que el stakeholder necesita, quiere y espera.

**Stakeholder:** cualquiera que tenga interés en que el proyecto salga bien (quien paga, quien lo usa, el patrocinador interno, los ingenieros, soporte…).

---

## 5. ¿Por qué es importante la IS?
- Permite construir sistemas complejos **a tiempo, dentro del presupuesto y con calidad**.
- Impone **disciplina** a un trabajo que puede ser caótico, **pero** deja adaptar el enfoque.
- La sociedad depende del software → hay que producirlo **confiable, económico y rápido**.
- **A largo plazo sale más barato** usar IS. No usarla significa más costo en **pruebas, aseguramiento de calidad y mantenimiento**.
- Hace **visibles y cuantificables los trade-offs**: más seguridad cuesta desempeño, menos tiempo cuesta más personas o más dinero. Cada decisión (lenguaje, framework, metodología) se **justifica comparando alternativas**, no "con el hígado".
- Los métodos son una **caja de herramientas**, no una camisa de fuerza.

🌳 **El meme del columpio**: lo que el usuario necesitaba, lo que entendió el ingeniero de requerimientos, lo que diseñó el arquitecto y lo que codificó el programador son cosas distintas, y lo que hacía falta era una **llanta colgada**. La IS busca que todos esos pasos estén alineados.

---

## 6. El proceso de software
### Jerarquía: Actividad > Acción > Tarea
| Nivel | Qué es | Ejemplo |
|---|---|---|
| **Actividad** | Objetivo amplio, se aplica siempre (sin importar dominio, tamaño ni rigor) | Comunicación con stakeholders |
| **Acción** | Conjunto de tareas que produce un **producto de trabajo importante** | Diseño arquitectónico → modelo arquitectónico |
| **Tarea** | Objetivo pequeño y bien definido, con resultado **tangible** | Hacer una prueba unitaria |

**Proceso** = colección de actividades, acciones y tareas para crear un producto de trabajo.
**Proceso de software** = secuencia de actividades que lleva a producir un producto de software.

### ⚠️ Dos autores, dos listas (no las confundas)
| **Sommerville: 4 actividades fundamentales** | **Pressman y Maxim: 5 actividades del marco genérico** |
|---|---|
| 1. **Especificación**: definir qué se produce y sus restricciones | 1. **Comunicación**: entender objetivos y levantar requerimientos con el cliente |
| 2. **Desarrollo**: diseñar y programar | 2. **Planificación**: el "mapa" (plan de proyecto: tareas, riesgos, recursos, productos, cronograma) |
| 3. **Validación**: verificar que es lo que el cliente quiere | 3. **Modelado**: "bocetos" para entender requerimientos y diseño |
| 4. **Evolución**: modificarlo según cambien el cliente o el mercado | 4. **Construcción**: código + pruebas |
| | 5. **Despliegue**: se entrega (completo o un incremento) y el cliente da feedback |

🧠 Truco: **Sommerville = 4 = "E-D-V-E"** · **Pressman = 5 = "Co-Pla-Mo-Cons-Des"**

### Tipos de software
Según el tipo, esas actividades se organizan distinto: aplicaciones stand-alone, transaccionales interactivas, embebidas de control, batch, entretenimiento, modelado y simulación, recolección de datos, sistemas de sistemas.

### Adaptación del proceso
El proceso **no es una receta rígida**. Debe ser **ágil y adaptable** al problema, al proyecto, al equipo y a la cultura de la organización. Dos proyectos pueden tener procesos muy distintos.

---

## 7. Ciclo de vida (SDLC) y modelos de proceso
- **Modelo de proceso de software (o modelo SDLC)** = **representación simplificada** de un proceso.
- Cada modelo muestra el proceso **desde una perspectiva** → da información **parcial** (p.ej., un modelo de actividades muestra el orden, pero no los roles).
- Son **marcos (frameworks)** de alto nivel que se **extienden y adaptan**.

| Modelos tradicionales | Modelos especializados |
|---|---|
| Cascada (Waterfall) | Desarrollo basado en componentes |
| Incremental | Desarrollo orientado a aspectos |
| Evolutivos | RUP (Rational Unified Process) |
| Concurrentes | |

➡️ Esto se ve en detalle en el **Paso 2**.

---

## ✅ Autotest (responde antes de abrir)
<details><summary>1. ¿Cuáles son las 3 diferencias entre programación individual y profesional?</summary>
Es para otra persona, se hace en equipo y se mantiene y cambia durante toda su vida.</details>

<details><summary>2. ¿Qué fue la crisis del software, dónde y cuándo se reconoció?</summary>
La dificultad de construir sistemas grandes y confiables de forma controlada y costo-efectiva. Se reconoció en la conferencia de la OTAN de 1968 en Garmisch, Alemania.</details>

<details><summary>3. ¿Por qué la IS es una disciplina empírica?</summary>
Porque el software es inmaterial (no sigue leyes físicas) y lo escriben personas para personas.</details>

<details><summary>4. ¿Cuáles son los 3 componentes del software?</summary>
Instrucciones (programas), estructuras de datos y documentación (información descriptiva).</details>

<details><summary>5. Define IS según SWEBOK.</summary>
La aplicación de un enfoque sistemático, disciplinado y cuantificable al desarrollo, operación y mantenimiento del software.</details>

<details><summary>6. ¿Cuáles son las capas de la IS, de abajo hacia arriba?</summary>
Enfoque en la calidad → Proceso → Métodos → Herramientas.</details>

<details><summary>7. Actividad, acción, tarea: da un ejemplo de cada una.</summary>
Actividad: comunicación con stakeholders. Acción: diseño arquitectónico. Tarea: hacer una prueba unitaria.</details>

<details><summary>8. ¿Cuáles son las 4 actividades de Sommerville y las 5 de Pressman?</summary>
Sommerville: especificación, desarrollo, validación, evolución. Pressman: comunicación, planificación, modelado, construcción, despliegue.</details>

<details><summary>9. ¿Qué es un modelo de proceso y por qué da información parcial?</summary>
Es una representación simplificada de un proceso. Lo muestra desde una sola perspectiva (por ejemplo, las actividades sin los roles).</details>

<details><summary>10. ¿Qué es calidad de software?</summary>
La capacidad de satisfacer necesidades declaradas e implícitas bajo condiciones especificadas, o el grado en que cumple los requerimientos, siempre que estos reflejen bien lo que quiere el stakeholder.</details>
