# Paso 2: Modelos de Proceso de Software y Desarrollo Ágil
*Fuente: Clase Semana 2 (Lecture 2, `02ProcessModels.pdf`). Esta clase no tiene transcripción.*
*Lo marcado con 🔹 viene de Sommerville/Pressman para completar diapositivas que eran solo imagen.*

---

## 🎯 La idea en una frase
> No existe un modelo "mejor": cada uno organiza las actividades (especificar, desarrollar, validar, evolucionar) de forma distinta. Se elige según **qué tan claros están los requerimientos**, el **riesgo**, el **tamaño** y el **contexto**.

### Mapa mental rápido
```
                    ┌─ Cascada (+ Modelo V) ......... lineal, todo planificado
  Tradicionales ────┼─ Incremental .................. entregas por partes
  (plan-driven)     ├─ Evolutivos ─┬─ Prototipado ... para aclarar requerimientos
                    │              └─ Espiral ....... guiado por RIESGO (Boehm)
                    └─ Concurrente .................. actividades en paralelo con estados
  Especializados ───┬─ Basado en componentes (CBSE) .. reuso / COTS
                    └─ RUP .......................... 4 fases, iterativo e incremental
  Ágil ─────────────── XP, Scrum, DSDM ............... incremental, poca documentación
```

---

## 1. Modelo en Cascada (Waterfall) 🌊
- Es el **primer modelo publicado** (1970). Sale de la ingeniería de **grandes sistemas militares**.
- El desarrollo avanza en **etapas** que caen una tras otra, como una cascada.
- Es **dirigido por plan (plan-driven)**: se planifica y programa **todo antes** de empezar a desarrollar.

🔹 Etapas (Sommerville): Definición de requerimientos → Diseño de sistema y software → Implementación y prueba unitaria → Integración y prueba del sistema → Operación y mantenimiento.

**Características**
- El producto **no se entrega** hasta la prueba de aceptación del sistema completo.
- Cada etapa debe estar **correcta y completa** antes de empezar la siguiente.
- Cada etapa transforma la salida de la anterior.
- Corregir un error o hacer un cambio puede obligar a **rehacer etapas anteriores**.

**✅ ¿Cuándo SÍ usarlo?**
1. **Sistemas embebidos**: el hardware es inflexible y no se pueden postergar las decisiones del software.
2. **Sistemas críticos**: hace falta un análisis extenso de **safety y security**, y para eso la especificación y el diseño deben estar completos.
3. **Sistemas grandes entre varias empresas**: se necesitan especificaciones completas para que cada empresa desarrolle su subsistema por separado.
- También en **proyectos pequeños, parecidos a otros anteriores y con requerimientos bien entendidos**.
- Ventaja: le da al **project manager un marco claro** para planificar y gestionar.

**❌ ¿Cuándo NO?** Cuando el equipo puede comunicarse de manera informal y los **requerimientos cambian rápido**.

**Debilidades**
- Es lento: rehacer etapas anteriores requiere aprobación gerencial.
- Las pruebas se concentran **al final**.
- Exige requerimientos claros **al inicio**, lo cual es difícil de lograr.
- El cliente solo participa en **requerimientos y aceptación**.
- Las etapas se solapan por presión de tiempo, lo que genera retrabajo.
- El cliente no puede expresar todo a tiempo y tiene que **esperar** al producto final.

### Modelo V (variante de cascada)
Relaciona cada actividad de **aseguramiento de calidad (pruebas)** con la actividad de comunicación o modelado que le corresponde.
- **Lado izquierdo (bajando):** los requerimientos se refinan hasta representaciones cada vez más detalladas y técnicas.
- **Lado derecho (subiendo):** después del código, una serie de **pruebas valida cada modelo** del lado izquierdo.
```
Requerimientos ─────────────────── Prueba de aceptación
   Diseño arquitectónico ───── Prueba de integración/sistema
       Diseño de componentes ── Prueba de componentes
                  Código (abajo, en la punta de la V)
```

---

