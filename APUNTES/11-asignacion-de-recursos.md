# Paso 11: Recursos y scheduling (time-limited vs. resource-limited)
*Fuentes: **transcripción de la Sesión 12** (`Meeting in _General_ .vtt`, clase virtual del lunes 9-nov-2026, Dr. Mera) → [`CLASES/SEMANA-7/TRANSCRIPCION-SESION-12.md`](../CLASES/SEMANA-7/TRANSCRIPCION-SESION-12.md) + diapositivas `07SchedulingandResourceAllocation.pdf` (láminas 24–54).*
*Continúa el [Paso 10](10-gestion-de-proyectos-y-cronogramas.md) (red AoA, forward/backward pass, float, camino crítico). Para practicar: [Paso 12, taller resuelto](12-practica-taller-aoa-recursos.md).*
*Sirve para la **lección del miércoles 11-nov-2026** y para el **examen**.*
*🎤 = lo dijo el profe en clase. 📄 = está en las diapositivas. 🔹 = lo agregué yo para completar. ⚠️ = cuidado, error típico.*

---

## 🎯 Lo que el profe dijo que viene en el examen (Sesión 12)
1. 🎤 **Formato del ejercicio:** *"Me da una tabla de actividades; para cada una me dice su dependencia, la duración y el personal… y en el examen esto es lo que usted va a encontrar."* Luego piden:
   - **(a)** *"Elabore y analice la red de activity-on-arrow"*.
   - **(b)** *"Un gráfico de recursos… el **no alisado** (unsmoothed), que es el original"*.
   - **(c)** *"Que empiece a disminuir la cantidad de recursos pico… aplicando el **smoothing**: mover las actividades de acuerdo a su flotación, manteniendo las precedencias"*.
   - Y lo que más preguntan: 🎤 *"¿Cuál es mi **recurso pico**? Es lo que te preguntan en el examen."*
2. 🎤 **Tamaño de la red:** *"En el examen no son tan grandes… no va a encontrar una red con 17 nodos… usualmente andan de **10 a 12** [nodos], en el peor de los casos."*
3. 🎤 **Personal por actividad:** *"La mayoría son de **1 o 2** personas, una que otra de 3 y, muy raro, una de 4. No se busca complicar el cálculo, sino que usted demuestre que entiende lo que está haciendo."*
4. 🎤 **La convención da puntos:** *"Debe acordarse que **obtiene puntos por colocar la convención**. La convención no se puede olvidar y tiene **cinco elementos**"* (ver §1).
5. 🎤 **Mínimo de dummies:** *"Siempre acordarse que debe tener el **menor número de dummies posible**."* Si la red del examen tiene un dummy de más, pierdes puntos.
6. 🎤 **Time-limited es "el más común en el examen".** Resource-limited: *"Se las voy a dejar para que las revisen con calma en casa"* → **igual entra**; el taller de hoy (Sección B) lo pide.
7. 🎤 Cierre: *"Debo acordarme de las reglas para el time-limited y las reglas para el enfoque resource-limited."*

---

## 1. Repaso rápido de la red AoA (lo que el profe repitió al inicio)
- **Forward pass:** desde el único nodo de inicio (t = 0), sumando duraciones. Si **llegan** varias flechas a un nodo, pon el **MAYOR**.
- **Backward pass:** desde el nodo de fin con la duración máxima del proyecto (si no te dan un plazo, usa la misma que salió del forward pass), restando duraciones. Si **salen** varias flechas de un nodo, pon el **MENOR**.
- **Restricciones de la red:** un **único nodo de inicio** y un **único nodo de fin** · **sin lazos** · **dos actividades no pueden compartir a la vez nodo de inicio Y nodo de fin** · **mínimo número de dummies**.
- **EST** = EET del nodo de inicio · **EFT** = EST + duración · **LST** = LET del nodo de fin − duración · **LFT** = LET del nodo de fin.
- ⭐ **Float total = LET(nodo fin) − EET(nodo inicio) − duración.** 🎤 *"Es lo que me sobra, el tiempo con el que podría jugar."*
- **Camino crítico** = el camino del inicio al fin con **menor** float: 🎤 *"las actividades que, si se atrasan, el proyecto se retrasa."*
- 🎤 La **tabla EST/EFT/LST/LFT/float** "no es obligatoria, pero sí convendría": casi todo se **copia de los nodos**; solo el float se calcula. Con ella justificas el camino crítico *"de forma justificada y no visual, que se pudiese confundir"*.

