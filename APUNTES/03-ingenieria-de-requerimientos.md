# Paso 3: Ingeniería de Requerimientos
*Fuente: Clase Semana 3 (Lecture 3a, `03aRequirementsEngineering.pdf`) + transcripción sesión 3 (Dr. Mera).*
*La sección 8 viene de las sesiones 3 y 4 (elicitación, atributos de calidad, validación). Pertenece a las clases 04/05, pero el profe la explicó antes del examen.*
*Lo marcado con 🔹 viene de Sommerville para completar diapositivas que eran solo imagen.*

---

## 🎯 La idea en una frase
> Los requerimientos dicen **qué** debe hacer el sistema y **bajo qué restricciones**. Si están mal escritos, todo lo que viene después (diseño, código, pruebas) sale mal, y además abren la puerta a **conflictos legales**.

🗣️ El profe: *"A estas alturas deberían tener claro qué es IR, qué es un RF, cómo se distingue de un RNF, de qué tipo es un RNF y cómo encontrar una ambigüedad, un conflicto o una omisión en un texto de requerimientos."*

---

## 1. Conceptos básicos
- **Requerimientos de un sistema:** descripciones de los **servicios** que debe proveer y las **restricciones** de su operación.
- Reflejan las **necesidades del cliente** para un propósito: controlar un dispositivo, hacer un pedido, buscar información…
- **Ingeniería de requerimientos (IR):** el proceso de **descubrir, analizar, documentar y verificar** esos servicios y restricciones.

### Requerimientos de usuario vs. de sistema (Sommerville)
| De usuario | De sistema |
|---|---|
| Alto nivel, abstractos → **dominio del problema** | Detallados → **dominio de la solución** |
| En **lenguaje natural + diagramas** | Descripción detallada de funciones, servicios y restricciones operativas |
| Qué servicios espera el usuario y con qué restricciones | El documento (a veces llamado **especificación funcional**) define **exactamente qué se implementa** |

👉 **Un requerimiento de usuario puede expandirse en varios requerimientos de sistema.**

---

## 2. Problemas en la ingeniería de requerimientos ⭐
1. Los stakeholders **no saben lo que quieren** o no saben expresarlo en lenguaje que entienda el ingeniero (cuesta imaginar el producto, sobre todo si es innovador).
2. Los stakeholders **no mencionan requerimientos porque los creen obvios**.
3. Los stakeholders **creen saber lo que quieren hasta que les damos lo que pidieron**.
4. Los analistas **creen entender el problema mejor que el stakeholder**.
5. **Nunca sabemos si ya definimos "todos"** los requerimientos.
6. Stakeholders distintos tienen **puntos de vista distintos**, y sus requerimientos pueden **chocar**.
7. El negocio es **dinámico**: los requerimientos **cambian**.
8. Ingeniero y stakeholders caen en la trampa de **imaginar soluciones** en vez de definir **qué hay que hacer**.
9. El ingeniero puede **no entender el problema de negocio** y proponer una solución inadecuada, o aceptar la que trae el cliente.
10. La mayoría de productos de ingeniería parten de modelos previos, pero **los requerimientos hay que crearlos**.
11. **No hay restricciones físicas** que limiten la imaginación.

🗣️ Del profe: los **requerimientos incompletos** son la **mayor causa de proyectos fallidos**. Un error en requerimientos es **el más caro de corregir**: más caro que uno de pruebas, de código o de UML. Malos requerimientos llevan a fallar en **costo, tiempo y calidad**.

---

## 3. Principios de comunicación (Pressman) — 10
Antes de analizar, modelar o especificar, los requerimientos se **recogen en la actividad de comunicación**.

| # | Principio | Idea |
|---|---|---|
| 1 | **Escucha** | Pide aclaración si algo no está claro, pero sin interrumpir a cada rato |
| 2 | **Prepárate antes de comunicar** | Entiende el problema antes de reunirte |
| 3 | **Alguien debe facilitar** | Mantiene la conversación productiva, media conflictos y vela por los demás principios |
| 4 | **Cara a cara es mejor** | Mejor aún si hay alguna representación de la información a la vista |
| 5 | **Toma notas y documenta decisiones** | Alguien hace de "secretario" (*recorder*) |
| 6 | **Busca la colaboración** | Cada pequeña colaboración construye confianza y un objetivo común |
| 7 | **Mantén el foco; modulariza la discusión** | Mientras más gente, más se dispersa la conversación |
| 8 | **Si algo no está claro, dibuja** | Un boceto aclara cuando las palabras no bastan |
| 9 | **Avanza** | (a) Si acuerdan algo, avancen. (b) Si no logran acordar, avancen. (c) Si algo no se puede aclarar ahora, avancen |
| 10 | **Negociar no es un juego** | Funciona mejor cuando **ambas partes ganan** |

