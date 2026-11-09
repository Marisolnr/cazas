---
name: cazar
description: Busca productos winner en Facebook Ads Library y te trae los mejores anunciantes (cohorte de 30+ ads con 7+ días corriendo en el país cazado). Barre mercados anglo, brasileño, europeo y —como mercado FUENTE— el hispano. Acepta embudos VSL/TSL/quiz/checkout y también WhatsApp/Messenger (oferta reconstruida desde el copy). Usar cuando el usuario dice "cazar", "buscar winner", "buscar whales", "analizar nicho", "espiar ads", o cuando la corre el programa de caza automatizado (modo bandeja).
---

# Cazar winners en Ads Library

Skill autónoma. El argumento es el **nicho o keyword** a investigar (ej: "recetas keto", "IA para abogados"), o bien un **nodo de la cola** cuando la corre el programa automatizado. Corre sola y devuelve la shortlist en el chat; en **modo bandeja** (§Modos) escribe archivos en el cerebro en vez de hablar.

## Qué hace por defecto

1. **Busca en el mercado que le indiquen** (`mercado`: `en` · `br` · `eu` · `es` · o un ISO-2). Sin argumento, el default histórico: mercados NO hispanos (PT, EN, IT, FR, DE). El hispano se barre **solo como mercado fuente** (ver §Mercado hispano).
2. Agrupa los resultados por anunciante y cuenta cuántos ads activos tiene cada uno.
3. Se queda con los **winners duros**: anunciantes con **~30+ ads que llevan 7+ días corriendo** sobre la misma oferta, contados **en el país cazado**. Los ads creados hoy no cuentan.
4. Los rankea por señales de escala y devuelve la shortlist con link a la landing (o la ficha reconstruida si cierra en WhatsApp), cantidad de ads, antigüedad y el ángulo que están usando.

## Requisito ⚠️

Usa la herramienta **`ads_library_search` del conector oficial de Meta** (el de Facebook — NO un MCP de terceros). Tenés que tenerlo **instalado** y con al menos una cuenta de ads activa en la sesión. Si está diferida, cargarla con ToolSearch.
- Es **solo lectura**: no toca tu cuenta ni crea nada → cero riesgo de baneo.
- **Fallback sin conector**: si no lo tenés instalado, hacé la caza a mano en `facebook.com/ads/library` (Chrome MCP o captura de pantalla) con los mismos filtros y la misma lectura de señales. Más lento, pero funciona. **En modo bandeja NO hay fallback**: sin conector o sin navegador, la sesión deja una línea en `log.md` y sale sin estimar nada.

También se usa el **navegador (Browser MCP o Chrome MCP)** para el Paso 3 · Filtro B: entrar al embudo de cada candidato y verificar que sea una VSL/TSL/checkout real. Sin navegador no se puede cerrar la verificación de embudo → avisar y no dar candidatos por válidos.

## Argumentos

| Argumento | Valores | Default |
|---|---|---|
| `nicho` | keyword / nodo de la cola (`veterinaria/grandes-animales-agro`) | obligatorio salvo modo `huella` |
| `mercado` | `en` (US GB) · `br` (BR, PT control) · `eu` (IT FR DE PT) · `es` (MX CO AR PE CL **BO EC GT** ES) · ISO-2 | no hispano (PT EN IT FR DE) |

> ⚠️ El bloque `es` **sin Bolivia/Ecuador/Guatemala subcuenta a los operadores andinos** (veterinaria, 2026-09-07: Amo la Zootecnia tenía 6 ads y la API devolvió 4). Y al abrir un `ad_snapshot_url` en el navegador, **esperar ~4 s** antes de leer: sin espera solo carga el encabezado.
| `modo` | `nicho` (clásico) · `huella` · `perforar` · `operadores` | `nicho` |
| `salida` | `chat` · `bandeja` | `chat` |

Los modos `huella` / `perforar` / `operadores` y la salida `bandeja` son los del programa de caza automatizado; su detalle está en `referencias/modos-y-bandeja.md` y el método en la página `automatizar-la-caza-de-winners` del cerebro. **Las reglas de evidencia de esta página valen igual en todos los modos.**

## Paso 1 — Barrido

⚠️ La tool **solo permite INCLUIR países, no excluirlos**. Por eso el mercado se elige con dos palancas: (a) keywords en el idioma del mercado y (b) la lista de países del `mercado`.