### ⚠️ Respetar las dependencias EXACTAMENTE
🎤 *"Lo que sí tengo que garantizar es que en el inicio de E solamente voy a poder trazar hacia atrás las actividades C y D. Si usted le pone que a ese nodo llegue A, ya está alterando los requisitos, porque E no puede depender bajo ningún concepto de A."*
→ Al terminar tu red, **verifica cada nodo**: lo que llega a él debe ser **exactamente** la lista de prerrequisitos de lo que sale (ni más ni menos).

### ⭐ La convención (leyenda): 5 elementos que dan puntos 🎤
```
 1. Unidades de tiempo:  semanas  (¡escríbelas!)
 2. ─────────►  actividad normal (letra arriba, duración abajo)
 3. ═════════►  actividad CRÍTICA (en el examen: línea DOBLE, no hay colores)
 4. - - - - ►   actividad dummy (duración 0)
 5. Nodo:  ┌────┬─────┐
           │    │ EET │   N   = número del evento
           │ N  ├─────┤   EET = earliest event time (lo más pronto que se llega
           │    │ LET │         al nodo con TODAS las actividades entrantes terminadas)
           └────┴─────┘   LET = latest event time (lo más tarde que se puede llegar
                                al nodo sin atrasar el proyecto)
```

### Ventajas de la red AoA frente al Gantt (🎤 las repitió)
- **Fechas relativas**: *"me pueden decir que arranca el 14/09/2027 o el 10/11/2026, da lo mismo"*.
- **Dependencias visibles de un vistazo**: *"ya sé que para empezar C deben haberse concluido A y B, en un solo plumazo"*, sin texto adicional.
- **Camino crítico visible** de inmediato.

### ✍️ Ejemplo 5 de las diapositivas (red + mínimo de dummies)
| Act. | Dur (sem) | Depende de | Personas |
|---|---|---|---|
| A | 10 | — | 1 |
| B | 5 | — | 2 |
| C | 10 | A y B | 2 |
| D | 10 | C | 1 |
| E | 5 | C | 1 |

🎤 La red de la diapositiva tiene **4 dummies**; el profe dijo que sobraban 2 (*"podía haber ido directo de 4 a 7 y eliminaba el nodo 6… y acá pude haber hecho que venga directo del nodo cero y eliminaba el nodo 1"*).
**Mínimo = 2 dummies**: uno porque A y B comparten inicio y fin, y otro porque D y E comparten inicio (fin de C) y fin (nodo final).
```
            A (10)            C (10)            D (10)
  (1) ═════════════► (2) ═════════════► (3) ═════════════► (5 FIN)
    \                 ▲                   \                  ▲
     \ B (5)          ┊ dummy              \ E (5)           ┊ dummy
      ──────► (6) ┄┄┄┄┘                     ──────► (4) ┄┄┄┄┄┘
```
- Forward: nodo 2 = max(10, 5) = **10**; nodo 3 = **20**; fin = max(30, 25) = **30 semanas**.
- Backward: 30 → nodo 3 = min(30−10, 30−5) = **20** → nodo 2 = **10** → inicio = min(10−10, 10−5) = **0** ✔.

| Act. | EST | EFT | LST | LFT | Float |
|---|---|---|---|---|---|
| A | 0 | 10 | 0 | 10 | **0** ⭐ |
| B | 0 | 5 | 5 | 10 | 5 |
| C | 10 | 20 | 10 | 20 | **0** ⭐ |
| D | 20 | 30 | 20 | 30 | **0** ⭐ |
| E | 20 | 25 | 25 | 30 | 5 |

**Camino crítico: A → C → D (30 semanas).**

---

## 2. Recursos y scheduling: los dos escenarios
🎤 *"En la mayoría de los proyectos la disponibilidad de recursos es limitada"*: profesionales, **flujo de caja** (*"no se puede gastar todo el presupuesto de varios meses en un solo golpe"*), instalaciones compartidas. Por eso **no siempre conviene programar todo lo más pronto posible**, sino donde se haga **el uso más eficiente de los recursos**.

