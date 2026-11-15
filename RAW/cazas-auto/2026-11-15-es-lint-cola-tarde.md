# Caza ES · 2026-11-15 (domingo) · lint de la cola · tarde

Corrida de la tarde (18:40 America/Argentina/Buenos_Aires). Domingo = lint de la cola de ES y nada más
(`cazas/nube/NUBE.md` §5): no se perforó ningún nodo ni se corrió ninguna búsqueda. El conector de Meta
(`ads_library_search`) se cargó bien.

## Cobertura

- Se re-verificó el lint de la mañana (`RAW/cazas-auto/2026-11-15-es-lint-cola.md`) contra `origin/main`:
  desde el commit `a2696ea` (06:40) los únicos cambios en `cazas/` son las líneas de bitácora y bandeja de los
  lints BR y EN de la tarde; ningún nodo, operador, fecha de re-medición ni fila de `descartados.md` de ES cambió.
- Re-mediciones ES con fecha ≤ 2026-11-15 sin hacer: ninguna. Nodos ES sin tocar > 30 d: ninguno. 🟡 vencidos:
  ninguno. Las 27 re-mediciones ES que vencen entre el 16 y el 21-11 siguen como las dejó la mañana.
- Exclusiones: neurokids sigue sin nodos ni operadores ES.

## Decisión

Sin cambios de estado. El orden de perforado para la próxima corrida B sigue siendo el del lint de la mañana
(punto 6): `tecnologia/electronica-programacion-pdf` (único `virgen` ES) primero. El lunes a la mañana toca
C operadores con las re-mediciones del 16 y 17-11.

## Nota técnica

El clon arrancó con HEAD desprendido (el `pull` inicial mostró «forced update» de `origin/main`, igual que
EN y BR esta tarde); se resolvió con `git checkout -B main` antes del primer commit. Sin force.

## Cambios escritos

- `cazas/cola.md`: línea de la bitácora.
- `cazas/bandeja.md`: una línea bajo `TARJETAS-ES`.
- `log.md` y `cazas/nube/log-nube.md`: una línea cada uno.