Llamar a `ads_library_search` con:
- `search_terms`: **una** keyword o frase por llamada (es el texto del creativo). Para probar N variaciones → N llamadas. **El matcher es AND por token: frases largas dan 0 por construcción; buscar con pares de palabras.**
- `countries`: la lista del `mercado` (correr por país o en tandas). Omitir `countries` SOLO si querés barrido global.
- `ad_active_status`: `ACTIVE` (default de caza). **`ALL` es obligatorio cuando un mercado da cero**: distingue un hueco de un cementerio (`el-hueco-que-es-cementerio`).
- `limit`: hasta 50. Si devuelve 50, hay más: la cohorte contada es un **piso** (`≥`).
- `advertiser_request`: el pedido del usuario con sus palabras.

Generar keywords por 4 ejes: **formato** (ebook, guia, template, kit, método, protocolo...), **disparadores de compra impulsiva**, **footprints técnicos** (dominios de Hotmart/Kiwify/Gumroad/Payhip como `search_terms`) y **keywords del nicho traducidas al idioma destino**. Para Brasil funcionan: método, segredo, desafio, renda extra, secar barriga, reconquista, passo a passo. Para inglés: method, secret, challenge, blueprint, protocol, hack.

**Reglas de barrido que salieron de las cazas (obligatorias):**
- **Un mercado no se declara vacío con menos de 4-5 keywords del vocabulario nativo** (matemáticas 🇮🇹, 2026-08-27: una keyword dijo «vacío», cinco encontraron un whale de 101 ads).
- **Buscar angosto para ver la cola larga.** En nichos de churn la keyword amplia devuelve 50 ads de las últimas 48 h y la cohorte queda invisible; la angosta trae las longevidades (matemáticas 🇧🇷, 2026-09-02).
- **El cero no descarta.** Un nicho se descarta solo después de (a) 4-5 keywords nativas, (b) un nivel de subnichos por avatar/materia/formato mirado y (c) `ALL`. Antes de eso el veredicto es «barrido superficial», no DESCARTAR.
- **Leer el idioma de cada creativo.** Keywords idénticas en varias lenguas (`farmacologia`, `peptide`, `dietoterapia`) inflan el mercado 3-8×; la moneda tampoco dice el país del operador.
- **Cruzar la lista de trampas de keyword** de `cazas/cola.md` del cerebro antes de generar keywords, y agregar las nuevas.

De cada ad la tool devuelve: texto del creativo, página, **fecha de creación** y `ad_snapshot_url` (vista visual del ad).

### Mercado hispano (`mercado: es`) — fuente, no destino

Excepción explícita de Franco (Colombia 2026-08-28; programa de caza 2026-09-07). El hispano está cada vez más competido y **una oferta que funciona ahí casi siempre se puede llevar a Europa**. Reglas propias:
- Se caza **para modelar y lanzar en otro mercado**: el veredicto de cada hallazgo es **a qué mercado con hueco se lleva** (`adaptar-winner-extranjero`), nunca «entrar a competir en el hispano».
- El cierre dominante es **WhatsApp / Messenger** → aplicar el Filtro B-WA de abajo, no descartar.
- Trampas propias: keywords compartidas con IT/PT, precios con moneda local que no dicen el país del operador, y fanpages que rotan.

## Paso 2 — Contar el arsenal de cada anunciante

Del barrido salen páginas candidatas. Para cada anunciante prometedor, llamar de nuevo a `ads_library_search` con `page_ids: ["<id de la página>"]` **Y `countries: ["<ISO-2>"]`** → devuelve los ads de esa página en ESE mercado. Con eso se cuenta el arsenal real y la longevidad de cada ad.

> ⛔ **`page_ids` SIN `countries` es un error, no un atajo.** Sin filtro de país la tool devuelve el arsenal **global** de la página, que puede ser 3-4× el del mercado que estás cazando — y el link de Ads Library que después entregás SÍ va filtrado por país, así que el número y el link describen cosas distintas. Caso real (caza Colombia, 28-ago-2026): *Hijos con Carácter* dio **42 ads sin filtro y 13 con `countries:["CO"]`**. **El conteo y el link se hacen sobre el mismo país, siempre.**

