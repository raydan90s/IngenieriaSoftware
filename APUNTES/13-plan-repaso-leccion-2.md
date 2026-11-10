# Paso 13: Plan de repaso para la 2da lección (miércoles 11-nov-2026)
*Tiempo disponible: **1 hora el lunes 9-nov en la noche** + **la tarde del martes 10-nov** (el plan asume unas 3 horas; abajo dice qué recortar si tienes menos).*

## 🎯 Qué entra (según lo que dijo el profe en las Sesiones 11 y 12)
| Tema | Peso probable | Dónde está |
|---|---|---|
| **Red AoA**: mínimo de dummies, forward/backward pass, float, camino crítico, **convención** | ⭐⭐⭐ (anunciado como "típica configuración" del examen) | [Paso 10](10-gestion-de-proyectos-y-cronogramas.md) §6–7 |
| **Gráfico de recursos**: unsmoothed → **recurso pico** → smoothing | ⭐⭐⭐ (*"es lo que te preguntan en el examen"*) | [Paso 11](11-asignacion-de-recursos.md) §3 |
| **Resource-limited**: 4 reglas + tabla del algoritmo | ⭐⭐ (*"debo acordarme de las reglas"*; está en el taller) | [Paso 11](11-asignacion-de-recursos.md) §4 |
| **Stakeholders + mapa** (a partir de un párrafo de 4–5 líneas) | ⭐⭐ (anunciado "en el final **o antes**") | [Paso 10](10-gestion-de-proyectos-y-cronogramas.md) §3 + ejercicios abajo |
| Roles, milestone/baseline, Gantt vs. redes, time- vs. resource-limited | ⭐ (preguntas cortas de teoría) | [Paso 10](10-gestion-de-proyectos-y-cronogramas.md) §1–5, [Paso 11](11-asignacion-de-recursos.md) §2 |

> ⚠️ El profe **no detalló** el temario exacto del miércoles; dijo *"estudiemos esta parte"*. El plan cubre todo lo visto en las Sesiones 11 y 12, con prioridad en los ejercicios.

---

## 🌙 Lunes en la noche: 1 hora (entender y memorizar, sin ejercicios largos)
| Min | Qué hacer | Archivo |
|---|---|---|
| 0–10 | Lee las secciones **🎯** del Paso 10 y del Paso 11: qué preguntará y cómo. | Pasos 10 y 11 |
| 10–25 | **Reglas de la red AoA** (Paso 10 §6–7): reglas, forward (MAYOR) / backward (MENOR), las 4 fórmulas EST/EFT/LST/LFT, float, convención. Luego **dibuja la red del Ejemplo 3 (oficinas)** sin mirar y compara. | Paso 10 |
| 25–45 | **Paso 11 §2–4**: tabla time- vs. resource-limited, los **6 pasos**, las reglas del gráfico (crítico abajo, no interrumpir) y las **4 reglas**. Léete con calma el smoothing de oficinas (C → 8–13, F → 22–27). | Paso 11 |
| 45–55 | **Escribe a mano la "hoja de memoria"** de abajo **sin mirarla**, y después corrígela. | este archivo |
| 55–60 | Autotest del **Paso 11** (preguntas 1–14). Marca las que fallaste para el martes. A dormir. | Paso 11 |

---

## ☀️ Martes en la tarde: unas 3 horas (practicar como en el examen)
| Bloque | Duración | Qué hacer |
|---|---|---|
| **1** | 45 min | **Taller, Sección A** a mano, **cronometrado (35 min)**: red con plazo de 45 semanas, unsmoothed, smoothing y justificación. Corrige con el [Paso 12](12-practica-taller-aoa-recursos.md) (10 min). |
| — | 10 min | Descanso |
| **2** | 50 min | **Taller, Sección B** a mano: red, gráfico inicial y **resource-limited con 3 personas con la tabla completa**. Corrige. |
| — | 10 min | Descanso |
| **3** | 35 min | **Stakeholders**: repasa el Paso 10 §2–5 (roles, 5 categorías, cebolla, mapa sencillo, milestone/baseline, limitaciones del Gantt) y haz los **2 mapas de práctica** de abajo. |
| **4** | 30 min | **Simulacro nuevo** (abajo), con números que nunca viste, **cronometrado (25 min)**. Corrige. |
| **5** | 15 min | Autotest del Paso 10 + repaso de lo que fallaste el lunes + **checklist del examen** (final del Paso 12). |