🧠 Truco: **Escucha, prepárate, facilita, cara a cara, anota, colabora, enfócate, dibuja, avanza, gana-gana.**

---

## 4. Requerimientos funcionales (RF) ⭐
- Son **servicios** que el sistema debe proveer, **cómo reacciona** a ciertas entradas y **cómo se comporta** en ciertas situaciones.
- También pueden decir **lo que el sistema NO debe hacer**.
- Deben expresarse **cuantitativamente** siempre que se pueda, para evitar conflictos con el cliente.
- 🗣️ Son los **más fáciles de identificar**.

**Ejemplos (sistema de pacientes de salud mental):**
- Un usuario podrá buscar en las listas de citas de todas las clínicas.
- El sistema generará cada día, por clínica, la lista de pacientes que se espera que asistan a una cita ese día.
- Cada empleado que use el sistema se identificará de forma única por su número de empleado de **8 dígitos**.

**Más ejemplos:** "Cuando el usuario seleccione *modificar detalles del bote*, el sistema solicitará el nombre del bote". "Al hacer clic en el ícono del vehículo se mostrarán la placa, la velocidad, el rumbo, la latitud, la longitud y la hora de su última ubicación".

🗣️ Ejemplo del profe de lo que **no** debe hacer: *"El sistema no debe permitir que un profesor altere una nota 24 horas después de ingresarla."*

---

## 5. Ambigüedad, conflicto, omisión ⭐⭐ (ejercicio típico de examen)
🗣️ *"Un típico ejercicio de examen: se le da un texto de requerimientos y se le pide encontrar N ambigüedades, conflictos u omisiones."*

| Problema | Qué es |
|---|---|
| **Ambigüedad** | Algo que **distintos lectores pueden interpretar de distintas maneras** |
| **Omisión** | Algo que **no está**: se menciona un cálculo, valor o regla, pero no se dice cuál es |
| **Conflicto** | Una **contradicción**: una parte dice blanco y otra dice negro |

### El ejercicio de la biblioteca (resuelto en clase)
> *"Un estudiante podrá extender el periodo de préstamo de libros en préstamo en cualquier momento. El sistema puede aprobar o rechazar una extensión y debe notificar al prestamista de su decisión. El sistema debe estar disponible a toda hora."*

| Texto | Tipo | Por qué |
|---|---|---|
| "disponible **a toda hora**" | **Ambigüedad** | ¿Horas laborables o calendario? ¿24/7? No es lo mismo, y el costo cambia |
| "en **cualquier momento**" | **Ambigüedad** | ¿Antes o después de que venza el préstamo? ¿Solo en horario laborable? |
| "**podrá extender**" vs. "el sistema puede **aprobar o rechazar**" | **Conflicto** | Si el estudiante "puede" extender, es una capacidad; pero si el sistema puede rechazarla, en realidad es una **solicitud** |
| "aprobar o rechazar" | **Omisión** | ¿Con qué criterios se aprueba o rechaza? |
| "aprobar o rechazar" | **Omisión** | ¿Qué **rol** autoriza la extensión? |
| "extender el periodo" | **Omisión** | ¿Por cuánto tiempo? ¿Cuántas veces? |
| "notificar" | **Omisión** | ¿Por qué medio (email, SMS…)? |
| "prestamista" | **Ambigüedad** | ¿El estudiante? ¿Un profesor o trabajador también puede serlo? Además, ¿"estudiante" y "prestamista" son la misma persona? No queda claro (por eso: **no uses sinónimos**) |

Después piden **escribir 6 requerimientos de usuario** que corrijan el texto (puedes hacer suposiciones razonables). Ejemplo: *"El estudiante podrá solicitar una extensión del préstamo hasta 1 día antes de la fecha de vencimiento"*.