🎤 **Supuestos del curso** (para simplificar los ejercicios): **todos los recursos son personas** y **las personas son intercambiables** entre actividades (aunque en la vida real no siempre es cierto).

| | **Time-limited scheduling** | **Resource-limited scheduling** |
|---|---|---|
| Qué es fijo | **La fecha de entrega** (🎤 *"me tienes que entregar en 8 meses"*) | **La cantidad de recursos** (🎤 *"solo puedes contar con 4 recursos"*) |
| Qué es flexible | Los recursos (se asumen **ilimitados**) | El **tiempo** (la fecha se puede alargar) |
| Qué puede hacer el PM | Contratar personal, pagar **horas extra**, contratar servicios, rentar instalaciones | **Nada de eso**; solo ser eficiente y entregar en la menor fecha posible |
| Técnica | **Resource smoothing** (nivelar la carga) | **Reglas elementales** (programación en paralelo o serial) |
| Resultado típico | Misma duración, **menor recurso pico** | **Recurso pico ≤ límite**, duración **mayor o igual** |

- 🎤 **Si tienes las dos limitaciones**: *"primero aplicas un enfoque y luego el otro; **no puedes enfrentar a ambos a la vez**. Eso es elemental."* 📄 Busca una solución compatible y, si no la hay, **negocia la factibilidad con el cliente**.
- ⚠️ Nombre: el de **tiempo fijo** es *time-limited*; el de **recursos fijos** es *resource-limited*. No los cruces.

---

## 3. Time-limited scheduling (resource smoothing) ⭐ el más común
**Objetivos** 📄: (1) calcular los recursos necesarios para que **estén disponibles en el momento indicado**; (2) programar cada actividad para que la carga sea **lo más nivelada posible** → **resource smoothing**.

🎤 **La analogía del Tetris:** *"Las tareas las tienes que ir acomodando de tal manera que siempre lo de abajo esté compacto, y arriba puede haber algún espacio."* El gráfico debe parecer un **histograma** relleno de abajo hacia arriba.

### Los 6 pasos (📄, memorízalos)
1. Elaborar el **diagrama de red**.
2. Elaborar una **tabla** con, por actividad: **personas, duración, EST, float y LFT**. 🎤 *"Si no quiere estar yendo a ver el diagrama, pues se puede confundir, lo pone en una tablita."*
3. **Ordenar las actividades por float creciente**; si empatan en float, **por LFT creciente**.
4. Graficar el **resource loading chart inicial** (*unsmoothed*) con **cada actividad en su EST** → las **críticas abajo** y las de **más float arriba**.
5. **Mover actividades dentro de su float** (hacia la derecha) para **nivelar** (**bajar el recurso pico**), sin cambiar duraciones y **sin romper dependencias**.
6. Usar el **criterio**: replantear dependencias, considerar **horas extra en el pico**.

### Por qué mira cada columna (🎤)
| Columna | Para qué sirve |
|---|---|
| **EST** | El gráfico inicial se dibuja con todas las actividades en su **EST** (no en su LST) |
| **Float** | Cuánto puedes **mover la actividad a la derecha** sin atrasar el proyecto |
| **LFT** | El límite que **no puedes pasar** o se atrasa el proyecto |
| **Duración** | Si dos tienen float parecido, la **más larga va más abajo** (bloque más compacto) |

### ⚠️ Reglas del gráfico de carga (🎤 "ojo, ese es un punto en el que me tienen que poner atención")
- **El camino crítico va SIEMPRE abajo.** 🎤 *"Si yo pongo la A arriba de C, está mal ya, porque el gráfico tiene que verse relleno, compacto de abajo hacia arriba."*
- **Más float y menor duración → más arriba.**
- **Una actividad NO se interrumpe.** 🎤 *"Una vez que una actividad se empieza, se avanza hasta el final; no se la puede dejar a medias… no pudiese poner un pedacito de C por acá y otro por acá."*
  - Lo que **sí** se permite: que el bloque de una actividad se dibuje en **dos cajitas apiladas a distinta altura** si es **continuo en el tiempo** (C de la semana 8 a la 13, aunque se vea en 2 cajas).
- **Respeta las dependencias** igual que en la red (si E depende de D, E va después de D también en el gráfico).
- Eje X = **tiempo (con unidades)**, eje Y = **número de personas**. Escribe la **letra** de cada actividad en su bloque.

