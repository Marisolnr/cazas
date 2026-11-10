# Log técnico de la nube

| Fecha | Sesión | Qué pasó |
|---|---|---|
| 2026-11-08 23:55 | EN | `ads_library_search` no aparece en ToolSearch: el conector de Meta (Biblioteca de anuncios) no está cargado en la sesión de nube (figura sin conectar / pide reconectar). No corrió (era domingo: lint). |
- 2026-11-09 18:40 EN (tarde): el clon arrancó en HEAD desacoplado; `git push origin main` empujaba la rama local vieja y era rechazado. Se resolvió con `git push origin HEAD:main` + `git checkout -B main`.
- 2026-11-10 EN (mañana): WebFetch de heroichusband.com quedó sin permiso (nadie respondió la solicitud); embudo no verificado. El clon arrancó en HEAD desacoplado: `git push origin main` empujaba el main viejo; se arregló con `git branch -f main HEAD && git checkout main`.
