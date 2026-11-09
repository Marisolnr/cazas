---
nombre: "Automatizar la caza de winners (programa de caza)"
tipo: estrategia
estado: en implementación — pasos 1-3 hechos el 2026-09-07 (cola + bandeja + skill v2 + CLAUDE.md §7.4 bis); faltan la corrida manual de cada modo y las tareas programadas
fecha: 2026-09-07
tags: [caza, automatizacion, especificacion]
---

# Automatizar la caza de winners — el programa de caza

**Problema que resuelve.** Franco necesita un catálogo amplio de productos validados para modelar cuando
uno de los actuales se muere, y no tiene tiempo de cazar a mano. La skill `/cazar` corrida a mano tiene
además un punto ciego documentado en [[cazas]]: parte de un **nicho que alguien tiene que nombrar**, y
si el nombre está mal nadie lo vuelve a nombrar. Un mercado se declaró vacío con una keyword
(matemáticas 🇮🇹, 2026-08), las keywords amplias solo devuelven el día de hoy, un cero no distingue
hueco de cementerio ([[el-hueco-que-es-cementerio]]), y los descartes se anotan por nicho cuando la
evidencia es por eje y mercado (veterinaria, artesanía, fisioterapia-b2b).

**Decisión de diseño (Franco, 2026-09-07).** No son «tres cazas programadas con una keyword del día».
Es **un programa de caza**: tres sesiones diarias repartidas por mercado que toman su trabajo de una
**cola** que vive en el cerebro, rotan entre **tres modos de descubrimiento**, y dejan todo en una
**bandeja de revisión** que Franco mira una vez por semana. El cerebro no se ensucia solo: ninguna
sesión automática crea páginas de producto ni descarta nada de forma permanente.

---

## 1. Los tres mercados

| Sesión | Mercados que barre | Rol del mercado |
|---|---|---|
| **EN** | 🇺🇸 US · 🇬🇧 GB (+ 🇦🇺 🇨🇦 si el arsenal lo pide) | Fuente y destino |
| **BR** | 🇧🇷 BR (+ 🇵🇹 PT como control) | Fuente (cuna de las olas low-ticket) |
| **ES** | 🇲🇽 🇨🇴 🇦🇷 🇵🇪 🇨🇱 🇪🇸 | **Fuente**. El veredicto de cada hallazgo es *a qué mercado europeo con hueco se lleva* ([[adaptar-winner-extranjero]]) |

La sesión ES es una **excepción explícita** a la regla de «mercados no hispanos» de la skill, con la
misma lógica que la caza de Colombia del 2026-08-28: el hispano está cada vez más competido, y una
oferta que funciona ahí casi siempre se puede llevar a Europa. Lo que NO se hace es entrar a competir
en el hispano.

## 2. Los tres modos (rotan por día)

| Modo | Qué hace | Qué entra a la cola |
|---|---|---|
| **A · Descubrir por huella** | Barre la **huella del formato**, no un nicho: dominios de plataforma y frases de entrega/precio (ver §2.1). Agrupa por anunciante, aplica cohorte 7+ y el gate. | Los **nichos que emergen** de los datos, como nodos nuevos. Acá aparece «plantillas para veterinarios» sin que nadie lo pida. |
| **B · Perforar un nicho** | Toma el nodo más viejo en estado *superficial* y lo baja un nivel: 4-6 subnichos concretos por **avatar, materia o formato** (estudiantes · pequeños animales · grandes animales · plantillas · examen), 4-5 keywords **nativas y angostas** por subnicho, `ALL` cuando da cero. | Los subnichos como hijos del nodo; el nodo pasa a *profundo*. |
| **C · Seguir operadores + agenda** | Enumera con `page_ids` + `countries` las fábricas multi-SKU ya cazadas (Fluidità, Farmácia Mapeada, Tales, ABA Tools, Emma Neumann, Digital Ninja Black…) para ver **qué producto nuevo están probando** antes de que aparezca por keyword; y ejecuta la **agenda de re-caza** de [[cazas]] que hoy nadie corre. | SKUs nuevos de operadores conocidos; nichos 🟡 que reabren. |

**Rotación semanal por defecto** (ajustable en la cola):

| Día | EN | BR | ES |
|---|---|---|---|
| Lun | A huella | B perforar | C operadores |
| Mar | B perforar | C operadores | A huella |
| Mié | C operadores | A huella | B perforar |
| Jue | A huella | B perforar | C operadores |
| Vie | B perforar | C operadores | A huella |
| Sáb | C agenda | A huella | B perforar |
| Dom | — (lint de la cola, una sola sesión) | | |

### 2.1. Huellas por mercado (modo A)