> 📌 **Anotar SIEMPRE dos datos por candidato: el `page_id` y el país donde está anunciando.** Los dos son obligatorios para armar el link de Ads Library que va en el output. Si un anunciante corre en más de un país, anotar el país principal y, si son relevantes, dar un link por país.

> 🧟 **La API puede quedarse ciega con una página entera** (Lobo de Cenizas, 2026-09-04: 0 resultados con y sin `countries`). Si el `page_id` da cero y el anuncio existe, medir por navegador con búsqueda de frase exacta. Y **el `page_id` de un reel no es el del anunciante**.

**El filtro madre (winner duro) — se mide sobre la COHORTE DE 7 DÍAS, no sobre el total:**

Para cada candidato, partir sus ads activos en dos grupos usando `ad_creation_time`:
- **Churn** — creados hace menos de 7 días. **No prueban nada**: son la tanda de hoy.
- **Cohorte 7+** — creados hace 7 días o más y **todavía activos**. Estos son los que sobrevivieron: nadie deja corriendo una semana lo que no vende.

**Pasa el filtro madre quien tiene ~30+ ads en la cohorte 7+, en el país cazado.** El total de activos es contexto, no evidencia.

> ⛔ **El error que este filtro existe para evitar** (caza Colombia, 28-ago-2026): se leyó el filtro como *"¿existe al menos un ad de 7+ días?"* en vez de *"¿cuántos ads llevan 7+ días?"*. Con esa lectura, una página que **recrea todo su arsenal cada mañana** pasa el filtro por un único sobreviviente.
>
> | Anunciante | Activos en 🇨🇴 | Cohorte 7+ | Veredicto real |
> |---|---|---|---|
> | Megapack de Lectoescritura | 64 | **≥40** (cohortes a 10·14·16·29·38·54·63·65 d) | winner |
> | Hijos con Carácter | 13 | **7** | tester |
> | Paquete de Diseños | ~104 | **0** (ninguno pasa las 72 h) | fábrica de churn |
>
> **Un anunciante con 100 ads activos y 0 en la cohorte 7+ no es un whale: es una página que quema creativos.**

**Cómo se reporta (obligatorio):** siempre `cohorte 7+ / total activos` juntos, nunca el total solo. Y si la cohorte es chica, decirlo aunque el total impresione.

> 🧟 **Ads zombis:** `ad_creation_time` mide cuándo se creó el ad, no que haya gastado. Dos anunciantes brasileños mostraban 155 y 106 días y no tenían una sola impresión. **Toda longevidad que vaya a un output se confirma abriendo el `ad_snapshot_url`.**

> 🏭 **Fábrica multi-SKU disfrazada de competidor:** una página con 54 ads puede tener uno del nicho y 53 de amigurumi. **Mirar el catálogo antes que el conteo.** El umbral es sobre **la misma oferta**.

## Paso 3 — Filtros anti–falso positivo (OBLIGATORIO antes de rankear) ⛔

Volumen + longevidad NO alcanzan. Antes de meter a cualquier candidato en la shortlist, tiene que pasar estos filtros. Si falla uno, se descarta (o se marca como "no modelable" y se explica por qué).

### Filtro A — ¿Es una marca personal consolidada? → DESCARTAR
Las marcas personales fuertes (un coach/gurú con nombre propio, cara, autoridad y audiencia ya construida) **rompen la lógica de la caza**. Su infoproducto de entrada de $12-19 es un **tripwire**: no lo corren porque ese front-end sea rentable por sí solo, sino para **capturar comprador y escalarlo por su escalera de valor** (mentoría, high-ticket, comunidad).
- Su volumen/longevidad valida **la marca y el back-end**, NO que el infoproducto de entrada sea rentable solo.
- **Nosotros no tenemos esa marca ni esa escalera** → no es modelable.
- **Señales a descartar**: misma cara/voz en todos los creativos, autoridad ("como te enseñé", seguidores, prensa), webinar/evento en vivo, "mi método", venta de mentoría/coaching visible en el funnel.
- **Lo que SÍ queremos**: páginas **fantasma / sin marca personal** que **viven o mueren por la economía del front-end**.

> ⚠️ **La marca personal se juzga en los ANUNCIOS, no en la landing** (Forgotten Home Apothecary, 2026-09-04). Un nombre de persona como página tampoco alcanza: *Ana Valentina Lima* era un fantasma de 35 seguidores cuyo nombre no aparecía ni en el copy ni en el checkout. Lo inmodelable es que **el creativo dependa de un rostro**.