### ✍️ Ejemplo de clase: instalación de oficinas (📄 Tabla 3.5 + 🎤)
Es la misma red del Ejemplo 3 del Paso 10 (camino crítico A → D → E, 32 semanas), ahora con personal.

| Act. | Descripción | Personas | Duración | EST | Float | LFT | Orden (paso 3) |
|---|---|---|---|---|---|---|---|
| A | preparar oficinas | 2 | 12 | 0 | 0 | 12 | 1 |
| D | instalar equipos (dep. A, B) | **4** | 10 | 12 | 0 | 22 | 2 |
| E | probar sistema (dep. C, D) | 3 | 10 | 22 | 0 | 32 | 3 |
| B | adquirir equipos | 2 | 8 | 0 | 4 | 12 | 4 |
| F | capacitar usuarios (dep. A, B) | 1 | 5 | 12 | 15 | 32 | 5 |
| C | diseñar pruebas | 1 | 5 | 0 | 17 | 22 | 6 |

Los números de la columna "orden" son los que aparecen en la esquina de cada bloque en la Figura 3.28: **float creciente y, si empatan, LFT creciente**. Ese es el orden en que se apilan, de abajo hacia arriba.

**Gráfico inicial (unsmoothed), todas en su EST:**
*(En todos los gráficos de estos apuntes: 1 carácter = 1 semana; eje Y = personas.)*
```
  5 ┤CCCCC       FFFFF
  4 ┤BBBBBBBB    DDDDDDDDDD
  3 ┤BBBBBBBB    DDDDDDDDDDEEEEEEEEEE
  2 ┤AAAAAAAAAAAADDDDDDDDDDEEEEEEEEEE
  1 ┤AAAAAAAAAAAADDDDDDDDDDEEEEEEEEEE
    └────────────────────────────────► semanas
     0    5    10   15   20   25   30
```
| Semanas | 0–5 | 5–8 | 8–12 | 12–17 | 17–22 | 22–32 |
|---|---|---|---|---|---|---|
| Carga | **5** (A+B+C) | 4 | 2 | **5** (D+F) | 4 | 3 |

→ **Recurso pico = 5 personas**, en dos tramos (semanas 0–5 y 12–17).
⚠️ En la grabación el profe dice "de la semana 0 a la 4", pero C dura 5 semanas desde t = 0, así que el primer tramo de 5 personas va de **0 a 5**.

**Smoothing (🎤 lo que hizo en clase):**
1. **Mover C** (float 17) para que **empiece cuando termina B**, en la semana **8 → 13**. 🎤 *"Al desplazar C, al arranque del proyecto ya no necesita 5 recursos… no altera dependencias ni atrasa el proyecto."* C es continuo de 8 a 13 aunque se dibuje en dos cajas (encima de A de 8 a 12, y encima de D de 12 a 13).
2. **Mover F** (float 15, nadie depende de F, puede empezar entre t = 12 y t = 27) para ponerlo **encima de E**, en las semanas **22 → 27**. 🎤 *"F se va de aquí hasta el final… la puedo empezar en t = 12 o en t = 27 y no pasa nada."*

```
  5 ┤            C                     ← el pico de 5 dura solo 1 semana (12–13)
  4 ┤BBBBBBBB    DDDDDDDDDDFFFFF
  3 ┤BBBBBBBBCCCCDDDDDDDDDDEEEEEEEEEE
  2 ┤AAAAAAAAAAAADDDDDDDDDDEEEEEEEEEE
  1 ┤AAAAAAAAAAAADDDDDDDDDDEEEEEEEEEE
    └────────────────────────────────► semanas
     0    5    10   15   20   25   30
```
| Semanas | 0–8 | 8–12 | 12–13 | 13–22 | 22–27 | 27–32 |
|---|---|---|---|---|---|---|
| Carga | 4 | 3 | **5** | 4 | 4 (E+F) | 3 |

→ 🎤 *"El recurso pico sigue siendo 5, pero **ya solamente durante una semana**, de la 12 a la 13."*
🔹 **¿Por qué no se puede bajar a 4?** C (5 semanas, 1 persona) tiene que caber entero **antes de la semana 22** (LFT). De 0 a 8 la carga ya es 4 (A + B); de 8 a 12 hay un hueco de 3, pero solo de 4 semanas; y de 12 a 22, D ya usa 4 personas. No existe una ventana de 5 semanas seguidas con carga ≤ 3, así que con las reglas del paso 5 el pico mínimo es 5. Para bajarlo habría que aplicar el paso 6: horas extra esa semana, o replantear una dependencia.
🎤 *"Habrá casos en los que usted no pueda hacer nada para modificar el recurso pico, y otros en los que sí."*

