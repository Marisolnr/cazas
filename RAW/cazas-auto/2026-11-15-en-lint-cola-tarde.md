# Caza EN · 2026-11-15 (domingo) · lint de la cola · tarde

Corrida de la tarde (18:37 America/Argentina/Buenos_Aires). Domingo = lint de la cola de EN y nada más
(`cazas/nube/NUBE.md` §5), así que no se perforó ningún nodo ni se corrió ninguna búsqueda. El conector de
Meta (`ads_library_search`) se cargó bien.

## Cobertura

- Se re-verificó el lint de la mañana (`RAW/cazas-auto/2026-11-15-en-lint-cola.md`) contra `origin/main`:
  desde las 06:38 los únicos commits sobre `cazas/cola.md` son los del lint ES (06:40) y los del lint BR de la
  tarde (18:35); ningún nodo ni operador EN cambió.
- Re-mediciones EN con fecha ≤ 2026-11-15 sin hacer: ninguna. Nodos EN sin tocar > 30 d: ninguno. 🟡 vencidos:
  ninguno. Las 17 re-mediciones EN que vencen entre el 16 y el 21-11 siguen como las dejó la mañana.

## Decisión

Sin cambios de estado. El orden de perforado para la próxima corrida B sigue siendo el del lint de la mañana
(punto 6): `musica/teoria-workbooks` (único `virgen` EN) primero.

## Nota técnica

El clon arrancó con HEAD desprendido (el `pull` inicial mostró «forced update» de `origin/main`): el primer
push del «en curso» fue rechazado; se resolvió con `git checkout -B main` sobre el commit propio (padre =
`origin/main`) y push normal. Sin force.

## Cambios escritos

- `cazas/cola.md`: línea de la bitácora.
- `cazas/bandeja.md`: una línea bajo `TARJETAS-EN`.
- `log.md` y `cazas/nube/log-nube.md`: una línea cada uno.
