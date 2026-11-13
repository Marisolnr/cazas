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