### ✍️ Ejemplo 3 de las diapositivas (pico que NO se puede reducir)
Mismos datos del Ejemplo 5 (A 10 sem/1 p, B 5/2 p, C 10/2 p dep. A y B, D 10/1 p dep. C, E 5/1 p dep. C).
```
  3 ┤BBBBB
  2 ┤BBBBB     CCCCCCCCCCEEEEE
  1 ┤AAAAAAAAAACCCCCCCCCCDDDDDDDDDD
    └──────────────────────────────► semanas
     0    5    10   15   20   25   30
```
- **¿Recurso pico?** **3** personas (semanas 0–5).
- **¿Se puede reducir?** 📄 **No.** *"B tiene float de 5; moverlo dentro de su float no cambia el pico de 3, porque A ocupa 1 persona durante todo el intervalo 0–10. No se puede reducir el pico sin alterar las actividades o extender la duración del proyecto."*
- **¿Qué más podrías hacer?** 🔹 Extender el proyecto (pasar a **resource-limited**: con 2 personas dura **35** semanas, ver §4), pagar horas extra en el pico, o replantear si B de verdad necesita 2 personas.

### 🔹 Truco para justificar el pico mínimo (suma rápida de persona-semanas)
**Pico mínimo ≥ (Σ personas × duración) ÷ duración del proyecto** (redondeado hacia arriba).
Ej. oficinas: 2·12 + 2·8 + 1·5 + 4·10 + 3·10 + 1·5 = **120 persona-semanas** ÷ 32 = 3.75 → el pico nunca bajará de **4**. Además, ninguna actividad puede tener menos personas de las que pide (D necesita 4), así que el pico tampoco baja del mayor "personas" de la tabla. Sirve para **explicar** tu respuesta en el literal (c), que pide justificar.

---

## 4. Resource-limited scheduling (reglas elementales)
📄 Es el punto de vista opuesto: **se ajusta la asignación de recursos a un límite fijo**. A diferencia del time-limited, usa un **conjunto elemental de reglas** (un algoritmo).

- **Parallel scheduling** (programación en paralelo): en cada instante se consideran **todas las actividades elegibles a la vez**. Es la que se usa en los ejemplos.
- **Serial scheduling** (programación serial): se considera **cada actividad en un orden predefinido**, por ejemplo float creciente.
- **Actividad elegible** = sus predecesoras **ya terminaron** y todavía no ha empezado.

### Las 4 reglas ⭐ (memorízalas: el profe dijo "debo acordarme de las reglas")
| Regla | Enunciado |
|---|---|
| **1** | Entre las elegibles, elige primero la de **LST más temprano**. Empate → la de **menor duración**. Si sigue el empate → por ejemplo, la que **más recursos** requiere. |
| **2** | Una actividad iniciada **continúa hasta terminar** (**no se interrumpe**). |
| **3** | **Nunca dejar un recurso ocioso** si hay una actividad elegible que puede iniciarse. |
| **4** | Una actividad **no puede iniciarse con recursos parciales**. |

### El algoritmo (🎤 "y ahí pregunta y pregunta y pregunta")
1. Empieza en t = 0 con todas las personas libres.
2. Lista las actividades **elegibles ordenadas por LST** (regla 1).
3. Para cada una: si alcanzan las personas libres → **aceptar** (restar personas); si no → **"personas insuficientes"** (regla 4) y sigue con la siguiente de la lista (regla 3: si una más pequeña cabe, entra).
4. Salta al **siguiente instante en que se liberen recursos** (cuando termina alguna actividad) y repite.
5. La duración nueva = cuando termina la última actividad. **Dibuja el resource loading chart** con el resultado.

Haz siempre la **tabla del algoritmo**; en el taller la piden ("muestre todo su trabajo"):

| Tiempo | Personas libres | Elegible (orden LST) | Personas | LST | Comentario |
|---|---|---|---|---|---|

