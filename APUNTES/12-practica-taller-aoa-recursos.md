# Paso 12: Práctica. Taller de Resources and Scheduling (resuelto)
*Fuente: [`Tareas/TallerActivityOnArrow-2.0.pdf`](../Tareas/TallerActivityOnArrow-2.0.pdf), el taller de la Sesión 12 (lunes 9-nov-2026). 🎤 El profe dijo que **el examen trae exactamente este formato**: tabla → red AoA → gráfico unsmoothed → smoothing → (resource-limited).*
*Teoría: [Paso 10](10-gestion-de-proyectos-y-cronogramas.md) (red, float, camino crítico) y [Paso 11](11-asignacion-de-recursos.md) (time-limited / resource-limited).*

> **Cómo usar este archivo:** copia el enunciado, **resuélvelo a mano en papel** (con la convención de 5 elementos y línea doble) y solo después abre las soluciones. Los resultados se verificaron con un script (forward/backward pass, cargas por semana y algoritmo de resource-limited).
> En los gráficos: 1 carácter = 1 semana; eje Y = personas.

---

## Sección A

| Actividad | Duración (semanas) | Personal | Depende de |
|---|---|---|---|
| A | 10 | 2 | ninguna |
| B | 5 | 1 | ninguna |
| C | 10 | 2 | A |
| D | 5 | 1 | B |
| E | 10 | 1 | C |
| F | 20 | 1 | C y D |
| G | 5 | 1 | E |
| H | 10 | 1 | E |

**a.** [30 %] Elabore y analice completamente una red activity-on-arrow, **asumiendo que el proyecto debe completarse en 45 semanas**. Use las convenciones de nodos de clase, un único nodo de inicio y un único nodo de fin, el **mínimo número de dummies** (cada actividad identificable de forma única por sus nodos) y una **clave** con el significado de los compartimentos del nodo.
**b.** [10 %] Elabore el gráfico de carga de recursos **unsmoothed** (cada actividad en su EST; personas intercambiables). ¿Cuál es el **pico de recurso antes del smoothing**?
**c.** [10 %] Si las 45 semanas no se pueden exceder, ¿cuál es el **pico de recurso después del smoothing**? **Explique cómo llega a su conclusión.**

<details><summary>✅ Solución A.a: red AoA</summary>

**Mínimo de dummies = 2** (el dibujo es orientativo; la **tabla de flechas** es la referencia exacta):
- **Dummy 4→5:** F depende de **C y D**, pero E depende **solo de C**. Si D llegara al nodo donde termina C, E heredaría una dependencia falsa de D. Por eso C termina en el nodo 4 (de donde sale E) y un dummy lleva al nodo 5, al que también llega D y del que sale F.
- **Dummy 7→8:** G y H salen ambas del nodo 6 (fin de E) y ambas terminan en el nodo final → compartirían inicio y fin.

```
              A (10)            C (10)            E (10)            H (10)
  (1) ═══════════════► (2) ═══════════════► (4) ═══════════════► (6) ═══════════════► (8 FIN)
    \                                         ┋                     \                  ▲  ▲
     \ B (5)                                  ┋ dummy (0)            \ G (5)           ┊  ║
      ─────────► (3) ──── D (5) ────► (5) ◄┅┅┅┛                       ──────► (7) ┄┄┄┄┄┘  ║
                                       ║                              dummy (0)            ║
                                       ╚═══════════════════ F (20) ════════════════════════╝
  Convención: ═══ crítica (línea doble) · ─── normal · ┄┄ dummy · ┅┅ dummy crítico · unidades: semanas
```

| Flecha | Nodos | Duración |
|---|---|---|
| A | 1 → 2 | 10 |
| B | 1 → 3 | 5 |
| C | 2 → 4 | 10 |
| D | 3 → 5 | 5 |
| dummy | 4 → 5 | 0 |
| E | 4 → 6 | 10 |
| F | 5 → 8 | 20 |
| G | 6 → 7 | 5 |
| dummy | 7 → 8 | 0 |
| H | 6 → 8 | 10 |

**Forward pass (EET):** 1 = 0 · 2 = 10 · 3 = 5 · 4 = 20 · 5 = max(20 + 0, 5 + 5) = **20** · 6 = 30 · 7 = 35 · 8 = max(20 + 20, 35 + 0, 30 + 10) = **40**.
→ El proyecto **podría** terminar en 40, pero el enunciado da **45**, así que el backward pass arranca en **LET(8) = 45**.

