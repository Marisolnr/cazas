# NUBE.md — reglas de las corridas en la nube

Este repo es el «cerebro de caza» de Marisol. Lo leen y lo escriben las **rutinas de Claude Code en la nube**
(una por mercado), sin nadie mirando. Este archivo **manda sobre cualquier otro** del repo donde choquen: la
skill `skills/cazar/SKILL.md` y `skills/cazar/referencias/modos-y-bandeja.md` fueron escritas para una PC con
navegador; acá no hay navegador y el disco es un clon de git.

## 1. Dónde estás y qué hay

- Directorio de trabajo: el clon del repo (normalmente `/home/user/<nombre del repo>`). Todas las rutas de
  abajo son relativas a esa raíz.
- `cazas/cola.md` (qué cazar y en qué modo) · `cazas/bandeja.md` (tus tarjetas) · `cazas/descartados.md`
  (lista negra, se cruza antes de cada tarjeta) · `cazas/cazas.md` (hub y agenda) · `RAW/cazas-auto/` (tu
  informe completo) · `log.md` (una línea por corrida) · `cazas/nube/log-nube.md` (bitácora técnica de la nube:
  qué falló, qué tardó) · `cazas/nube/prompts/<xx>.md` (tu prompt de sesión).
- La skill vive **dentro del repo**: `skills/cazar/SKILL.md` y `skills/cazar/referencias/modos-y-bandeja.md`.
  Donde digan `~/.claude/skills/cazar`, es esa carpeta. Donde digan «Franco», es Marisol; donde digan «el
  cerebro», es este repo.

## 2. Arranque obligatorio (antes de cazar)

1. `git pull --rebase origin main` (otra rutina pudo haber escrito hace minutos). Si falla, `git fetch origin
   main && git reset --hard origin/main` **solo si todavía no escribiste nada**.
2. Hora y fecha en `America/Argentina/Buenos_Aires` (`TZ=America/Argentina/Buenos_Aires date`). El día de la semana decide el modo (§5).
3. Cargar la herramienta de la Biblioteca de anuncios: `ToolSearch` con `ads_library_search`; su nombre
   completo es `mcp__<nombre del conector>__ads_library_search`. **Si no aparece, escribí en `log.md`
   `## [fecha] caza-auto | <XX> — sin conector de Meta, no corrió`, hacé commit + push (§3) y terminá.** No se
   estima nada.
4. Leer `cazas/cola.md`, `cazas/descartados.md`, `cazas/bandeja.md` (las tarjetas de hoy de las otras
   sesiones, para no duplicar) y tu `cazas/nube/prompts/<xx>.md`.
5. Escribir tu línea «en curso» en la bitácora de la cola **y hacer un commit + push chico ya** (así otra
   rutina ve que ese nodo está tomado).

## 3. Escritura y cierre con git (lo más importante de este archivo)

- Varias rutinas escriben el mismo repo casi a la misma hora. Por eso: **inserciones chicas con Edit, nunca
  Write sobre un archivo que ya existe** (Write solo para tu informe nuevo en `RAW/cazas-auto/`). `log.md`
  se agrega al final con `>>`, nunca se reescribe.
- Cierre, siempre en este orden y aunque la caza haya salido vacía:
  ```
  git add -A
  git commit -m "caza <XX> <fecha> <modo> <nodo> → <n> tarjetas"
  for i in 1 2 3; do git pull --rebase origin main && git push origin main && break; sleep 10; done
  git log --oneline -1 && git status -sb
  ```
  Con un clon shallow, si el push falla con «shallow update not allowed», hacé `git fetch --unshallow origin`
  y repetí. Si después de 3 intentos no pudiste pushear, dejalo escrito en tu mensaje final: **una caza que no
  está en `origin/main` no existe.**
- Si el rebase da conflicto, casi siempre es en `cazas/bandeja.md`, `cazas/cola.md` o `log.md`: resolvelo
  **conservando las dos versiones** (lo tuyo y lo del otro), nunca borrando líneas ajenas; `git add` y
  `git rebase --continue`.
- Nunca: `git push --force`, borrar archivos, tocar `skills/`, `cazas/nube/` ni `CLAUDE.md`.

## 4. Sin navegador: cómo cambia la evidencia