El matcher de `ads_library_search` es **AND por token**: se buscan **pares** de palabras, nunca
frases largas (caza café, 2026-09-01). Las huellas son puntos de partida, y cada sesión anota en la
cola cuáles rindieron.

- **BR:** `hotmart`, `kiwify`, `pay.hotmart`, `acesso imediato`, `e-book`, `passo a passo`, `R$ 19,90`, `R$ 27`, `R$ 37`, `R$ 47`, `R$ 97`, `método`, `segredo`, `desafio`.
- **EN:** `gumroad`, `payhip`, `etsy digital`, `instant download`, `printable`, `digital download`, `$7`, `$17`, `$27`, `$37`, `blueprint`, `protocol`, `cheat sheet`.
- **ES:** `hotmart`, `acceso inmediato`, `PDF`, `guía`, `plantillas`, `te lo envío`, `por WhatsApp`, `S/`, `COP`, `MXN`, `$9`, `$17`, `método`, `paso a paso`.

⚠️ Trampas de keyword ya conocidas y que la sesión NO repite: `book/novel/read` (short-dramas), `Google
Sheets` a secas (short-dramas), `farmacologia` (idéntica en ES/IT/PT → medir con la huella de idioma, ver [[peptidos]] y [[estudiantes-salud]]),
siglas cortas (`EKG` = spam), `barista/latte art` (préstamos que traen anunciantes de otros países).
La lista vive en la cola y crece.

## 3. Las reglas nuevas (cambian la skill)

1. **El cero no descarta.** Un nicho pasa a *descartado* solo después de (a) 4-5 keywords nativas,
   (b) un nivel de subnichos perforado (modo B) y (c) `ad_active_status: ALL` mirado para distinguir
   hueco de cementerio. Antes de eso vuelve a la cola como *superficial*.
2. **El descarte se registra por eje × mercado**, nunca por nicho entero. «Veterinaria» no está
   descartada: están descartados dos productos propios en español. El árbol de la cola lo refleja.
3. **Buscar angosto para ver la cola larga.** En nichos de churn la keyword amplia devuelve 50 ads de
   48 h; la angosta trae las longevidades (lección de [[matematicas]] BR, 2026-09-02).
4. **Toda longevidad se confirma abriendo el snapshot** (ads zombis) y con `limit` como piso, no como
   total (trampa del `limit`, ver [[herbolaria-remedios-naturales]]).
5. **La sesión automática nunca**: crea páginas de producto, escribe en `descartados.md` con 🔴,
   toca `index.md` más allá del log, ni **le escribe a un vendedor** (ver §4).

## 4. El embudo WhatsApp / Messenger (Franco, 2026-09-07)

Hasta hoy «cierra en WhatsApp» era motivo de descarte en el Filtro B (estética, Vispo Studio). En
LATAM es **el** embudo de infoproducto low-ticket, y Franco los modela igual: la oferta se reconstruye
desde el copy y se relanza **con landing y a precio mayor**. Deja de ser veredicto y pasa a ser **un
quinto tipo de embudo**, válido en **todos los mercados**.

- **Evidencia de validación: la misma.** Cohorte 7+ en el país, escalonamiento, duplicación, gate de
  marca personal. No dependen del embudo.
- **Filtro B para WA:** no hay embudo que recorrer, así que se verifica sobre el **copy del anuncio +
  el mensaje prellenado del botón** (destino `wa.me`, `api.whatsapp.com`, `m.me`). El anuncio ES la
  página de ventas: es el swipe más completo que da la Library.
- **Test del copy (WhatsApp cierra de todo):** ¿prueba que es un infoproducto **entregable
  digitalmente**?
  - ✅ Pasa: PDF, e-book, guía, plantillas, «te llega al instante», «acceso inmediato», precio escrito,
    sin ciudad ni sede.
  - ⛔ Cae: «inscripciones abiertas», cupos, sede, «agendá tu consulta», envío físico, o un copy que
    solo dice «escribime para más info» sin decir qué vende (no hay oferta que reconstruir, por más ads
    que tenga).
- **Filtro C (escalera / back-end): NO EVALUABLE.** Los bumps y upsells recién se ven hablando con el
  bot o el vendedor. Se anota «escalera no evaluable», que no es pasa ni falla, y la ficha lo dice
  explícito: **el back-end lo diseña Franco desde cero** con [[validar-bumps-antes-de-producir]].
- **Ficha de salida distinta:** qué vende · promesa · dolor · precio dicho (**piso, no referencia**) ·
  bonos nombrados · **lista explícita de lo que no se sabe**.
- **Agrupación por operador:** rotan muchas fanpages y no hay dominio. Se agrupa por **número de
  teléfono del botón** o por el **texto del mensaje prellenado**, que se repite entre páginas del mismo
  operador. Evita contar cinco veces al mismo vendedor.