## 2. Modelo Incremental 🧩
- Sirve cuando hace falta **entregar pronto un conjunto limitado de funciones** y luego ampliarlo en versiones posteriores.
- **Combina flujos lineales y paralelos**: es una serie de "mini cascadas" escalonadas.
- Es un **punto intermedio** entre cascada y evolutivo.
- El **primer incremento suele ser el producto núcleo (core)**: cubre lo básico y deja fuera funciones complementarias.
- El cliente usa o evalúa ese núcleo → se arma el **plan del siguiente incremento** → se repite hasta tener el producto completo.
- **Cada sistema parcial es usable** y cada vez más completo.

| ✅ Ventajas | ❌ Desventajas |
|---|---|
| El cliente tiene partes funcionando **antes** | El producto final puede **tardar más y costar más** |
| Cada fase aprovecha la experiencia del cliente | Es difícil definir incrementos que den algo útil |
| Cada fase usa menos recursos y molesta menos al cliente | El proceso **no es visible** para los gerentes, que necesitan entregables regulares |
| **Baja el riesgo** de fracaso | La **estructura se degrada** con cada incremento |
| Lo más importante se hace primero y **se prueba más** | Los cambios frecuentes dejan **código desordenado** |

---

## 3. Modelos Evolutivos 🔄
**¿Por qué existen?**
- Los requerimientos **cambian** durante el desarrollo, así que un camino en línea recta no es realista.
- Los plazos del mercado impiden terminar un producto completo, **pero** hay que sacar una versión limitada.
- El núcleo se entiende bien, pero las **extensiones aún no están definidas**.

Son **iterativos**: producen versiones cada vez más completas, y **cada versión puede resultar en un producto diferente**.

### 3a. Prototipado
**Flujo:** Comunicación → Plan rápido → **Diseño rápido** (lo que ve el usuario: interfaz, formatos de salida) → Construcción del prototipo → **Despliegue y feedback** → se repite.
- Idealmente, el prototipo es un **mecanismo para identificar requerimientos**.
- Les gusta a todos: el usuario "siente" el sistema y el desarrollador construye algo enseguida.

**⚠️ Problemas**
1. El stakeholder ve algo que **parece funcionar** y no sabe que, por la prisa, **no se cuidó la calidad ni la mantenibilidad**.
2. El ingeniero toma **malas decisiones de implementación** para que funcione rápido (lenguaje inadecuado, algoritmo ineficiente), se acostumbra a ellas y **olvida por qué eran malas**.

### 3b. Modelo Espiral (Barry Boehm) 🌀
- Une lo **iterativo del prototipado** con lo **controlado y sistemático de la cascada**.
- Es un **generador de modelos de proceso guiado por el riesgo (risk-driven)**. ⭐ Esta frase es clave.
- Tiene dos rasgos distintivos:
  1. **Enfoque cíclico**: el sistema crece en **definición e implementación** mientras **baja su riesgo**.
  2. **Hitos de anclaje (anchor point milestones)**: aseguran el **compromiso de los stakeholders** con soluciones factibles y aceptables para todos.

---

## 4. Modelos Concurrentes ⚡
- También se llama **ingeniería concurrente**.
- Permite representar los elementos **iterativos y concurrentes** de cualquier modelo.
- Cada actividad, acción o tarea tiene **estados** (inactiva, en desarrollo, en espera de cambios, en revisión, terminada…). Ciertos **eventos disparan transiciones** entre esos estados.
- *Ejemplo:* durante el diseño se descubre una inconsistencia en el modelo de requerimientos. Ese **evento** hace que la actividad de análisis pase de "terminada" a "en espera de cambios".
- **Cuándo usarlo:** cuando el **cronograma es crítico**.

---

## 5. Desarrollo Basado en Componentes (CBSE) 🧱
- **Componente:** unidad de software **independiente y desplegable**, completamente definida y **accedida mediante interfaces**.
- Se basa en el **reuso de componentes** más un **framework de integración**. El trabajo es **integrar**, no desarrollar desde cero.
- Los componentes pueden ser sistemas completos: **COTS** (*Commercial Off-The-Shelf*).