### Si tienes menos tiempo, recorta en este orden
1. ❌ Primero sacrifica el **bloque 4** (el simulacro).
2. ❌ Luego reduce el **bloque 3** a hacer **1** solo mapa.
3. ✅ **No sacrifiques** los bloques 1 y 2: son el formato exacto del examen.

### Miércoles antes de la lección (opcional, 15 min)
Solo lee la **hoja de memoria** y el **checklist** del Paso 12. Nada nuevo.

---

## 📄 Hoja de memoria (escríbela de memoria el lunes)
**Red AoA**
- Actividad = flecha (duración debajo) · evento = nodo · **1 nodo de inicio y 1 de fin** · sin lazos · dos actividades **no comparten inicio y fin** a la vez · **mínimo de dummies**.
- Forward: **+ duración, MAYOR** de las que llegan. Backward: **− duración, MENOR** de las que salen. LET(fin) = **plazo del enunciado** o, si no hay, el EET(fin).
- EST = EET(i) · EFT = EET(i) + d · LST = LET(j) − d · LFT = LET(j).
- **Float = LET(j) − EET(i) − d.** Camino crítico = el de **menor** float.
- Lo que **no cambia** entre dibujos distintos: **número mínimo de dummies** y **duración del proyecto**.
- **Convención (5 elementos):** unidades · normal ─── · crítica ═══ (línea doble) · dummy - - - · nodo [N | EET / LET].

**Time-limited (fecha fija, recursos ilimitados → resource smoothing)**
1. Red. 2. Tabla: personas, duración, EST, float, LFT. 3. Ordenar por **float ↑** (empate → **LFT ↑**). 4. Gráfico inicial en el **EST** (crítico **abajo**). 5. **Mover dentro del float** sin cambiar duraciones ni dependencias. 6. Criterio: horas extra en el pico, replantear dependencias.
- **Nunca interrumpir** una actividad. Respuesta: **pico = X personas, en las semanas a–b**.
- Justificación rápida: **pico mínimo ≥ ⌈Σ(personas × duración) ÷ duración del proyecto⌉** y ≥ el mayor "personas" de la tabla.

**Resource-limited (recursos fijos, la fecha puede alargarse)**
- **R1:** menor **LST** primero (empate → menor duración → más recursos). **R2:** no interrumpir. **R3:** no dejar recursos ociosos si alguna elegible cabe. **R4:** no empezar con recursos parciales.
- Tabla: tiempo | libres | elegibles por LST | personas | LST | comentario (aceptar / personas insuficientes).
- Parallel = todas las elegibles a la vez; serial = un orden predefinido.
- Las reglas son **heurísticas**: con criterio a veces sale mejor (oficinas: 37 semanas con las reglas, 33 con criterio).

**Stakeholders**
- Cualquiera **con interés**, **afectado** o **con influencia** (incluidos los que pueden bloquear y los que dan los recursos).
- 5 categorías: senior managers · project managers · practitioners · customers · end users (**customer ≠ end user**).
- Cebolla: **producto → trabajo (operación) → negocio (sponsor, consultores internos) → entorno amplio** (reguladores, beneficiarios político y financiero, consultores externos, **stakeholder negativo**).
- Mapa sencillo: **proyecto al centro**, **clave** cerca o en caja, **no clave** afuera, y **leyenda**.

---