- ⛔ **Nunca se le escribe al vendedor**, ni en manual ni en automático. Es una acción hacia afuera y
  contamina su embudo. Si Franco quiere el precio real o el contenido, escribe él desde su teléfono y
  pasa la respuesta.
- **Veredicto típico:** no «entrar en el hispano» sino **arbitraje de embudo + arbitraje de mercado**.
  Tercera forma de modelar junto a [[adaptar-winner-extranjero]] y
  [[modelar-producto-fisico-como-infoproducto]] → página propia [[modelar-embudo-whatsapp-a-landing]].

## 5. Los archivos

### 5.1. `cazas/cola.md` — el árbol de nichos (fuente de trabajo)

Un nodo por nicho/subnicho. Semilla: las 39 páginas de `wiki/nichos/` + `descartados.md`, **reclasificando**
los descartes por nicho a descartes por eje (veterinaria → *superficial*, con subnichos pendientes).

```
| Nodo | Padre | Mercados | Estado | Keywords cubiertas (mercado:kw) | Última caza | Próxima acción |
| veterinaria | — | ES BR EN | superficial | ES:vademecum, ES:veterinario | 2026-05 | B: estudiantes · pequeños · grandes · plantillas · examen |
| veterinaria/plantillas | veterinaria | ES BR | virgen | — | — | B |
```

Estados: `virgen` · `superficial` · `profundo` · `ENTRAR` · `descartado-eje` (con mercado y motivo) ·
`🟡 re-caza <fecha>`. La sesión elige por **estado + antigüedad**: primero lo virgen, después lo
superficial más viejo. Sección aparte: **trampas de keyword** (§2.1) y **operadores a seguir** (modo C).

### 5.2. `cazas/bandeja.md` — la bandeja de revisión (salida)

> **Corrección de Franco (2026-09-07, después de la primera corrida):** no quiere informes. Quiere
> **una o dos tarjetas por mercado y por día** —producto, por qué es ganador, qué se puede hacer con él
> (físico→digital, app→PDF, WA→landing), link de Ads Library— y nada más. La vara para tener tarjeta es
> gate + (cohorte 7+ ≥ 8 o longevidad ≥ 45 d); si nadie llega, una línea y no se rellena. El informe
> largo queda en `RAW/cazas-auto/` como evidencia y **no se le muestra**. Formato exacto en
> `~/.claude/skills/cazar/referencias/modos-y-bandeja.md` §5. Lo de abajo describe la fila interna
> que quedó superada por la tarjeta.

Una fila por candidato que pasó el gate. **Franco la mira una vez por semana, ~5 min.**

```
| Fecha | Sesión | Modo | Anunciante (page_id · país) | Cohorte 7+/activos | Embudo | Score | Veredicto provisorio | Informe | Decisión de Franco |
| 2026-09-08 | ES | A | Plantillas Vet (123… · MX) | 22/31 | WA | 3/4 · escalera n/e | ENTRAR → FR | RAW/cazas-auto/… | (vacío) |
```

Decisiones posibles: `Idea` (→ Claude ingiere por §7.4, crea la página) · `tirar` (→ fila a
`descartados.md` con el motivo de Franco) · `re-cazar <fecha>` (→ agenda) · `profundizar` (→ nodo a
la cola en modo B). Las filas sin decisión se quedan; las decididas se mueven a un histórico al pie.

### 5.3. `RAW/cazas-auto/YYYY-MM-DD-<sesión>-<modo>-<nodo>.md` — el informe completo

Mismo formato de salida de `/cazar` (shortlist, `cohorte/total`, links filtrados por país, snapshots
más duplicados, veredicto, par fuente→destino), más una sección **«Cobertura»**: keywords corridas por
mercado, cuántos resultados, `ALL` sí/no. Es lo que permite que la sesión siguiente no repita.

### 5.4. `log.md`

Una línea por sesión: `## [YYYY-MM-DD] caza-auto | <sesión> <modo> <nodo> → <n> candidatos a bandeja`.

## 6. Las tres tareas programadas

Con el mismo mecanismo que corre `ayl-tracker-corrida-nocturna` (22:05) y las cazas puntuales del
2026-09-04 (06:30-08:00, funcionaron con navegador). Escalonadas para no pisarse ni pisar al Tracker:

| Tarea | Hora local | Sesión |
|---|---|---|
| `caza-auto-en` | **06:30, en paralelo** | EN |
| `caza-auto-br` | **06:30, en paralelo** | BR |
| `caza-auto-es` | **06:30, en paralelo** | ES |