**4 actividades** (en orden):
1. **Análisis de componentes**: a partir de los requerimientos, buscar el componente que mejor se ajuste.
2. **Modificación de requerimientos**: se ajustan según los componentes disponibles.
3. **Diseño del sistema con reuso**: se organiza el framework. Puede haber algo de desarrollo propio si no existe un componente.
4. **Desarrollo e integración**: se integran los componentes y los COTS.

**Tipos de componentes:** servicios web (invocación remota), colecciones de objetos para frameworks (.NET, JEE) y sistemas stand-alone configurables.
**Modelo de componentes:** estándares de implementación, documentación y despliegue que garantizan la **interoperabilidad**. Ejemplos: **EJB, .NET, CORBA**.

| ✅ Ventajas | ❌ Limitaciones |
|---|---|
| Menos software que desarrollar, por lo tanto **menos costo y riesgo** | Se **pierde el control de la evolución** si las nuevas versiones del componente no dependen de la organización |
| **Entregas más rápidas** | Ajustar los requerimientos puede producir un sistema que **no satisfaga las necesidades reales** |

**Cuándo usarlo:** para desarrollar un **portafolio de sistemas** dentro de una organización o para venta comercial.

---

## 6. RUP (Rational Unified Process) 🏛️
- **Separa las actividades de las fases** ⭐ (esa es su idea distintiva).
- Su flujo es **iterativo e incremental**, con un "sabor evolutivo".

| Fase | Qué se hace | Equivale en el modelo genérico a |
|---|---|---|
| **1. Inception (Inicio)** | Se establece el **caso de negocio**, se identifican los requerimientos de negocio, se propone una **arquitectura preliminar** y se planifica el proyecto iterativo | Comunicación + Planificación |
| **2. Elaboration (Elaboración)** | Se entiende el **dominio del problema** y la **arquitectura**. Se refinan los **casos de uso** preliminares | Comunicación + Modelado |
| **3. Construction (Construcción)** | Diseño, programación y pruebas. Se construyen los componentes que hacen operativo cada caso de uso | Construcción |
| **4. Transition (Transición)** | **Se despliega** en el entorno real, hay **pruebas beta** con usuarios y se preparan **manuales** | Despliegue |

🧠 Truco: **I-E-C-T** → "**I**nicio, **E**laboro, **C**onstruyo, **T**ransfiero".

---

## 7. Desarrollo Ágil 🏃
**¿Por qué surge?** Los negocios cambian rápido y es **casi imposible tener requerimientos completos y estables**. Despega a finales de los 90: **XP (1999), Scrum (2001), DSDM (2003)**.

**Ágil = filosofía + guías de desarrollo**
- **La filosofía** promueve: satisfacción del cliente y **entregas incrementales tempranas**, **equipos pequeños y motivados**, **métodos informales**, **mínimos productos de trabajo** (poca documentación) y **simplicidad**.
- **Las guías** priorizan la **entrega** sobre el análisis y el diseño (que no se prohíben), con **comunicación activa y continua** entre desarrolladores y clientes.

**Características**
- Especificación, diseño e implementación están **intercalados**.
- Se desarrolla en **incrementos**, y los usuarios participan en especificar y evaluar cada uno.
- Usa **muchas herramientas**: pruebas automatizadas, gestión de configuración, integración e interfaces de usuario.

🔹 **Principios ágiles (Sommerville):**
| Principio | Significa |
|---|---|
| Participación del cliente | El cliente está involucrado durante todo el desarrollo y prioriza requerimientos |
| Entrega incremental | Se entrega por incrementos y el cliente define qué va en cada uno |
| Personas, no procesos | Se reconocen las habilidades del equipo y se deja que trabaje a su manera |
| Aceptar el cambio | Se espera que los requerimientos cambien y se diseña para acomodarlos |
| Mantener la simplicidad | Simplicidad en el software y en el proceso |