**Backward pass (LET):** 8 = 45 · 7 = 45 · 6 = min(45 − 5, 45 − 10) = **35** · 5 = 45 − 20 = **25** · 4 = min(35 − 10, 25 − 0) = **25** · 3 = 25 − 5 = **20** · 2 = 25 − 10 = **15** · 1 = min(15 − 10, 20 − 5) = **5**.
⚠️ **El LET del nodo de inicio da 5, no 0.** Eso es correcto cuando hay un plazo mayor que la duración mínima: **todo** el proyecto tiene 5 semanas de holgura. No es un error.

| Nodo | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
|---|---|---|---|---|---|---|---|---|
| EET | 0 | 10 | 5 | 20 | 20 | 30 | 35 | 40 |
| LET | 5 | 15 | 20 | 25 | 25 | 35 | 45 | 45 |

| Act. | Pers. | Dur | EST | EFT | LST | LFT | Float |
|---|---|---|---|---|---|---|---|
| A | 2 | 10 | 0 | 10 | 5 | 15 | **5** ⭐ |
| B | 1 | 5 | 0 | 5 | 15 | 20 | 15 |
| C | 2 | 10 | 10 | 20 | 15 | 25 | **5** ⭐ |
| D | 1 | 5 | 5 | 10 | 20 | 25 | 15 |
| E | 1 | 10 | 20 | 30 | 25 | 35 | **5** ⭐ |
| F | 1 | 20 | 20 | 40 | 25 | 45 | **5** ⭐ |
| G | 1 | 5 | 30 | 35 | 40 | 45 | 10 |
| H | 1 | 10 | 30 | 40 | 35 | 45 | **5** ⭐ |

**Camino crítico** (el de **menor** float, 5; no hay ninguno con 0 porque hay plazo extra): hay **dos**:
- **A → C → E → H** (40 semanas)
- **A → C → (dummy 4→5) → F** (40 semanas)
</details>

<details><summary>✅ Solución A.b: gráfico unsmoothed</summary>

Orden de apilado (float creciente, empate → LFT): A (5, 15) · C (5, 25) · E (5, 35) · F (5, 45) · H (5, 45) · G (10, 45) · B (15, 20) · D (15, 25).
```
  3 ┤BBBBBDDDDD                    GGGGG
  2 ┤AAAAAAAAAACCCCCCCCCCFFFFFFFFFFHHHHHHHHHH
  1 ┤AAAAAAAAAACCCCCCCCCCEEEEEEEEEEFFFFFFFFFF
    └─────────────────────────────────────────────► semanas
     0    5    10   15   20   25   30   35   40   45
```
| Semanas | 0–10 | 10–30 | 30–35 | 35–40 | 40–45 |
|---|---|---|---|---|---|
| Carga | **3** | 2 | **3** | 2 | 0 |

→ **Pico antes del smoothing = 3 personas** (semanas 0–10 y 30–35).
</details>

<details><summary>✅ Solución A.c: smoothing y justificación</summary>

**Respuesta: el pico sigue siendo 3**, pero se puede reducir **cuánto tiempo dura** (de 15 semanas a solo 5).

**¿Por qué no puede bajar a 2? (justificación pedida):**
Total de trabajo = 2·10 + 1·5 + 2·10 + 1·5 + 1·10 + 1·20 + 1·5 + 1·10 = **95 persona-semanas**.
Con un pico de 2 personas durante 45 semanas caben como máximo 2 × 45 = **90** < 95 → **imposible**. Hacen falta al menos 95 − 90 = **5 persona-semanas extra**, es decir, **mínimo 5 semanas con 3 personas**.