> **Creadas el 2026-09-07** (Franco: las tres a la vez, 06:30, desde el 08-09; modelo Fable 5.1). Como escriben
> sobre los mismos archivos al mismo tiempo, cada sesión inserta bajo su propio marcador
> `<!-- TARJETAS-XX -->` en la bandeja, relee cada archivo justo antes de editarlo y solo hace inserciones
> chicas; el log se abre en modo append. Corren mientras la app esté abierta; si estaba cerrada, corren al
> abrirla. La primera corrida conviene lanzarla con «Run now» para pre-aprobar el conector de Meta y el
> navegador.

> ⚠️ **El horario no sobrevive a un cambio de cuenta; el prompt sí.** Al pasar a otra cuenta de Claude
> (13-09-2026) las tres tareas dejaron de correr: la última corrida fue la del 12-09. Los `SKILL.md`
> siguen intactos en `%USERPROFILE%\.claude\scheduled-tasks\<tarea>\SKILL.md` (están en disco, no en la
> cuenta), pero el **registro del cron vive en el estado de la cuenta** y quedó vacío
> (`list_scheduled_tasks` no devolvía nada). Se rehace con `create_scheduled_task` usando el **mismo
> `taskId`** —eso pisa el `SKILL.md` con un prompt corto—, así que después hay que **restaurar el archivo
> original** (copiarlo de vuelta): el `model: claude-fable-5-1` del frontmatter también se pierde en la
> regeneración. El registro no se rompe por restaurar el archivo. Verificar con `md5sum` contra la copia
> previa y con `list_scheduled_tasks`. Volvieron a quedar a las 06:30 (`30 6 * * *`); la app les agrega
> un jitter de ~1-2 min.

Cada tarea: lee `CLAUDE.md`, `cazas/cola.md`, `cazas/descartados.md`, `cazas/bandeja.md`; elige modo por
día y nodo por estado; corre `/cazar` con el mercado y el modo; escribe el informe en RAW, las filas en
la bandeja, actualiza el nodo en la cola, una línea en el log. Presupuesto: ~45-60 min por sesión.
Si el conector de Meta o el navegador no están, **no estima nada**: deja una línea en el log y sale.

## 7. Cambios concretos a la skill `/cazar`

Versión nueva, con zip de respaldo como se hizo el 2026-09-04.

1. Argumento **`mercado`** (`en` · `br` · `es` · o país ISO) que reemplaza la exclusión dura del
   hispano por la regla «ES es fuente, el veredicto es el destino».
2. Argumento **`modo`** (`huella` · `perforar` · `operadores`) con las huellas de §2.1 y la
   generación de subnichos de §2.
3. **Filtro B:** quinto tipo de embudo **WA/Messenger** con el test del copy, la agrupación por
   teléfono/mensaje y la ficha de oferta reconstruida (§4).
4. **Filtro C:** «no evaluable» para WA, no falla.
5. **Regla «el cero no descarta»** + `ALL` obligatorio ante un cero + mínimo de keywords nativas.
6. Salida **modo bandeja**: escribe RAW + bandeja + cola en vez de solo el chat, etiquetado
   `sin-revisar`; nunca páginas de producto ni 🔴.
7. Prohibición explícita de contactar vendedores.

Y en `CLAUDE.md` §7.4: la operación **CAZA-AUTO → BANDEJA → INGEST** (la revisión semanal de Franco
es el disparador de la ingesta) y la corrección de que WhatsApp ya no descarta.

## 8. Riesgos y cómo se miden

- **Falsos ENTRAR sin Franco.** El hub muestra que sus correcciones son la mitad del valor de cada
  caza (Colombia, Bangladesh). Mitigación: todo sale `sin-revisar`, y la **tasa de aprobación
  semanal** es la métrica de salud: si Franco aprueba <20 % de la bandeja, se suben los umbrales; si
  aprueba >70 %, se bajan.
- **Cuota y throttling de `ads_library_search`**, y la API que se queda ciega con páginas enteras
  (el page_id del reel no es el de Ads Library, ver [[supervivencia]]). Mitigación: la sesión reporta cobertura, no
  conclusiones, cuando la API falla.
- **Bandeja que se llena de ruido de servicios** por WhatsApp en EN/EU. Franco aceptó el riesgo:
  el test del copy filtra, no el país. Se revisa con la tasa de aprobación.
- **Éxito** = candidatos nuevos con score ≥ 3 por semana en la bandeja, nichos nuevos descubiertos
  por huella que no estaban en la cola, y que la agenda de re-caza se ejecute sola.

## 9. Orden de implementación (cuando Franco dé el OK)

1. `cazas/cola.md` sembrada desde nichos + descartados (reclasificación por eje).
2. `cazas/bandeja.md` vacía + `RAW/cazas-auto/`.
3. Skill `/cazar` v2 (§7) + `CLAUDE.md` §7.4.
4. **Una corrida manual de cada modo** en una sola sesión, con Franco mirando la bandeja resultante.
5. Recién ahí las tres tareas programadas.