🔹 **Manifiesto Ágil (2001), 4 valores:** *individuos e interacciones* sobre procesos y herramientas · *software funcionando* sobre documentación extensiva · *colaboración con el cliente* sobre negociación de contratos · *respuesta al cambio* sobre seguir un plan.

**¿Dónde funciona mejor ágil?**
1. **Desarrollo de productos** pequeños o medianos para la venta (hoy casi todas las apps).
2. **Sistemas a medida dentro de una organización**, con un cliente comprometido y pocas regulaciones o stakeholders externos.

### Historias de usuario (introducción; se ve a fondo en el Paso 6)
- Ágil **no tiene una actividad de ingeniería de requerimientos separada**: la **integra** con el desarrollo.
- **Historia de usuario** = un **escenario de uso** que podría vivir un usuario. Se escribe en una **story card**.
- El equipo la **divide en tareas** y **estima** esfuerzo y recursos.
- ✅ **A favor:** la gente se identifica más fácilmente con historias que con un documento de requerimientos o casos de uso.
- ❌ **En contra:** el problema principal es la **completitud**. Es difícil saber si hay suficientes historias, si una historia representa bien la actividad, y los usuarios expertos **omiten cosas** porque las dan por obvias.

### Problemas prácticos del ágil
1. Su informalidad **choca con los contratos legales** de las empresas grandes.
2. Es mejor para **desarrollo nuevo** que para **mantenimiento**, y la mayor parte del costo en empresas grandes **es mantenimiento**.
3. Está pensado para **equipos pequeños y en el mismo lugar**, pero hoy los equipos están distribuidos por el mundo.

---

## 8. ¿Ágil o dirigido por plan? (preguntas para decidir) ⭐
> Para escalar ágil hay que **integrarlo con enfoques dirigidos por plan**. Muchas veces la respuesta es un **híbrido**.

| Factor | Pregunta | Si la respuesta es… → tiende a **plan** |
|---|---|---|
| **Sistema** | ¿Qué tan grande es? | Grande, que no cabe en un equipo pequeño en el mismo lugar |
| | ¿Qué tipo de sistema? | Requiere mucho análisis previo (tiempo real con tiempos complejos) |
| | ¿Cuánto vivirá? | Mucho tiempo: hace falta documentación para el equipo de soporte |
| | ¿Tiene regulación externa? | Sí (p.ej., la FAA en aviación): documentación detallada obligatoria |
| **Equipo** | ¿Qué tan buenos son los programadores? | Menos expertos (se dice que ágil exige más habilidad) |
| | ¿Cómo está organizado? | Distribuido o con outsourcing: hacen falta documentos de diseño |
| | ¿Qué tecnologías hay? | Sin buenas herramientas (ágil depende de ellas) |
| **Organización** | ¿Hace falta especificación detallada antes, p.ej. por contrato? | Sí: requerimientos plan-driven, pero se puede implementar con ágil |
| | ¿Es realista la entrega incremental? ¿Hay representante del cliente disponible? | No |
| | ¿Hay temas culturales? | Organización de ingeniería tradicional con cultura de planes y documentación |

---

## 9. ¿Cómo elegir el ciclo de vida? (resumen para el examen) ⭐⭐
| Modelo | Úsalo cuando… |
|---|---|
| **Cascada** | Proyecto pequeño o mediano · requerimientos **bien entendidos** · restricciones de tiempo y costo |
| **Incremental** | Se puede dividir en **mini-proyectos** · **alto riesgo** o **pocos recursos** · requerimientos generales entendidos · tiempo y costo fijables por incremento |
| **Evolutivo** | Requerimientos **inciertos** · la **calidad importa más** que tiempo o costo · equipos pequeños y colaborativos. ❌ No sirve para sistemas **críticos (safety)** ni **regulados** |
| **Híbrido** (iteración controlada) | Proyecto grande con **arquitectura estable**, pero con algo de incertidumbre |
| **Prototipado** | Hay que **aclarar requerimientos** (algoritmos complejos, interfaz), probar la factibilidad en diseño o comparar resultados en pruebas |
| **Concurrente** | El **cronograma es crítico** |
| **Componentes** | **Portafolio de sistemas** en una organización o para venta |
| **Ágil** | Sistemas **pequeños o medianos** con **pocos stakeholders** · **sin contrato fijo** · la **documentación no es importante** |

