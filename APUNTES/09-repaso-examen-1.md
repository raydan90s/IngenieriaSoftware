# Repaso final: Examen 1
*Alcance: `01bSoftwareProcesses` + `02ProcessModels` + `03aRequirementsEngineering`. Scrum no entra.*
*🗣️ = lo dijo o lo recalcó el profe en clase. Detalle completo en los pasos 01, 02 y 03.*

---

## 🔥 Top 10: lo que el profe dijo que sale
1. 🗣️ **"Pregunta de cajón: ¿qué es ingeniería de software?"** Puedes usar tu propia definición, pero **cita la fuente**.
2. 🗣️ **¿Por qué es importante la IS?** "Dame 2 razones".
3. 🗣️ **La documentación también es software**: mucha gente lo olvida.
4. 🗣️ **Ejercicio típico:** encontrar N **ambigüedades, conflictos u omisiones** en un texto de requerimientos.
5. 🗣️ **Escribir requerimientos de usuario** que corrijan ese texto.
6. 🗣️ **Definir RNF para un contexto y clasificarlos con Sommerville.** "Debe aprendérsela".
7. 🗣️ **Clasificar un RNF dado** en la taxonomía de Sommerville.
8. 🗣️ **RNF siempre con métricas.** "Nunca ponga 'a toda hora'".
9. 🗣️ **No usar sinónimos** en un documento de requerimientos.
10. 🗣️ **Respuestas cortas:** "2 o 3 líneas, sin inventarse nada. Si no sabe, deje en blanco".

---

## 1️⃣ Clase 01b: Ingeniería de software y procesos

### Definiciones que debes poder escribir de memoria
| Concepto | Definición |
|---|---|
| **IS (SWEBOK)** | Aplicación de un enfoque **sistemático, disciplinado y cuantificable** al **desarrollo, operación y mantenimiento** del software |
| **IS (Sommerville)** | Disciplina de ingeniería que se ocupa de **todos los aspectos de la producción de software**, desde la **especificación inicial** hasta el **mantenimiento** en uso |
| **Software (Pressman)** | (1) **Instrucciones** (programas), (2) **estructuras de datos**, (3) **información descriptiva** (documentación) |
| **Calidad de software** | Capacidad de satisfacer **necesidades declaradas e implícitas** bajo condiciones especificadas |
| **Stakeholder** | Cualquiera con interés en el proyecto: quien paga, quien usa, el patrocinador, los ingenieros, soporte… |
| **Proceso de software** | Secuencia de actividades que lleva a producir un producto de software |
| **Modelo de proceso** | **Representación simplificada** de **un** proceso, desde **una** perspectiva, por lo tanto **parcial** |

🗣️ "**Sistemático** = no hacer las cosas al azar ni por instinto." Y fíjate que dice **operación y mantenimiento**: *"no somos solo desarrolladores"*.

### ¿Por qué es importante la IS? 🗣️ (ten 2 o 3 listas)
- Permite construir sistemas complejos **a tiempo, dentro del presupuesto y con calidad**.
- **A largo plazo es más barato**: sin IS sube el costo de pruebas, de aseguramiento de calidad y de mantenimiento.
- 🗣️ **Hace visibles y cuantificables los trade-offs** (más seguridad cuesta desempeño). Las decisiones se **justifican comparando alternativas**, *"no con el hígado ni con el páncreas"*.
- **Impone disciplina**, pero 🗣️ *"los métodos son una caja de herramientas, no una camisa de fuerza"*.