**Smoothing paso a paso** (moviendo solo dentro del float y sin romper dependencias):
1. **G** (float 10): de 30–35 a **40–45** → desaparece el pico de 30–35. Ahora el pico de 3 solo ocurre en las semanas 0–10.
```
  3 ┤BBBBBDDDDD
  2 ┤AAAAAAAAAACCCCCCCCCCFFFFFFFFFFHHHHHHHHHH
  1 ┤AAAAAAAAAACCCCCCCCCCEEEEEEEEEEFFFFFFFFFFGGGGG
    └─────────────────────────────────────────────► semanas
     0    5    10   15   20   25   30   35   40   45
```
2. Para quitar D de las semanas 5–10: **D** (float 15, LFT 25) pasa a **20–25**, encima de E. Como F depende de D, **F** (float 5) pasa a **25–45**. Para que no se junten F + G + H, **G** vuelve a **30–35** y **H** (float 5) pasa a **35–45**.
```
  3 ┤BBBBB
  2 ┤AAAAAAAAAACCCCCCCCCCDDDDDFFFFFGGGGGHHHHHHHHHH
  1 ┤AAAAAAAAAACCCCCCCCCCEEEEEEEEEEFFFFFFFFFFFFFFF
    └─────────────────────────────────────────────► semanas
     0    5    10   15   20   25   30   35   40   45
```
| Semanas | 0–5 | 5–20 | 20–25 | 25–30 | 30–35 | 35–45 |
|---|---|---|---|---|---|---|
| Carga | **3** (A+B) | 2 | 2 (E+D) | 2 (E+F) | 2 (F+G) | 2 (F+H) |

Verificación de dependencias: D (20–25) después de B (0–5) ✔ · F (25–45) después de C (20) y D (25) ✔ · G (30–35) y H (35–45) después de E (30) ✔ · todo termina en 45 ✔.

→ **Pico después del smoothing = 3, solo durante 5 semanas (0–5)**. Es el **óptimo**, porque coincide con el mínimo de 5 semanas a 3 personas que exige la cuenta de persona-semanas.
🔹 **Comentario que suma puntos:** en la versión final, F y H consumieron todo su float. Ahora **cualquier retraso en D, F o H atrasa el proyecto** (hay más actividades críticas). Nivelar recursos **cuesta holgura**. Si se prefiere conservar holgura, la versión del paso 1 (pico de 3 durante 0–10) también es válida.
</details>

---

## Sección B

| Actividad | Duración (semanas) | Personal | Dependencia en |
|---|---|---|---|
| A | 5 | 2 | ninguna |
| B | 10 | 1 | ninguna |
| C | 15 | 1 | ninguna |
| D | 10 | 2 | B |
| E | 5 | 2 | A y B |
| F | 5 | 1 | D y E |
| G | 10 | 1 | D y E |
| H | 10 | 1 | A y B |

**a.** [20 %] Diagrame una red activity-on-arrow completa, asumiendo que el proyecto debe terminarse **en el menor tiempo posible** (mismas condiciones: convenciones, nodo único de inicio y fin, mínimo de dummies, clave del nodo).
**b.** [10 %] Produzca el **resource loading chart inicial** con las reglas de **time-limited scheduling** (cada actividad en su EST; la duración de (a) no se puede exceder; personas intercambiables). ¿Cuál es el **pico de recursos**?
**c.** [20 %] Al Jefe de Proyecto le dan un **límite de 3 recursos**. Use las reglas de **resource-limited scheduling** para calcular el tiempo requerido. **Muestre todo su trabajo** y redibuje el gráfico. ¿Cuál es la **nueva duración**?

<details><summary>✅ Solución B.a: red AoA</summary>

**Mínimo de dummies = 2** (el dibujo es orientativo; la **tabla de flechas** es la referencia exacta):
- **Dummy 2→3:** D depende **solo de B**, pero E y H dependen de **A y B**. B termina en el nodo 2 (de donde sale D) y un dummy lleva al nodo 3, al que llega A y del que salen E y H.
- **Dummy 5→6:** F y G salen ambas del nodo 4 (D y E terminadas) y terminan en el nodo final.
- C no depende de nadie y nadie depende de C: va **directo del nodo 1 al nodo final** (no comparte el par inicio-fin con nadie, así que no necesita dummy).

```
              B (10)               D (10)               G (10)
  (1) ═══════════════► (2) ═══════════════► (4) ═══════════════► (6 FIN)
   │ \                  ┊                   ▲  \                  ▲  ▲  ▲
   │  \ A (5)           ┊ dummy (0)         │   \ F (5)           ┊  │  │
   │   ──────────────► (3) ──── E (5) ──────┘    ──────► (5) ┄┄┄┄┄┘  │  │
   │                    \                                 dummy (0)  │  │
   │                     ─────────────────── H (10) ─────────────────┘  │
   └─────────────────────────────────── C (15) ─────────────────────────┘
  Convención: ═══ crítica (línea doble) · ─── normal · ┄┄ dummy · unidades: semanas
```