### Filtro B — Verificar el embudo (obligatorio, comprar con los ojos) 🔎
**Nunca asumir el funnel por el anuncio.** Para cada candidato que pasó el volumen/longevidad, **abrir la página del anuncio en el navegador** y recorrer el embudo hasta el checkout.

**Procedimiento (rápido, ~1-2 min por candidato):**
1. Abrir el `ad_snapshot_url`. Ahí se ve el creativo y el **link de destino** (botón/CTA del anuncio).
2. **Mirar a dónde va el destino.** Si es `wa.me`, `api.whatsapp.com`, `m.me` o un botón «Enviar mensaje» → **saltar a B-WA** (abajo). Si es una URL normal → seguir.
3. **Seguir ese link** hasta la landing real y avanzar el funnel un paso más (scrollear, buscar el botón de compra, llegar al checkout).
4. Leer la página con `get_page_text` / `read_page` y **clasificar el tipo de embudo**: **VSL** · **TSL / advertorial→VSL** · **quiz/survey → oferta** · **directo a checkout / página de producto con precio**.
5. Confirmar que la página **está diseñada para vender un infoproducto**: checkout visible directo, o VSL/TSL con oferta diferida (el botón suele aparecer al minuto 10-15: **no descartar por «no veo botón»**).

**Qué es PASA vs FALSO POSITIVO:**
- ✅ **PASA**: el clic termina en una VSL/TSL/quiz/checkout **diseñada para vender un infoproducto**, o en un embudo WA que pasa el test del copy.
- ⛔ **FALSO POSITIVO típico**: página de puro texto que NO empuja a ninguna oferta; link roto; redirect a home genérica; "solo junta leads/seguidores" sin producto prometido; curso presencial; servicio; producto físico donde el objeto es el mecanismo.
- Anotar en el output: **tipo de embudo verificado** (VSL / TSL / quiz / directo / **WA**), qué infoproducto vende y a qué precio. Si no se pudo verificar (link caído, login, geobloqueo), decirlo explícito — no darlo por válido.

> 📦 **Ser producto físico NO descarta por sí solo** (Franco, 2026-09-04): si el dolor se resuelve con conocimiento y el objeto no es el mecanismo, se guarda como molde a convertir (`modelar-producto-fisico-como-infoproducto`). Lo que descarta es que el formato digital equivalente esté saturado o que el saber se regale como bonus del físico.

### Filtro B-WA — Embudo WhatsApp / Messenger: oferta reconstruida desde el copy (Franco, 2026-09-07)

**«Cierra en WhatsApp» dejó de ser motivo de descarte.** En LATAM es el embudo normal del infoproducto low-ticket, y se modela igual: la oferta se reconstruye desde el copy y se relanza **con landing y a precio mayor**. Válido en **todos los mercados**.

- **La evidencia es la misma** (cohorte 7+, escalonamiento, duplicación, Filtro A). Lo que cambia es cómo se verifica: no hay embudo que recorrer, así que se lee **el copy del anuncio + el mensaje prellenado del botón**. En este formato **el anuncio ES la página de ventas** — es el swipe más completo que da la Library.
- **Test del copy (WhatsApp cierra de todo — presenciales, servicios, suplementos, academias):** ¿prueba que es un infoproducto **entregable digitalmente**?
  - ✅ Pasa: PDF, e-book, guía, plantillas, «te llega al instante», «acceso inmediato», precio escrito, sin ciudad ni sede.
  - ⛔ Cae: «inscripciones abiertas», cupos, sede, «agendá tu consulta», envío físico, o un copy que solo dice «escribime para más info» sin decir qué vende. **Sin oferta en el copy no hay oferta que reconstruir, por más ads que tenga.**
- **Filtro C: NO EVALUABLE.** Los bumps y upsells recién se ven hablando con el bot o el vendedor. Se anota «escalera n/e» (ni pasa ni falla) y la ficha lo dice explícito: **el back-end lo diseña Franco desde cero**.
- **Ficha de salida distinta:** qué vende · promesa · dolor · precio dicho (**piso, no referencia**: la landing cobra más) · bonos nombrados · **lista explícita de lo que no se sabe**.
- **Agrupar operadores por número de teléfono del botón o por el texto del mensaje prellenado**: rotan muchas fanpages y no hay dominio que los una. Evita contar cinco veces al mismo vendedor.
- ⛔ **Nunca escribirle al vendedor**, ni en manual ni en automático. Es una acción hacia afuera y contamina su embudo. Si hace falta el precio real o el contenido, lo pide Franco desde su teléfono.
- **Veredicto típico:** no «entrar» sino **arbitraje de embudo + arbitraje de mercado** (misma oferta con landing, precio mayor, otro país) → estrategia `modelar-embudo-whatsapp-a-landing`.