### ✍️ Ejemplo de clase: oficinas con límite de 4 personas (📄 Tabla 3.8)
LST: A 0, B 4, D 12, C 17, E 22, F 27.

| Tiempo | Libres | Elegible | Pers. | LST | Comentario |
|---|---|---|---|---|---|
| 0 | 4 | A | 2 | 0 | aceptar (regla 1) → quedan 2 |
| | 2 | B | 2 | 4 | aceptar → quedan 0 |
| | 0 | C | 1 | 17 | personas insuficientes |
| 8 (termina B) | 2 | C | 1 | 17 | aceptar (C: 8–13) |
| 12 (termina A) | 3 | D | 4 | 12 | personas insuficientes (regla 4) |
| | 3 | F | 1 | 27 | aceptar (regla 3: no dejar gente ociosa) (F: 12–17) |
| 13 (termina C) | 3 | D | 4 | 12 | personas insuficientes |
| 17 (termina F) | 4 | D | 4 | 12 | aceptar (D: 17–27) |
| 27 (termina D) | 4 | E | 3 | 22 | aceptar (E: 27–37) |

```
  4 ┤BBBBBBBB         DDDDDDDDDD
  3 ┤BBBBBBBBCCCC     DDDDDDDDDDEEEEEEEEEE
  2 ┤AAAAAAAAAAAAC    DDDDDDDDDDEEEEEEEEEE
  1 ┤AAAAAAAAAAAAFFFFFDDDDDDDDDDEEEEEEEEEE
    └─────────────────────────────────────► semanas
     0    5    10   15   20   25   30   35
```
→ Duración **37 semanas** (5 más que las 32 sin límite); pico = 4 ✔.
🔹 **Lección importante:** las reglas son **heurísticas, no óptimas**. Por la regla 3, F se metió en la semana 12 y eso retrasó a D hasta la 17. La Figura 3.31 de las diapositivas muestra que, **usando el criterio** (esperar a que termine C y arrancar D en la 13, con F encima de E), el proyecto termina en **33 semanas** con el mismo límite de 4. Si te preguntan "¿se puede mejorar?", esto es lo que hay que comentar.
```
  4 ┤BBBBBBBB     DDDDDDDDDDFFFFF
  3 ┤BBBBBBBBCCCC DDDDDDDDDDEEEEEEEEEE
  2 ┤AAAAAAAAAAAA DDDDDDDDDDEEEEEEEEEE
  1 ┤AAAAAAAAAAAACDDDDDDDDDDEEEEEEEEEE      (C sigue siendo continua: 8–13)
    └─────────────────────────────────► semanas
     0    5    10   15   20   25   30
```

### ✍️ Ejemplo 5 de las diapositivas: límite de 2 personas
LST: A 0, B 5, C 10, D 20, E 25.

| Tiempo | Libres | Elegible | Pers. | LST | Comentario |
|---|---|---|---|---|---|
| 0 | 2 | A | 1 | 0 | aceptar (regla 1) |
| | 1 | B | 2 | 5 | personas insuficientes (regla 4) |
| 10 | 2 | B | 2 | 5 | aceptar (B: 10–15) |
| 15 | 2 | C | 2 | 10 | aceptar (C: 15–25) |
| 25 | 2 | D | 1 | 20 | aceptar (D: 25–35) |
| | 1 | E | 1 | 25 | aceptar (E: 25–30) |

```
  2 ┤          BBBBBCCCCCCCCCCEEEEE
  1 ┤AAAAAAAAAABBBBBCCCCCCCCCCDDDDDDDDDD
    └───────────────────────────────────► semanas
     0    5    10   15   20   25   30   35
```
→ 📄 *"After resource-limited scheduling: reducing peak to 2."* La duración pasa de **30 a 35 semanas**. Compáralo con el Ejemplo 3 de §3: con time-limited el pico de 3 **no** se podía bajar; con resource-limited **sí**, pero a costa de **5 semanas más**. Esa es la diferencia entre los dos enfoques.

---