| Flecha | Nodos | Duración |
|---|---|---|
| B | 1 → 2 | 10 |
| A | 1 → 3 | 5 |
| C | 1 → 6 | 15 |
| dummy | 2 → 3 | 0 |
| D | 2 → 4 | 10 |
| E | 3 → 4 | 5 |
| H | 3 → 6 | 10 |
| F | 4 → 5 | 5 |
| dummy | 5 → 6 | 0 |
| G | 4 → 6 | 10 |

**Forward:** 1 = 0 · 2 = 10 · 3 = max(0 + 5, 10 + 0) = **10** · 4 = max(10 + 10, 10 + 5) = **20** · 5 = 25 · 6 = max(20 + 10, 25 + 0, 10 + 10, 0 + 15) = **30**.
**Backward** ("menor tiempo posible" → LET(6) = 30): 6 = 30 · 5 = 30 · 4 = min(30 − 10, 30 − 5) = **20** · 3 = min(20 − 5, 30 − 10) = **15** · 2 = min(20 − 10, 15 − 0) = **10** · 1 = min(10 − 10, 15 − 5, 30 − 15) = **0** ✔.

| Nodo | 1 | 2 | 3 | 4 | 5 | 6 |
|---|---|---|---|---|---|---|
| EET | 0 | 10 | 10 | 20 | 25 | 30 |
| LET | 0 | 10 | 15 | 20 | 30 | 30 |

| Act. | Pers. | Dur | EST | EFT | LST | LFT | Float |
|---|---|---|---|---|---|---|---|
| A | 2 | 5 | 0 | 5 | 10 | 15 | 10 |
| B | 1 | 10 | 0 | 10 | 0 | 10 | **0** ⭐ |
| C | 1 | 15 | 0 | 15 | 15 | 30 | 15 |
| D | 2 | 10 | 10 | 20 | 10 | 20 | **0** ⭐ |
| E | 2 | 5 | 10 | 15 | 15 | 20 | 5 |
| F | 1 | 5 | 20 | 25 | 25 | 30 | 5 |
| G | 1 | 10 | 20 | 30 | 20 | 30 | **0** ⭐ |
| H | 1 | 10 | 10 | 20 | 20 | 30 | 10 |

**Camino crítico: B → D → G = 30 semanas.**
</details>

<details><summary>✅ Solución B.b: loading chart inicial (time-limited)</summary>

Orden (float creciente, empate → LFT): B (0, 10) · D (0, 20) · G (0, 30) · E (5, 20) · F (5, 30) · A (10, 15) · H (10, 30) · C (15, 30).
```
  6 ┤          CCCCC
  5 ┤          HHHHH
  4 ┤CCCCC     EEEEE
  3 ┤AAAAA     EEEEEHHHHH
  2 ┤AAAAACCCCCDDDDDDDDDDFFFFF
  1 ┤BBBBBBBBBBDDDDDDDDDDGGGGGGGGGG
    └──────────────────────────────► semanas
     0    5    10   15   20   25   30
```
| Semanas | 0–5 | 5–10 | 10–15 | 15–20 | 20–25 | 25–30 |
|---|---|---|---|---|---|---|
| Carga | 4 | 2 | **6** (C+D+E+H) | 3 | 2 | 1 |

→ **Pico inicial = 6 personas (semanas 10–15).**

🔹 **Extra (por si en el examen piden también el smoothing):** E necesita A y B (termina en 10) y debe acabar antes de 20 (LFT), así que **siempre coincide con D** (2 + 2 = 4). Por eso el pico **no puede bajar de 4**. Se consigue moviendo **E a 15–20** y **H a 20–30** (C se queda en 0–15):
```
  4 ┤CCCCC          EEEEE
  3 ┤AAAAA     CCCCCEEEEEHHHHH
  2 ┤AAAAACCCCCDDDDDDDDDDFFFFFHHHHH
  1 ┤BBBBBBBBBBDDDDDDDDDDGGGGGGGGGG
    └──────────────────────────────► semanas
     0    5    10   15   20   25   30
```
Carga: 0–5 = 4 · 5–10 = 2 · 10–15 = 3 · 15–20 = 4 · 20–25 = 3 · 25–30 = 2 → **pico 4**, sin cambiar los 30 semanas.
</details>

<details><summary>✅ Solución B.c: resource-limited con 3 personas</summary>