### ¿Por qué importa? (profe)
- Lo **ambiguo** o en **conflicto** termina en un **conflicto legal** ("yo me acojo a esta línea y tú a esa": trabajo para el abogado).
- Lo **omitido** se llena con **suposiciones del diseñador**, que termina diseñando cualquier cosa.
- El documento es el **insumo de diseñadores, arquitectos y testers**. Debe ser claro, completo y **versionado**.
- 🚫 **No uses sinónimos.** Si en un lugar dices *email*, nunca digas *correo electrónico*. Si dices *aprobación*, nunca *autorización* ni *visto bueno*.

---

## 6. Requerimientos no funcionales (RNF) ⭐⭐
- Son **restricciones** sobre los servicios o funciones del sistema: de **tiempo**, del **proceso de desarrollo**, impuestas por **estándares**…
- Suelen aplicar al **sistema completo** (son **transversales**), no a una función en particular.
  - 🗣️ Ejemplo: "el profesor puede descargar la asistencia en Excel" solo afecta al profesor (RF). "El sistema debe cumplir la **Ley Orgánica de Protección de Datos**" afecta a **todos** los módulos (RNF).
- Se escriben en **lenguaje natural** y deben ser **cuantitativos (con métricas)**, para que el cliente pueda validarlos y no haya conflictos.
  - 🗣️ *"Si usted me dice 'buen desempeño'… al final yo le digo que para mí es 1 milisegundo, y si no, no le pago."*
- **A veces un RNF genera RF.** Ejemplo: "solo usuarios autorizados" (RNF de seguridad) genera: una ventana para actualizar la lista de autorizados, rechazar a los no autorizados con el mensaje XYZ y comparar el login contra la lista (RF).

### Taxonomía de Sommerville: **P-O-E** (Producto, Organizacional, Externo) ⭐⭐⭐
🗣️ *"Hay varias taxonomías, pero la de Sommerville es la más completa. **Usted debe aprendérsela.**"*

```
                       Requerimientos no funcionales
          ┌──────────────────────┼──────────────────────────┐
      PRODUCTO              ORGANIZACIONAL                EXTERNO
   ├ Usabilidad           ├ Ambiental (entorno)        ├ Regulatorio
   ├ Eficiencia           ├ Operacional                ├ Ético
   │   ├ Desempeño        └ Desarrollo                 └ Legislativo
   │   └ Espacio                                            ├ Contable
   ├ Confiabilidad (dependability)                          └ Safety/Security
   └ Seguridad (security)
```

#### 🅿️ Producto: cómo se comporta el producto
| Tipo | Qué cubre | Métricas o ejemplos |
|---|---|---|
| **Eficiencia: desempeño** | Rendimiento | Tiempo de respuesta promedio o máximo por transacción, **transacciones por segundo** (throughput), capacidad, tiempo de refresco de pantalla |
| **Eficiencia: espacio** | Uso de memoria o disco | KBytes, número de chips de RAM |
| **Usabilidad** | Interfaz e interacción | **Horas de entrenamiento** por tipo de usuario, tiempo por tarea, cumplir un *look & feel*, manuales y ayuda, errores por uso, tiempo de instalación |
| **Confiabilidad (dependability)** | La familia de las "-ilities" | Disponibilidad, fiabilidad, robustez, reparabilidad, mantenibilidad |
| **Seguridad (security)** | Resistencia a intrusiones deliberadas o accidentales, sobrevivir a ataques | Cifrado, hash, control de acceso. Se identifican **analizando amenazas** y pueden **generar RF** |

**Dentro de dependability (🗣️ el profe insistió):**
| Término | Significa |
|---|---|
| **Availability (disponibilidad)** | El sistema **está ahí**, arriba, cuando lo consultas |
| **Reliability (fiabilidad)** | Lo que entrega es **correcto y exacto**. Ejemplo: un sistema de impuestos que calcula exactamente, ni de más ni de menos |
| **Robustez** | Se puede caer, pero **se levanta** (redundancia: dos componentes, como en aviones y satélites, idealmente de distinto proveedor y tecnología) |
| **Resiliencia** | **Se adapta** ante la dificultad y continúa sin caerse (como la planta que dobla su tronco para buscar la luz) |
| **Antifragilidad** | Se adapta **y sale más fuerte**: aprende |
| **Safety** | Seguridad de las **personas**: operar sin fallas que pongan en riesgo vidas (semáforos, UCI, torre de control) |
| **Security** | Seguridad **informática**: protegerse de ataques |
| **Mantenibilidad / reparabilidad** | Facilidad para **modificar y reparar**. Métrica: tiempo para hacer un cambio simple, moderado o complejo |