## 🧪 Simulacro nuevo (25 min, unidades: **días**)
| Act. | Duración | Personas | Depende de |
|---|---|---|---|
| A | 6 | 2 | — |
| B | 4 | 1 | — |
| C | 8 | 1 | A |
| D | 5 | 2 | A y B |
| E | 7 | 1 | B |
| F | 4 | 2 | C y D |
| G | 6 | 1 | E |

**a.** Red AoA en el menor tiempo posible (convención, mínimo de dummies). **b.** Gráfico unsmoothed: ¿recurso pico? **c.** Smoothing sin exceder la duración: ¿nuevo pico? Justifica. **d.** Resource-limited con **3** personas: tabla y nueva duración.

<details><summary>✅ Solución</summary>

**a.** Necesitas **2 dummies**: C depende solo de A, E solo de B y D de **A y B**. Por eso A termina en el nodo 2 (sale C), B en el nodo 3 (sale E), y dos dummies (2→4 y 3→4) forman el nodo 4, de donde sale D.

| Flecha | A | B | dummy | dummy | C | D | E | F | G |
|---|---|---|---|---|---|---|---|---|---|
| Nodos | 1→2 | 1→3 | 2→4 | 3→4 | 2→5 | 4→5 | 3→6 | 5→7 | 6→7 |

| Nodo | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| EET | 0 | 6 | 4 | 6 | 14 | 11 | **18** |
| LET | 0 | 6 | 5 | 9 | 14 | 12 | 18 |

| Act. | EST | EFT | LST | LFT | Float |
|---|---|---|---|---|---|
| A | 0 | 6 | 0 | 6 | **0** ⭐ |
| B | 0 | 4 | 1 | 5 | 1 |
| C | 6 | 14 | 6 | 14 | **0** ⭐ |
| D | 6 | 11 | 9 | 14 | 3 |
| E | 4 | 11 | 5 | 12 | 1 |
| F | 14 | 18 | 14 | 18 | **0** ⭐ |
| G | 11 | 17 | 12 | 18 | 1 |

**Camino crítico: A → C → F = 18 días.**

**b.** Orden de apilado: A, C, F, B, E, G, D.
```
  4 ┤      DDDDD
  3 ┤BBBBEEDDDDD   GGG
  2 ┤AAAAAAEEEEEGGGFFFF
  1 ┤AAAAAACCCCCCCCFFFF
    └──────────────────► días
     0    5    10   15
```
Carga: 0–6 = 3 · 6–11 = **4** (C+D+E) · 11–14 = 2 · 14–17 = 3 · 17–18 = 2 → **pico 4 (días 6–11, 5 días)**.

**c.** Total de trabajo = 12 + 4 + 8 + 10 + 7 + 8 + 6 = **55 persona-días**; 55 ÷ 18 = 3.06 → el pico **no puede bajar de 4**. Lo que sí se puede reducir es **cuánto dura**: moviendo **D a 7–12** (float 3) y **G a 12–18** (float 1):
```
  4 ┤       DDDD
  3 ┤BBBBEE DDDDD  GGGG
  2 ┤AAAAAAEEEEEDGGFFFF
  1 ┤AAAAAACCCCCCCCFFFF
    └──────────────────► días
     0    5    10   15
```
(D es continua del día 7 al 12; solo se dibuja más abajo cuando E termina.)
Carga: 0–6 = 3 · 6–7 = 2 · 7–11 = **4** · 11–12 = 3 · 12–14 = 2 · 14–18 = 3 → **pico 4, pero solo 4 días** (antes 5). Dependencias: D (7) después de A (6) y B (4) ✔; F (14) después de D (12) ✔; G (12) después de E (11) ✔.

**d.** Resource-limited con 3 personas (LST: A 0, B 1, E 5, C 6, D 9, G 12, F 14):