- **Herramienta de perfil de proyecto de David Boddy:** los proyectos **core** y los que tienen **vínculos externos** tienden a usar ciclos **incrementales** en vez de evolutivos.

### Puntos clave (take away) de la diapositiva final
- **Proceso de software** = actividades para **producir y evolucionar** un sistema.
- **Modelo de proceso** = **representación abstracta** de ese proceso.
- Actividades generales: **especificación, diseño e implementación, validación y evolución**.
- Los modelos **iterativos** describen el proceso como un **ciclo** de actividades.
- **RUP separa actividades de fases.**

---

## ✅ Autotest
<details><summary>1. ¿Por qué se dice que cascada es "plan-driven"?</summary>
Porque todas las actividades se planifican y programan antes de empezar el desarrollo.</details>

<details><summary>2. ¿En qué 3 tipos de sistema conviene cascada?</summary>
Embebidos (por el hardware inflexible), críticos (necesitan análisis de safety y security sobre una especificación completa) y sistemas grandes desarrollados entre varias empresas.</details>

<details><summary>3. ¿Qué relaciona el Modelo V?</summary>
Cada actividad de aseguramiento de calidad (prueba) con su actividad de modelado o especificación correspondiente. El lado izquierdo refina y el derecho valida.</details>

<details><summary>4. ¿Qué es el "producto núcleo" en el modelo incremental?</summary>
El primer incremento: cubre los requerimientos básicos y deja fuera las funciones complementarias. Su uso por parte del cliente alimenta el plan del siguiente incremento.</details>

<details><summary>5. Incremental vs. evolutivo: ¿cuál es la diferencia clave?</summary>
En el incremental el producto general se conoce y se entrega por partes usables. En el evolutivo los requerimientos son inciertos, cada versión es más completa y puede terminar siendo un producto diferente.</details>

<details><summary>6. ¿Cuáles son los dos riesgos del prototipado?</summary>
(i) El cliente cree que el prototipo ya es el producto, sin calidad ni mantenibilidad. (ii) El ingeniero se queda con malas decisiones de implementación que tomó para ir rápido.</details>

<details><summary>7. ¿Qué guía al modelo espiral y cuáles son sus dos rasgos?</summary>
El riesgo (es un generador de modelos guiado por el riesgo). Sus rasgos son el ciclo que aumenta la definición mientras reduce el riesgo, y los hitos de anclaje que aseguran el compromiso de los stakeholders.</details>

<details><summary>8. ¿Cuáles son las 4 actividades de CBSE?</summary>
Análisis de componentes → modificación de requerimientos → diseño con reuso → desarrollo e integración.</details>

<details><summary>9. ¿Cuáles son las fases de RUP y qué lo distingue?</summary>
Inception, Elaboration, Construction y Transition. Lo distingue que separa las actividades de las fases, y es iterativo e incremental.</details>

<details><summary>10. ¿Cuál es el principal problema de las historias de usuario según la clase?</summary>
La completitud: es difícil saber si las historias cubren todos los requerimientos esenciales.</details>

<details><summary>11. ¿Cuáles son los 3 problemas prácticos de ágil?</summary>
Choca con los contratos legales, sirve más para desarrollo nuevo que para mantenimiento, y está pensado para equipos pequeños en el mismo lugar.</details>

<details><summary>12. Caso: software de control para un marcapasos, regulado por la autoridad de salud. ¿Ágil o plan? ¿Por qué?</summary>
Dirigido por plan (cascada o Modelo V). Es un sistema crítico de safety y está regulado externamente, así que exige especificación y documentación completas para el análisis y la certificación.</details>