### Filtro C — ¿El front-end es el producto, o es carnada de un back-end?
Aunque tenga BCL y venda algo, preguntarse **de dónde sale la plata**. Si el front-end barato es claramente la puerta a una escalera cara (upsells agresivos a mentoría/coaching, marca detrás), el front-end **no está validado como producto rentable por sí solo**. Modelable = el infoproducto de entrada se sostiene solo. **En embudos WA este filtro se marca n/e** (ver B-WA).

> Regla de oro: **modelamos productos, no marcas.** Un winner válido es una oferta de front-end que un desconocido sin audiencia podría relanzar y que se banca sola.

## Señales de winner — escalera de certeza

> Todos los niveles se cuentan sobre la **cohorte 7+** (ads con 7 o más días corriendo, en el país cazado), nunca sobre el total de activos.

- **Nivel 1 — convierte**: 8+ ads en la cohorte, con antigüedad de 7-20 días. ⚠️ **Para dar una tarjeta en modo bandeja el piso es 10, y de un solo `page_id`** (Franco, 2026-09-23): no se suman fanpages hermanas ni se compensa el volumen con la longevidad de un ad suelto.
- **Nivel 2 — escalando**: ~30 ads en la cohorte.
- **Nivel 3 — WHALE (la casi-segura)**: **50-100+ ads en la cohorte** sobre una misma oferta, y/o los mismos ads corriendo **45-90+ días** sin pausa. La señal más fuerte es el **escalonamiento**: cohortes sucesivas a 10, 20, 40, 60 días prueban que el anunciante fue dejando vivo lo que ganaba, tanda tras tanda. Al detectar un whale, enumerar todo su arsenal con `page_ids`, mapear landings, precios y ángulos.
- **Duplicación de creativos**: el mismo creativo repetido 10-20 veces = ese ya ganó el test interno del anunciante. Anotar esos `ad_snapshot_url` aparte — son los ángulos a modelar primero.
- Todos los creativos apuntando a la MISMA landing (o al mismo número de WhatsApp).
- Misma oferta corriendo en 5-10 fanpages distintas = se esconde de los cloners → convierte seguro.
- Descartar marcas personales consolidadas (Filtro A), todo lo que no pase la verificación de embudo (Filtro B / B-WA) y fanpages "front" duplicadas que no gastan.

## Veredicto de competencia

Contar cuántos anunciantes distintos atacan la misma promesa:
- **ENTRAR**: 2-6 anunciantes activos con gasto sostenido y ninguno domina → demanda validada y espacio.
- **SUBNICHO**: 7+ anunciantes con creativos muy parecidos → validado pero saturado. Proponer 3 subnichos concretos (mismo dolor, avatar más específico).
- **DESCARTAR**: 0-1 anunciantes o ads que mueren a los pocos días → demanda no validada. **Solo se declara con las tres condiciones de «el cero no descarta»; si no, es «barrido superficial» y el nicho vuelve a la cola con subnichos.**
- **WHALE DOMINANTE**: un jugador domina con señales de Nivel 3 → no competirle de frente en su mercado. Modelar su oferta y lanzarla traducida en otro mercado con hueco.

## Arbitraje multi-mercado

Si encontrás un winner fuerte, chequeá si el mismo ángulo está libre en otro mercado. Repetir la búsqueda con `countries: ["<ISO-2>"]` traduciendo el término:
- 🇧🇷 Brasil y 🌎 hispano — cunas de las olas low-ticket → mercados FUENTE
- 🇺🇸 🇬🇧 inglés · 🇮🇹 🇫🇷 🇩🇪 🇵🇹 Europa · 🇷🇴 🇨🇿 🇵🇱 el Este (donde la casa ya opera)