LST (de la tabla de B.a): B 0 · A 10 · D 10 · C 15 · E 15 · G 20 · H 20 · F 25.

| Tiempo | Libres | Elegible (orden LST) | Pers. | LST | Comentario |
|---|---|---|---|---|---|
| 0 | 3 | B | 1 | 0 | aceptar (regla 1) → quedan 2 |
| | 2 | A | 2 | 10 | aceptar → quedan 0 |
| | 0 | C | 1 | 15 | personas insuficientes (regla 4) |
| 5 (termina A) | 2 | C | 1 | 15 | aceptar (regla 3) → C: 5–20, queda 1 |
| 10 (termina B) | 2 | D | 2 | 10 | aceptar → D: 10–20, quedan 0 |
| | 0 | E | 2 | 15 | personas insuficientes |
| | 0 | H | 1 | 20 | personas insuficientes |
| 20 (terminan C y D) | 3 | E | 2 | 15 | aceptar → E: 20–25, queda 1 |
| | 1 | H | 1 | 20 | aceptar → H: 20–30, quedan 0 |
| 25 (termina E) | 2 | G | 1 | 20 | aceptar (G antes que F por LST) → G: 25–35 |
| | 1 | F | 1 | 25 | aceptar → F: 25–30 |
| 30 (terminan F y H) | 2 | — | | | nada elegible |
| 35 (termina G) | | | | | **fin** |

```
  3 ┤AAAAA     CCCCCCCCCCHHHHHHHHHH
  2 ┤AAAAACCCCCDDDDDDDDDDEEEEEFFFFF
  1 ┤BBBBBBBBBBDDDDDDDDDDEEEEEGGGGGGGGGG
    └───────────────────────────────────► semanas
     0    5    10   15   20   25   30   35
```
→ **Nueva duración = 35 semanas** (5 más que las 30 originales), con un pico de 3 ✔.
🔹 **¿Se puede hacer en menos?** No. D (2 personas) y E (2 personas) **no pueden correr a la vez** con solo 3 personas, ambas empiezan como pronto en la semana 10, y G necesita las dos terminadas:
- D primero (10–20) → E 20–25 → G 25–35.
- E primero (10–15) → D 15–25 → G 25–35.

En los dos casos G termina en **35**, así que el algoritmo dio el óptimo.
</details>

---

## ✍️ Ejercicios extra (de las diapositivas) para seguir practicando
Resuélvelos de cero y compara con el [Paso 11](11-asignacion-de-recursos.md):
1. **Oficinas** (A 12/2 p · B 8/2 p · C 5/1 p · D 10/4 p dep. A, B · E 10/3 p dep. C, D · F 5/1 p dep. A, B): red (1 dummy), unsmoothed (pico 5), smoothed (pico 5 solo 1 semana), resource-limited con 4 personas (37 semanas).
2. **Ejemplo 5** (A 10/1 p · B 5/2 p · C 10/2 p dep. A, B · D 10/1 p dep. C · E 5/1 p dep. C): red (2 dummies), time-limited (pico 3, no se puede reducir), resource-limited con 2 personas (35 semanas).
3. **Inventa variantes:** toma la Sección A y pide resource-limited con **2** personas, o la Sección B con un plazo de **35** semanas (recalcula los floats con LET(fin) = 35 y vuelve a hacer smoothing).

## ✅ Checklist antes de entregar o de terminar el examen
- [ ] ¿Un solo nodo de inicio y uno de fin? ¿Sin lazos?
- [ ] ¿Cada nodo recibe **exactamente** los prerrequisitos de lo que sale de él?
- [ ] ¿Ningún par de actividades comparte inicio **y** fin? ¿Quité todos los dummies sobrantes?
- [ ] ¿Usé el **plazo del enunciado** en el backward pass (45 en la Sección A)?
- [ ] ¿Convención con **5 elementos** (unidades, normal, crítica en línea doble, dummy, compartimentos del nodo)?
- [ ] ¿Tabla con EST/EFT/LST/LFT/float y camino crítico marcado?
- [ ] ¿Gráfico con ejes rotulados (semanas / personas), crítico abajo y **sin interrumpir** actividades?
- [ ] ¿Respondí **el número del pico y en qué semanas** ocurre, y **justifiqué** el smoothing?
- [ ] ¿En resource-limited mostré la **tabla del algoritmo** con el número de regla en cada decisión?