| t | Libres | Elegible | Pers. | LST | Comentario |
|---|---|---|---|---|---|
| 0 | 3 | A | 2 | 0 | aceptar → queda 1 |
| | 1 | B | 1 | 1 | aceptar → quedan 0 |
| 4 (termina B) | 1 | E | 1 | 5 | aceptar → E: 4–11 |
| 6 (termina A) | 2 | C | 1 | 6 | aceptar → C: 6–14, queda 1 |
| | 1 | D | 2 | 9 | personas insuficientes (R4) |
| 11 (termina E) | 2 | D | 2 | 9 | aceptar → D: 11–16 |
| | 0 | G | 1 | 12 | personas insuficientes |
| 14 (termina C) | 1 | G | 1 | 12 | aceptar → G: 14–20 |
| 16 (termina D) | 2 | F | 2 | 14 | aceptar → F: 16–20 |

```
  3 ┤BBBBEE     DDDDDGGGG
  2 ┤AAAAAAEEEEEDDDDDFFFF
  1 ┤AAAAAACCCCCCCCGGFFFF
    └────────────────────► días
     0    5    10   15   20
```
→ **Nueva duración = 20 días** (2 más que 18), con un pico de 3 ✔.
</details>

---

## 🗺️ Práctica de mapas de stakeholders (como en el examen: un párrafo → identificar → mapa clave / no clave)
*Los casos son inventados para practicar.*

**Caso 1.** *La Clínica Veterinaria San Roque, de Guayaquil, quiere un sistema web y móvil para agendar citas y llevar historias clínicas. La directora general impulsó el proyecto y aprobó el presupuesto. Veterinarios y recepcionistas lo usarán a diario, y los dueños de mascotas agendarán desde la app. El área de TI de la clínica dará soporte. La autoridad sanitaria exige el registro de vacunas, una empresa externa provee la pasarela de pagos y una clínica competidora ve el proyecto con malos ojos. El sistema lo desarrollan 5 estudiantes de ESPOL.*

**Caso 2.** *El Municipio de un cantón contrata una app para que los ciudadanos reporten baches y alumbrado dañado. El alcalde quiere mostrar resultados antes de las elecciones. El director de Obras Públicas lidera el proyecto y sus cuadrillas atenderán los reportes. La Contraloría auditará el gasto, una consultora externa revisa la arquitectura y un concejal de oposición critica el proyecto en los medios. El proveedor de mapas cobra por consulta.*

<details><summary>✅ Solución sugerida (la clasificación clave / no clave es "subjetiva hasta cierto punto", según el profe)</summary>

**Caso 1**
| Stakeholder | Capa (cebolla) | ¿Clave? |
|---|---|---|
| Directora general | Negocio: **sponsor** | ✅ clave |
| Veterinarios, recepcionistas | Trabajo: **usuarios finales / operadores** | ✅ clave |
| Dueños de mascotas | Entorno: **clientes** (usuarios de la app) | ✅ clave |
| Autoridad sanitaria | Entorno: **regulador** | ✅ clave (puede bloquear) |
| Equipo de 5 estudiantes | Producto: **desarrolladores** | ✅ clave |
| Área de TI | Trabajo: **soporte / mantenimiento** | no clave (o clave, si mantendrá el sistema en IS II) |
| Proveedor de pasarela de pagos | Entorno: proveedor | no clave |
| Clínica competidora | Entorno: **stakeholder negativo** | no clave, pero hay que identificarlo |

**Caso 2**
| Stakeholder | Capa | ¿Clave? |
|---|---|---|
| Director de Obras Públicas | Negocio: **sponsor** / líder | ✅ clave |
| Alcalde | Entorno: **beneficiario político** | ✅ clave |
| Ciudadanos | Entorno: **usuarios finales / clientes** | ✅ clave |
| Cuadrillas de obras | Trabajo: **operadores** | ✅ clave |
| Contraloría | Entorno: **regulador** | ✅ clave |
| Consultora externa | Entorno: **consultor externo** | no clave |
| Concejal de oposición | Entorno: **stakeholder negativo** | no clave |
| Proveedor de mapas | Entorno: proveedor | no clave |

**Cómo dibujarlo:** el **proyecto en el centro**, los clave en un primer anillo (o en cajas), los no clave afuera, y **leyenda** ([ ] = clave, sin caja = no clave).
</details>