### Datos que suelen preguntar
- **Crisis del software:** cómo construir sistemas **grandes y confiables** de forma **controlada y costo-efectiva**. Se reconoció en la **OTAN, 1968, Garmisch (Alemania)**. Causa: quienes hacían software venían del hardware y no sabían de procesos.
- **Disciplina empírica** porque el software es **inmaterial** y lo escriben **personas para personas**.
- **Individual vs. profesional:** es **para otros**, se hace **en equipo** y **se mantiene y cambia** durante años.
- **RF** = qué hace. **RNF** = cómo lo hace (ejemplo del zapato: la comodidad es un RNF).
- **Capas (Pressman), de abajo hacia arriba:** **Enfoque en la calidad → Proceso** (la base que une todo) **→ Métodos → Herramientas**.
- **Actividad** (amplia, siempre se aplica) **> Acción** (conjunto de tareas que produce un **producto de trabajo importante**) **> Tarea** (pequeña y **tangible**).
- **Sommerville, 4 actividades:** Especificación, Desarrollo, Validación, Evolución.
- **Pressman, 5 actividades:** Comunicación, Planificación, Modelado, Construcción, Despliegue.

---

## 2️⃣ Clase 02: Modelos de proceso

| Modelo | Clave | Úsalo cuando… |
|---|---|---|
| **Cascada** | **Plan-driven**: todo se planifica antes. Etapas en secuencia | Requerimientos **claros**. Sistemas **embebidos, críticos (safety) o multiempresa** |
| **Modelo V** | Cada **prueba valida** un modelo del lado izquierdo | Variante de cascada |
| **Incremental** | Primero el **producto núcleo**; cada entrega es **usable** | Hay que entregar rápido algo **básico**. Alto riesgo o pocos recursos |
| **Prototipado** | Sirve para **aclarar requerimientos** | Requerimientos o interfaz **inciertos** |
| **Espiral (Boehm)** | **Guiado por el riesgo**, con **hitos de anclaje** (compromiso de los stakeholders) | Proyectos con mucho riesgo |
| **Concurrente** | Actividades con **estados**; los **eventos** disparan transiciones | El **cronograma es crítico** |
| **CBSE** | **Reuso** y **COTS**. Análisis de componentes → modificación de requerimientos → diseño con reuso → integración | **Portafolio de sistemas** |
| **RUP** | **Separa actividades de fases**: Inicio, Elaboración, Construcción, Transición | Iterativo e incremental |
| **Ágil** | Entregas tempranas, equipos pequeños, poca documentación, aceptar el cambio | Sistemas **pequeños o medianos**, **pocos stakeholders**, **sin contrato fijo** |

### Diferencias que confunden
- **Incremental vs. evolutivo:** en el incremental **sabes** qué quieres y lo entregas por partes. En el evolutivo **no sabes bien**, y el producto **puede terminar siendo otro**.
- **Riesgos del prototipado:** (1) el cliente cree que **ya está listo** (sin calidad ni mantenibilidad); (2) el ingeniero se queda con **malas decisiones** que tomó por ir rápido.
- **Problemas de ágil:** **contratos** legales, **mantenimiento** (que es la mayor parte del costo), **equipos distribuidos**.
- **Historias de usuario:** su problema es la **completitud** (¿están todas?).
- **¿Ágil o plan?** Depende del **sistema** (tamaño, tipo, vida útil, regulación), del **equipo** (habilidad, distribución, herramientas) y de la **organización** (contrato, cliente disponible, cultura). Muchas veces la respuesta es un **híbrido**.

---

## 3️⃣ Clase 03a: Ingeniería de requerimientos (⭐ la más pesada)

### Conceptos
- **IR** = proceso de **descubrir, analizar, documentar y verificar** los **servicios** y **restricciones** del sistema.
- **Requerimiento de usuario** (alto nivel, dominio del **problema**) vs. **de sistema** (detallado, dominio de la **solución**). Uno de usuario genera **varios** de sistema.
- 🗣️ Los **requerimientos incompletos** son la **mayor causa de proyectos fallidos**. Un error en requerimientos es **el más caro** de corregir.

