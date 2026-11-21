# Log técnico de la nube

| Fecha | Sesión | Qué pasó |
|---|---|---|
| 2026-11-08 23:55 | EN | `ads_library_search` no aparece en ToolSearch: el conector de Meta (Biblioteca de anuncios) no está cargado en la sesión de nube (figura sin conectar / pide reconectar). No corrió (era domingo: lint). |
- 2026-11-09 18:40 EN (tarde): el clon arrancó en HEAD desacoplado; `git push origin main` empujaba la rama local vieja y era rechazado. Se resolvió con `git push origin HEAD:main` + `git checkout -B main`.
- 2026-11-10 EN (mañana): WebFetch de heroichusband.com quedó sin permiso (nadie respondió la solicitud); embudo no verificado. El clon arrancó en HEAD desacoplado: `git push origin main` empujaba el main viejo; se arregló con `git branch -f main HEAD && git checkout main`.
- 2026-11-12 BR (mañana): el clon arrancó otra vez en HEAD desacoplado (main local en e622a61); el primer push fue rechazado 3 veces. Se arregló con `git checkout main && git merge --ff-only <HEAD>`.
- 2026-11-12 EN (tarde): HEAD desacoplado otra vez al arrancar; el push «en curso» fue rechazado 3 veces. Se arregló con `git checkout -B main HEAD && git branch -u origin/main`.
- 2026-11-12 18:36 BR: WebFetch de la landing de Cozinhanoprato no se pudo correr (pedido de permiso sin respuesta en sesión desatendida).
- 2026-11-13 BR (mañana): HEAD desacoplado al arrancar; el push «en curso» fue rechazado 3 veces. Se arregló con `git checkout -B main HEAD && git branch -u origin/main`.
- 2026-11-13 EN (mañana): HEAD desacoplado otra vez al arrancar (main local en e622a61); el push «en curso» fue rechazado 3 veces. Se arregló con `git checkout -B main HEAD && git branch -u origin/main`.
- 2026-11-13 BR (tarde): conflicto de rebase en la bitácora de `cazas/cola.md` con la línea «en curso» de EN; se resolvió conservando las dos líneas.
- 2026-11-13 ES (tarde): HEAD desacoplado al arrancar (tercera vez hoy); el push «en curso» fue rechazado 3 veces y se arregló con `git checkout -B main HEAD && git branch -u origin/main`. La API de Meta devolvió solo títulos (sin cuerpo del copy ni URL): toda la oferta salió de `ad_creative_link_title`.
- 2026-11-13 18:40 EN (tarde): WebFetch de custodylogs.com rechazado (pide aprobación de URL que nadie contesta en corrida desatendida); embudo quedó sin verificar.
- 2026-11-14 06:40 EN (mañana): HEAD desacoplado al arrancar otra vez; el push «en curso» fue rechazado 3 veces y se arregló con `git checkout -B main HEAD && git branch -u origin/main`. `page_ids` + `search_terms` no destapa la cola vieja en 4 páginas (Lost Skills, Heroic Husband, Visual Guide Lab, Stitch Well).
- 2026-11-14 18:38 EN (tarde): HEAD desacoplado otra vez al arrancar (main local viejo, del 10-11); el push «en curso» se rechazó 3 veces y se arregló con `git branch -f main HEAD && git checkout main`.
- 2026-11-15 18:37 EN (tarde): HEAD desacoplado al arrancar (otra vez); el push «en curso» se rechazó 3 veces y se arregló con `git checkout -B main <commit propio>` + push normal. Patrón recurrente: el clon de la nube arranca en HEAD desprendido.
- 2026-11-15 18:40 ES (tarde): el clon arrancó con HEAD desprendido tras «forced update» de origin/main; resuelto con `git checkout -B main` antes del primer commit, sin force.
- 2026-11-16 18:38 EN (tarde): HEAD desacoplado al arrancar (main local viejo, e622a61 del 10-11); el push «en curso» se rechazó 3 veces y se arregló con `git branch -f main HEAD && git checkout main` + push normal. Sigue recurriendo.
- 2026-11-16 18:45 EU (tarde): la rutina «Caza automática · EU» (trig_01K4RuQZdX6Aj1DD3G9pWbAw, creada hoy 14:22 UTC, cron 06:45/18:45) pide seguir `cazas/nube/prompts/eu.md`, que no existe; tampoco hay columna EU en la rotación de `cazas/cola.md`, marcador `TARJETAS-EU` en la bandeja ni fila en `rutinas.md`. No cazó (no se inventa alcance de mercado).
- 2026-11-17 06:36 BR (mañana): HEAD desprendido al arrancar otra vez (main local viejo); el push «en curso» se rechazó 3 veces y se arregló con `git checkout -B main HEAD` + `git branch -u origin/main` + push normal, sin force.
- 2026-11-17 06:47 EU (mañana): otra vez sin `cazas/nube/prompts/eu.md` (ni columna EU en la rotación, ni `TARJETAS-EU`, ni fila en `rutinas.md`); no cazó. Segunda corrida seguida perdida: falta crear el prompt o pausar la rutina.
- 2026-11-17 EN (mañana): conflicto de rebase en cola.md (bitácora) y log.md con ES/EU; resuelto conservando las dos versiones.
- 2026-11-18 18:40 EN (tarde): conflicto de rebase en cola.md (bitácora) y log.md con BR/ES; resuelto conservando las tres versiones.
- 2026-11-19 06:40 EN (mañana): el brief del primer subagente salió sin la lista de huellas (placeholder); barrió 4 keywords ya usadas. Las 14 huellas nuevas se corrieron con otros 2 subagentes.
- 2026-11-20 06:40 EN (mañana): HEAD desprendido al arrancar (main local 27 commits atrás); el push «en curso» se rechazó 3 veces y se arregló con `git branch -f main HEAD` + `git checkout main` + `git branch -u origin/main` + push normal, sin force.
- 2026-11-21 18:55 EN (tarde): conflicto de rebase en `cazas/cola.md` (bitácora) y `log.md` con BR/ES, resuelto conservando las dos versiones; 1 consulta `page_ids` + `reading` falló con error de la API (reemplazada por `phonics`).
- 2026-11-21 18:45 ES (tarde): la API de la Biblioteca falló 4 veces de forma intermitente («Ad Library search failed»); todas salieron al reintentar.