**Métricas de fiabilidad y disponibilidad:** **MTTF** (tiempo medio hasta la falla), probabilidad de no disponibilidad, tasa de ocurrencia de fallas, % de disponibilidad **entre ? am y ? pm**, **MTTR** (tiempo de reinicio tras una falla), % de eventos que causan falla, probabilidad de corrupción de datos, tasa de defectos.

⚠️ 🗣️ *"Cuando diga disponibilidad **nunca ponga 'a toda hora'**, sino **de tal hora a tal hora** y para tales usuarios."* E incluso un "99%" está incompleto si no dice **en qué periodo**: 99% anual permite 3,65 días caído, y podrían ser justo el día de pago.

#### 🅾️ Organizacional: viene de las políticas de la organización
| Tipo | Qué cubre | Ejemplo |
|---|---|---|
| **Ambiental (entorno)** | Plataforma de operación, **portabilidad** | "Debe operar en Windows 11/10 y Linux". "Accesible desde el navegador Opera desde la versión X". Métricas: n.º de plataformas, % de código dependiente de plataforma |
| **Operacional** | **Entrega** (fecha, costo), forma de uso, **interoperabilidad** | "Disponible para agosto 2027". "Presupuesto máximo de 200 000 USD". "Comunicarse con los servicios web del SRI" |
| **Desarrollo** | Lenguaje, método de diseño, **estándares** de proceso | "Usar .NET". "Usar la librería de clases del servidor de desarrollo". Estándares: TCP/IP, ISO 9001, CMM, PRINCE2 |

#### 🅴 Externo: viene de fuera del sistema y de la organización
| Tipo | Qué cubre | Ejemplo |
|---|---|---|
| **Regulatorio** | Organismos reguladores | Un sistema hospitalario debe cumplir lo que dispongan el MSP y el IESS |
| **Legislativo** | **Leyes**: contables, safety, security | "Cumplir la Ley Orgánica de Protección de Datos" |
| **Ético** | Lo aceptable para el cliente y el público | Privacidad. ¿Es ético que una aseguradora guarde el historial médico? "Cumplir el código de ética de la agremiación o de ESPOL" |

### 🎯 Ejemplos para clasificar (de las diapositivas, preguntables)
| Requerimiento | Clasificación |
|---|---|
| El operador debe usar el sistema con media hora de entrenamiento | Producto: **usabilidad** |
| Las respuestas a estimaciones deben tomar menos de 2 s | Producto: **desempeño** |
| Disponible el 99% del tiempo entre las 08h00 y la medianoche | Producto: dependability (**disponibilidad**) |
| Las mejoras deben completarse en una semana | Producto: dependability (**mantenibilidad**) |
| Tiempo promedio de respuesta menor a 5 s | Producto: eficiencia (**desempeño**) |
| Disponible para el inicio del proyecto XYZ | Organizacional: operacional (**entrega**) |
| Un director experimentado lo usa tras 1 hora de entrenamiento | Producto: **usabilidad** (facilidad de uso) |
| Usar la librería de clases del servidor de desarrollo | Organizacional: **desarrollo** |
| Operar en Windows 11/10 y Linux | Organizacional: **ambiental** (plataforma, portabilidad) |
| Accesible solo para usuarios autorizados | Producto: **seguridad** / Externo: ético. **Genera RF** |
| Las estimaciones actualizan la BD histórica del sistema CostXpert | Organizacional: operacional (**interoperabilidad**) |
| Cumplir la ley de protección de datos | Externo: **legislativo** (security) |