### Problemas de la IR (memoriza 4 o 5)
No saben lo que quieren · omiten lo "obvio" · *"creen saber lo que quieren hasta que les damos lo que pidieron"* · el analista cree entender mejor que el stakeholder · nunca sabes si los tienes todos · puntos de vista en conflicto · los requerimientos cambian · se piensa en soluciones en vez de en el qué.

### 10 principios de comunicación
Escucha · prepárate · alguien facilita · cara a cara · toma notas · colabora · enfócate y modulariza · si no está claro, dibuja · avanza · negociar es gana-gana.

### RF vs. RNF
| RF | RNF |
|---|---|
| **Qué** hace el sistema: servicios, reacciones, comportamiento, o lo que **no** debe hacer | **Restricciones** sobre cómo se proveen los servicios |
| Afecta una función o módulo | 🗣️ **Transversal**: afecta a todo el sistema |
| Los más fáciles de identificar | 🗣️ Deben tener **métricas** |

Un RNF puede **generar RF**. Ejemplo: "solo usuarios autorizados" lleva a una lista de usuarios, una pantalla de mantenimiento y un mensaje de rechazo.

### 🗣️ Ambigüedad / conflicto / omisión
- **Ambigüedad:** admite **más de una interpretación** ("a toda hora", "en cualquier momento").
- **Conflicto:** **contradicción** ("podrá extender" vs. "el sistema puede rechazar").
- **Omisión:** **falta** algo (criterio de aprobación, rol que aprueba, medio de notificación, duración).
- 🗣️ Por qué importa: lo ambiguo o en conflicto lleva a **juicios**; lo omitido lleva a **suposiciones del diseñador**.

### 🗣️ Taxonomía de Sommerville: **P-O-E**
| Categoría | Subtipos | Ejemplo para memorizar |
|---|---|---|
| **Producto** | **Usabilidad** | "Un profesor usa el sistema tras un taller de máximo 5 h" |
| | **Eficiencia: desempeño** | "Consulta de notas en menos de 2 s" / "1000 transacciones por segundo" |
| | **Eficiencia: espacio** | "La app no debe ocupar más de 50 MB" |
| | **Dependability** | "Disponible el 99% del tiempo cada mes, de 08h00 a 24h00" |
| | **Seguridad (security)** | "Solo usuarios autorizados" / "Contraseñas cifradas con SHA-256" |
| **Organizacional** | **Ambiental** | "Debe operar en Windows 11 y Linux" |
| | **Operacional** | "Listo para agosto 2027" / "Máximo 200 000 USD" / "Integrarse con el SRI" |
| | **Desarrollo** | "Desarrollarse en .NET" / "Cumplir ISO 9001" |
| **Externo** | **Regulatorio** | "Cumplir las normas del MSP y el IESS" |
| | **Legislativo** | "Cumplir la Ley Orgánica de Protección de Datos" |
| | **Ético** | "Cumplir el código de ética de ESPOL" |

🗣️ **Dependability, las palabras que preguntó en clase:**
- **Availability:** el sistema **está ahí**.
- **Reliability:** lo que entrega es **correcto**.
- **Robustez:** se cae y **se levanta** (redundancia).
- **Resiliencia:** **se adapta** y continúa.
- **Antifragilidad:** se adapta **y sale más fuerte**.
- **Safety:** protege **personas**. **Security:** protege **información** (seguridad informática).

🗣️ **"99%" también está incompleto si no dice el periodo**: 99% anual equivale a 3,65 días caído, y podría ser justo el día de pago.

### 🗣️ Reglas de redacción
**Sin sinónimos** · sin *algunos, usualmente, tales como, incluyendo* · **rangos explícitos** (de 08h00 a 17h00) · **2 ejemplos** en cálculos · sin pronombres ambiguos · un **ID** por requerimiento (RQ-001) · glosario de términos.