- No hay navegador: la web de la Biblioteca y los `ad_snapshot_url` devuelven 403 desde la nube. **Toda la
  evidencia sale de la API** (`ads_library_search`), que trae texto del creativo, página, `ad_creation_time`,
  `ad_delivery_start_time` y `ad_snapshot_url`.
- **Longevidad** = hoy − `ad_delivery_start_time` (en días) del ad que vende. Se anota en la tarjeta como
  «longevidad por API, snapshot no verificado desde la nube». Los filtros de zombis que piden abrir el snapshot
  se reemplazan por: la página tiene **≥ 3 ads creados en fechas distintas** y **≥ 1 creado en los últimos
  30 días** (operador vivo). Una página que solo tiene ads viejos y ninguno nuevo se marca «posible zombi» y
  no pasa a tarjeta.
- **Embudo (Filtro B):** si el copy del ad trae la URL de la landing, probá leerla con `WebFetch`; si carga,
  anotá qué vende, el precio y el tipo (checkout / VSL / WhatsApp). Si no hay URL o no carga, la tarjeta dice
  «embudo no verificado desde la nube: verificar en la PC antes de decidir». Nunca se inventa.
- **Marca personal** se juzga en los anuncios (nombre de página = persona + cara en los títulos). **Nunca
  escribirle a un vendedor** (ni WhatsApp, ni Messenger, ni formulario).
- `page_ids` siempre con `countries`. Cohorte = ads creados hace 7+ días y todavía activos, reportada como
  `cohorte / activos`. `limit: 50` es el tope de la API y no hay paginado: si una página tiene más de 50, la
  cohorte es **un piso** y se dice.

## 5. Dos corridas por día y el modo de cada una

- Hay una corrida a la **mañana** y otra a la **tarde** (06:30 y 18:30 America/Argentina/Buenos_Aires). La de la mañana hace el modo del
  día de la tabla «Rotación vigente» de `cazas/cola.md` (columna de tu sesión). La de la tarde hace **B
  perforar** sobre el siguiente nodo `virgen`/`superficial` de tu mercado que ninguna sesión tocó en 7 días;
  si no hay nodo, repite el modo de la mañana con huellas distintas. Si solo hay una corrida por día (lo dice
  tu prompt), hacés la de la mañana.
- Domingo: **lint de la cola** de tu mercado (nodos sin tocar > 30 días, 🟡 vencidos, re-mediciones con fecha
  cumplida) y nada más; se cierra igual con git.
- Presupuesto por corrida: 45-60 minutos. Si te quedás sin tiempo, cerrá con lo que tengas: un informe parcial
  pusheado vale más que uno completo perdido.

## 6. La salida (lo único que Marisol lee)

- **Máximo 2 tarjetas por corrida.** Vara: pasa el gate (no marca personal, embudo verificado o
  WhatsApp con la oferta en el copy, no excluido) **y** cohorte de **10 o más** ads con 7+ días activos de un solo page_id.
- Formato exacto: §5 de `skills/cazar/referencias/modos-y-bandeja.md`, diez líneas, en español, más la línea
  «Evidencia: API; snapshot y embudo <verificado por WebFetch | no verificados desde la nube>». Se inserta
  justo debajo de `<!-- TARJETAS-<XX>: ... -->` en `cazas/bandeja.md`. Debajo, «Señales del día <XX>», una
  línea por ítem.
- Si nadie pasa la vara: **una sola línea** («<XX> <fecha>: nada que pase la vara; se barrió X, Y, Z»). Nunca
  rellenar.
- Informe completo en `RAW/cazas-auto/YYYY-MM-DD-<xx>-<modo>-<nodo>.md` (mañana) o `...-<nodo>-tarde.md`
  (tarde), con la sección «Cobertura». Actualizá tu nodo, tu bitácora y las trampas nuevas en `cazas/cola.md`.
  Una línea en `log.md`: `## [YYYY-MM-DD] caza-auto | <XX> <modo> <nodo> → <n> candidatos a bandeja`. Una
  línea en `cazas/nube/log-nube.md` si algo técnico falló (conector, 403, conflicto de git, tiempo).
- Lo que **nunca** hace una rutina: crear fichas de producto en `wiki/productos/`, escribir 🔴 en
  `descartados.md`, dar veredicto DESCARTAR, contactar vendedores, tocar `index.md`.
- Mensaje final del chat: **solo las tarjetas tal cual quedaron en la bandeja + las señales**, y una línea
  final con el hash del commit pusheado. Sin informe, sin narración.