### 🔹 Métricas para RNF (tabla de Sommerville; la diapositiva era imagen)
| Propiedad | Métrica |
|---|---|
| Velocidad | Transacciones procesadas por segundo, tiempo de respuesta, tiempo de refresco de pantalla |
| Tamaño | MBytes, n.º de chips de ROM |
| Facilidad de uso | Tiempo de entrenamiento, n.º de pantallas de ayuda |
| Fiabilidad | MTTF, probabilidad de no disponibilidad, tasa de ocurrencia de fallas, disponibilidad |
| Robustez | Tiempo de reinicio tras una falla, % de eventos que causan falla, probabilidad de corrupción de datos |
| Portabilidad | % de sentencias dependientes de la plataforma, n.º de sistemas destino |

### 💡 Estrategia de examen para RNF (consejo literal del profe)
🗣️ *"Usted debe tener en mente **2 o 3 requerimientos aprendidos por cada tipo**, y en el examen los **mapea al contexto**."*
Ejemplo: "el operador usa el sistema con media hora de entrenamiento" se convierte en "un profesor agregado usa el sistema académico tras un taller de máximo 5 horas".

**Ejercicio del examen:** para el texto de la biblioteca, define **2 RNF**, explica por qué son apropiados y **clasifícalos con Sommerville**. Por ejemplo:
1. *"El sistema estará disponible el 99,5% del tiempo cada mes, entre las 07h00 y las 22h00."* → Producto: dependability (disponibilidad). Corrige el "a toda hora".
2. *"La notificación de aprobación o rechazo debe llegar al estudiante en menos de 5 minutos."* → Producto: eficiencia (desempeño).

---

## 7. Puntos clave (take away) de la diapositiva final
1. ¿Qué es la ingeniería de requerimientos?
2. ¿Cuál es la diferencia entre RF y RNF?
3. Da ejemplos de **cada tipo** de RNF de la clasificación de Sommerville.
4. Escribe requerimientos **no ambiguos, completos y consistentes**.

---

## 8. Extra de clase (sesiones 3 y 4): proceso, elicitación, calidad, validación
*Esto es de las clases 04/05, pero el profe lo explicó. Repásalo por si sale.*

### Proceso de IR
**Elicitación** (extraer requerimientos de los stakeholders) → **Análisis** (que sean de calidad: sin ambigüedades, omisiones ni contradicciones) → **Validación** → **Gestión** (documento aprobado **habiéndolo leído** y manejo de los cambios).

### Técnicas de elicitación
**Etnografía, entrevistas, cuestionarios, talleres y prototipos.** No solo reuniones.
- **Etnografía** = observar el proceso. **Pasiva:** observar sin interrumpir. **Activa:** hacer el trabajo tú mismo.
  - ✅ Descubre **requerimientos implícitos**, el **proceso real** (no el documentado) y problemas no documentados.
  - ❌ Consume **tiempo** y puede dar una **visión parcial** (el día que observas quizás no ocurren todas las variantes). No hagas sentir a la gente como animal de experimento.
- **Entrevistas:** casi siempre **estructuradas**. Evita preguntas **parcializadas** (que inducen la respuesta), **subjetivas** e **impositivas**. Pide permiso para grabar, escucha, sé paciente, pregunta "¿algo más?" y **siempre levanta un acta** para que el entrevistado la apruebe.
  - 🗣️ **Protocolo de comunicación:** si el cliente no responde en **48 h**, el documento se da por preaprobado.
- Evalúa el **problema antes que la solución**, recapitula con tus propias palabras y busca los RNF desde el inicio, porque las **decisiones arquitectónicas dependen de los RNF**.