### Extra (por si sale)
- **Verificación:** ¿cumple los requerimientos escritos? ("¿lo construimos **bien**?"). **Validación:** ¿satisface al cliente? ("¿construimos el producto **correcto**?").
- **Elicitación:** etnografía (pasiva o activa), entrevistas, cuestionarios, talleres, prototipos.
- **Priorizar con MoSCoW:** *Must, Should, Could, Won't*.

---

## 📝 Simulacro (responde en papel antes de abrir)

<details><summary>1. ¿Qué es la ingeniería de software? Cita la fuente. (2 pts)</summary>
SWEBOK: la aplicación de un enfoque sistemático, disciplinado y cuantificable al desarrollo, operación y mantenimiento del software.</details>

<details><summary>2. Da 2 razones por las que es importante la IS. (2 pts)</summary>
Permite construir sistemas complejos a tiempo, dentro del presupuesto y con calidad. Hace visibles y cuantificables los trade-offs para justificar decisiones. A largo plazo es más barata.</details>

<details><summary>3. ¿Qué 3 elementos componen el software según Pressman? (1 pt)</summary>
Instrucciones (programas), estructuras de datos y documentación.</details>

<details><summary>4. ¿Por qué se dice que el espiral está "guiado por riesgo"? (2 pts)</summary>
Porque en cada ciclo se identifica y ataca primero el mayor riesgo. Según ese riesgo, cada vuelta puede parecerse a otro modelo, por eso es un "generador de modelos". Los hitos de anclaje aseguran el compromiso de los stakeholders.</details>

<details><summary>5. Caso: un software de control de vuelo regulado por la autoridad aeronáutica. ¿Qué modelo usarías? (2 pts)</summary>
Uno dirigido por plan (cascada o Modelo V). Es un sistema crítico de safety y está regulado, así que necesita especificación y documentación completas.</details>

<details><summary>6. Encuentra 3 problemas en: "El sistema debe enviar reportes rápidamente a algunos gerentes y estar disponible siempre." (3 pts)</summary>
"Rápidamente": ambigüedad, falta la métrica (¿en menos de cuántos segundos?). "Algunos gerentes": ambigüedad u omisión (¿cuáles? ¿qué rol?); "algunos" es un término prohibido. "Disponible siempre": ambigüedad (¿24/7? ¿qué %? ¿en qué horario?). Omisión: ¿qué contienen los reportes? ¿por qué medio se envían?</details>

<details><summary>7. Clasifica con Sommerville. (5 pts)
a) "Responder consultas de notas en menos de 3 s".
b) "Desarrollarse en Java".
c) "Cumplir el reglamento de la Superintendencia de Bancos".
d) "Un estudiante nuevo se matricula sin capacitación en menos de 10 min".
e) "Estar listo antes del inicio del semestre 2027-I".</summary>
a) Producto: eficiencia (desempeño). b) Organizacional: desarrollo. c) Externo: regulatorio. d) Producto: usabilidad. e) Organizacional: operacional (entrega).</details>

<details><summary>8. Diferencia entre disponibilidad, fiabilidad y robustez. (3 pts)</summary>
Disponibilidad: el sistema está arriba cuando lo usas. Fiabilidad: lo que entrega es correcto y exacto. Robustez: si se cae, se recupera (por ejemplo, con un componente redundante).</details>

<details><summary>9. Escribe 2 RNF para un sistema de citas médicas y clasifícalos. (4 pts)</summary>
"El sistema estará disponible el 99,5% del tiempo cada mes, entre las 06h00 y las 22h00" → Producto: dependability (disponibilidad). "El sistema debe cumplir la Ley Orgánica de Protección de Datos Personales en el manejo de historias clínicas" → Externo: legislativo.</details>

<details><summary>10. ¿Qué significa que RUP "separa actividades de fases"? (2 pts)</summary>
En cada fase (Inicio, Elaboración, Construcción, Transición) se hacen todas las actividades (requerimientos, diseño, código, pruebas), pero en distinta proporción. A diferencia de cascada, la fase no equivale a una sola actividad.</details>