**Orden de prioridad de destino:** 1) inglés (US/GB), 2) Europa (IT/FR/DE), 3) Brasil/Portugal y el Este. Se **modela** desde el mercado fuente (saturado, funnels maduros) y se **lanza** en un destino con 0-3 players débiles. Si en el destino ya aparecen testers con ads de pocos días, la ventana se está cerrando. **Un destino vacío se confirma con `ALL`**: puede ser hueco o cementerio.

## Output (salida `chat`)

Devolver en el chat la **shortlist rankeada de 3-5 anunciantes** que pasaron TODOS los filtros, cada uno con:
- **Nombre de la página + link a su perfil de Ads Library filtrado por el país donde anuncia** (obligatorio, ver abajo) + link a la landing (o la ficha reconstruida si es WA)
- **`cohorte 7+ / total activos`** en ese país, y el escalonamiento (ej: "≥40 / 64 — cohortes a 10·16·29·54·65 d"). **Nunca el total solo.** Este par tiene que poder reproducirse abriendo el link que entregás.
- **Tipo de página**: fantasma/sin marca (✅ modelable) vs marca personal (⛔ descartar)
- **Embudo verificado**: VSL / TSL / quiz / directo / **WA (reconstruido, escalera n/e)** + qué infoproducto vende y a qué precio.
- Hook/ángulo principal (el dolor que atacan = lo validado)
- Los `ad_snapshot_url` de los creativos más duplicados

### 🔗 Link de Ads Library por anunciante — OBLIGATORIO

**Nunca presentar un anunciante sin el link a su perfil de Ads Library, y ese link SIEMPRE va filtrado por el país específico donde está anunciando.**

```
https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=<PAIS>&view_all_page_id=<PAGE_ID>&search_type=page&media_type=all
```

- **Un link por anunciante, mínimo.** Si corre la misma oferta en varias fanpages, dar el link de **cada fanpage**, todas filtradas por país.
- Si corre en varios países, un link por país relevante.
- `active_status=active` por defecto; `all` solo investigando historial.
- Este link muestra **todo el arsenal de la página**; el `ad_snapshot_url` muestra **un creativo**. Se entregan los dos.

⚠️ **Antes de presentar la shortlist, correr Paso 3 sobre cada candidato.** Es preferible una shortlist de 1-2 winners reales que 5 falsos positivos.

Cerrar con el veredicto (ENTRAR / SUBNICHO / DESCARTAR / WHALE) y el par mercado fuente→destino. Si el usuario quiere, guardar todo en un `.md`.

**GATE previo (Paso 3) — eliminatorio, no puntúa:** para entrar al scoring, el candidato debe (a) NO ser marca personal consolidada y (b) tener embudo verificado que vende un infoproducto modelable (o embudo WA que pasa el test del copy). Si falla el gate, queda afuera **por más score que sacaría**.

**Score de 4 señales** (solo para los que pasan el gate; 1 punto c/u): ① longevidad — la cohorte llega a 45+ días; ② volumen — 50+ ads **en la cohorte 7+** de un solo jugador sobre la misma oferta, en el país cazado; ③ duplicación — mismo creativo repetido 10+ veces **dentro de la cohorte**; ④ hueco de arbitraje — sin equivalente fuerte en un mercado destino prioritario. **4/4 = candidata A**; 3 = candidata B; ≤2 = observar. En WA se agrega «escalera n/e» al lado del score.

Recordatorio: el whale valida la **OFERTA**, no te salva de un test sucio. Landing degradada, pixel ciego o un solo conjunto queman igual — cuando lances, armá el test en serio.

## Salida `bandeja` (programa automatizado) — resumen

La sesión **no habla**: escribe. Detalle completo en `referencias/modos-y-bandeja.md`.
1. Antes de empezar lee `cazas/cola.md`, `cazas/descartados.md` y `cazas/bandeja.md` del cerebro.
2. Informe completo en `RAW/cazas-auto/YYYY-MM-DD-<sesión>-<modo>-<nodo>.md` (con la sección **Cobertura**).
3. Una fila por candidato que pasó el gate en `cazas/bandeja.md`, etiquetada `sin-revisar`. **Nunca** con veredicto DESCARTAR: eso lo dice Franco.
4. Actualiza el nodo en la cola (estado, cobertura, bitácora) y agrega trampas nuevas.
5. Una línea en `log.md`.
6. **Nunca**: crea páginas de producto, escribe 🔴 en `descartados.md`, toca `index.md`, ni contacta vendedores.