### Atributos de calidad de un requerimiento
**Correcto, no ambiguo** (una sola interpretación), **entendible** (sin jerga técnica para el stakeholder), **completo, consistente, técnicamente factible, priorizado** (**MoSCoW**: *Must, Should, Could, Won't*), **verificable, modificable, trazable** (con ID: RQ-001…), **organizado** (plantilla, glosario, historial de versiones) e **independiente del diseño** (dice el **qué**, no el **cómo**).

🚫 **Términos prohibidos:** *algunos, usualmente, generalmente, a menudo, frecuentemente, tales como, incluyendo…*
✅ Los rangos deben ser explícitos (de 08h00 a 17h00, no "horas laborables"), con al menos **2 ejemplos** en cálculos, sin pronombres ambiguos ("el cual", "ello") y **sin sinónimos**.

### Verificación vs. validación
| Verificación | Validación |
|---|---|
| ¿El software **cumple los requerimientos escritos**? | ¿Satisface las **expectativas del cliente**? |
| "¿Construimos **bien** el producto?" | "¿Construimos el producto **correcto**?" |
| Más técnica | Va más allá de la verificación |

**Validación de requerimientos** = revisar que los requerimientos definen **exactamente lo que el cliente quiere** (buscar errores en el documento). Chequeos: **validez, consistencia, completitud, realismo, verificabilidad**. Técnicas: **revisiones, prototipado, generación de casos de prueba**.
**Criterios para verificar un requerimiento:** aprobación de un **experto**, **prueba medible**, **prueba de aceptación** del usuario, **simulación** y **encuestas de satisfacción**.

---

## ✅ Autotest
<details><summary>1. ¿Qué es la ingeniería de requerimientos?</summary>
El proceso de descubrir, analizar, documentar y verificar los servicios que debe proveer el sistema y las restricciones de su operación.</details>

<details><summary>2. Requerimiento de usuario vs. de sistema.</summary>
El de usuario es de alto nivel, en lenguaje natural más diagramas (dominio del problema). El de sistema es detallado y define exactamente qué se implementa (dominio de la solución). Uno de usuario puede expandirse en varios de sistema.</details>

<details><summary>3. Menciona 4 problemas de la IR.</summary>
Los stakeholders no saben lo que quieren; omiten lo que les parece obvio; tienen puntos de vista en conflicto; los requerimientos cambian; nunca sabes si los tienes todos; se piensa en soluciones en vez de en el qué.</details>

<details><summary>4. Ambigüedad, conflicto y omisión: define cada una.</summary>
Ambigüedad: admite más de una interpretación. Conflicto: una contradicción entre partes del texto. Omisión: falta información (una regla, un valor, un rol).</details>

<details><summary>5. ¿Qué es un RF y qué es un RNF? ¿Qué rasgo clave tiene el RNF?</summary>
El RF dice qué hace el sistema (servicios, reacciones, comportamiento, o lo que no debe hacer). El RNF es una restricción sobre cómo se proveen esos servicios. Suele ser transversal (aplica a todo el sistema) y debe tener métricas.</details>

<details><summary>6. ¿Cuáles son las 3 categorías de RNF de Sommerville y sus subtipos?</summary>
Producto (usabilidad, eficiencia [desempeño, espacio], confiabilidad, seguridad). Organizacional (ambiental, operacional, desarrollo). Externo (regulatorio, ético, legislativo [contable, safety/security]).</details>

<details><summary>7. Disponibilidad vs. fiabilidad vs. robustez.</summary>
Disponibilidad: el sistema está arriba cuando lo usas. Fiabilidad: lo que entrega es correcto. Robustez: si se cae, se levanta (redundancia).</details>

<details><summary>8. Clasifica: "El sistema debe operar en Windows y Linux".</summary>
Organizacional, ambiental (plataforma de operación, portabilidad).</details>

<details><summary>9. Clasifica: "Disponible para el inicio del proyecto XYZ".</summary>
Organizacional, operacional (entrega).</details>

<details><summary>10. ¿Por qué "el sistema debe estar disponible a toda hora" está mal escrito?</summary>
Es ambiguo (¿horas laborables o calendario?) y no tiene métrica. Debe decir un rango y un %: por ejemplo, 99% entre 08h00 y 24h00 cada mes.</details>

<details><summary>11. Da un ejemplo de un RNF que genere RF.</summary>
"Solo usuarios autorizados pueden acceder" (seguridad) genera: mantener una lista de usuarios autorizados, una pantalla para actualizarla y rechazar el acceso con un mensaje.</details>

<details><summary>12. ¿Cuáles son los 10 principios de comunicación?</summary>
Escucha; prepárate; alguien facilita; cara a cara; toma notas; colabora; enfócate y modulariza; si no está claro, dibuja; avanza (si acuerdan, si no acuerdan, si no se puede aclarar); negociar es gana-gana.</details>

<details><summary>13. Verificación vs. validación.</summary>
Verificación: el software cumple los requerimientos escritos ("¿lo construimos bien?"). Validación: satisface las expectativas del cliente ("¿construimos el producto correcto?").</details>