## 5. 📋 Receta para el examen (de principio a fin)
1. **Red AoA**: dibuja, revisa nodo por nodo que las dependencias sean exactas y **elimina los dummies sobrantes** (pregúntate en cada dummy: ¿podría conectar la flecha directo sin que dos actividades compartan inicio y fin, y sin crear una dependencia falsa?).
2. **Forward pass** (MAYOR) → **backward pass** (MENOR), usando el **plazo** si el enunciado da uno (por ejemplo, "debe completarse en 45 semanas" → LET del nodo final = 45).
3. **Tabla**: personas, duración, EST, EFT, LST, LFT, float. Marca el **camino crítico** con **línea doble**.
4. **Convención (5 elementos)**: unidades, actividad normal, crítica, dummy y compartimentos del nodo.
5. **Unsmoothed**: ordena por float (y LFT), apila de abajo hacia arriba en el EST. Escribe la **tabla de carga por tramo** e indica el **recurso pico y en qué semanas** ocurre.
6. **Smoothing**: mueve solo actividades con float, sin interrumpirlas y sin romper dependencias, para tapar los huecos. Da el **nuevo pico** y **justifica** (por ejemplo, con la suma de persona-semanas o explicando por qué ninguna actividad cabe en otro hueco).
7. **Resource-limited** (si lo piden): tabla tiempo / libres / elegibles por LST / comentario con número de regla → **nueva duración** → redibuja el gráfico.

---

## 🧠 Autotest (respuestas abajo, tápalas)
1. ¿Qué es fijo y qué es flexible en time-limited scheduling? ¿Y en resource-limited?
2. ¿Qué puede hacer el PM en time-limited que no puede hacer en resource-limited?
3. ¿Qué haces si un proyecto tiene limitaciones de tiempo **y** de recursos?
4. ¿Cómo se llama la técnica de nivelar la carga en time-limited?
5. Los 6 pasos del time-limited scheduling.
6. ¿En qué orden se apilan las actividades en el gráfico inicial? ¿Qué va abajo?
7. ¿En qué tiempo se dibuja cada actividad en el gráfico inicial: EST o LST?
8. ¿Se puede partir una actividad en dos pedazos separados en el tiempo?
9. Las 4 reglas del resource-limited scheduling.
10. Diferencia entre parallel y serial scheduling.
11. En el ejemplo de oficinas, ¿cuál es el pico inicial, cuál es el pico después del smoothing y cuánto dura ese pico?
12. ¿Cuántos elementos tiene la convención y cuáles son?
13. ¿Por qué el resource-limited con 4 personas da 37 semanas si con criterio se puede hacer en 33?
14. ¿Cuántos nodos tiene, como máximo, una red típica de examen?

<details><summary>Respuestas</summary>

1. Time-limited: la fecha de entrega es fija y los recursos se consideran ilimitados. Resource-limited: los recursos son fijos y la fecha puede alargarse.
2. Contratar personal adicional, pagar horas extra, contratar servicios y rentar instalaciones.
3. Aplicar primero un enfoque y luego el otro (nunca los dos a la vez), buscando una solución compatible; si no la hay, negociar con el cliente.
4. Resource smoothing.
5. (1) Red; (2) tabla con personas, duración, EST, float y LFT; (3) ordenar por float creciente (empate → LFT); (4) gráfico inicial con todo en su EST; (5) mover actividades dentro de su float para nivelar sin cambiar duraciones ni dependencias; (6) usar el criterio (replantear dependencias, horas extra en el pico).
6. Por float creciente (empate → LFT). El camino crítico va abajo; más float y menor duración van más arriba.
7. En su EST.
8. No. Una vez que empieza, sigue hasta terminar. Solo se permite dibujarla en dos cajas apiladas si es continua en el tiempo.
9. (1) Elegir la de menor LST (empate → menor duración → más recursos); (2) no interrumpir; (3) no dejar recursos ociosos si hay una elegible que pueda empezar; (4) no iniciar con recursos parciales.
10. Parallel: considera todas las elegibles a la vez en cada instante. Serial: considera cada actividad en un orden predefinido (por ejemplo, float creciente).
11. Pico inicial = 5 (semanas 0–5 y 12–17). Después del smoothing (C a 8–13 y F a 22–27) = 5, pero solo durante 1 semana (12–13).
12. Cinco: unidades de tiempo, actividad normal, actividad crítica (línea doble), actividad dummy y convención del nodo (N, EET, LET).
13. Porque las reglas son heurísticas: la regla 3 obliga a meter F en la semana 12, lo que retrasa a D. Con criterio, D espera una semana y empieza en la 13.
14. Entre 10 y 12 nodos, según el profe.
</details>
