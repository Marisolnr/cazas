# Caza EN · 2026-11-22 (domingo) · lint de la cola · tarde

Corrida de la tarde (18:37 America/Argentina/Buenos_Aires). Domingo = lint de la cola de EN y nada más
(`cazas/nube/NUBE.md` §5): no se perforó ningún nodo ni se corrió ninguna búsqueda. El conector de Meta
(`ads_library_search`) se cargó bien.

## Cobertura

- Se re-verificó el lint de la mañana (`RAW/cazas-auto/2026-11-22-en-lint-cola.md`) contra `origin/main`:
  desde a33b3e6 (06:38) solo entraron los lints ES y BR (mañana y tarde); ninguna fila con mercado EN, US o GB
  cambió.
- Re-mediciones EN con fecha ≤ 2026-11-22 en filas de nodos: todas ya re-fechadas a la mañana salvo dos filas
  cuya fecha vieja ya estaba resuelta en otro lado:
  - `religion/biblia-visual/visual-ilustrada`: Revelation Unsealed 3D se midió el 21-11 (19/30 US · 19/29 GB) y
    su fila de operador dice re-medir 2026-12-05; la fila del nodo seguía con «re-medir 2026-11-21» → alineada.
  - `musica/teoria-workbooks/guitarra`: Escuela Fingerstyle (AR) es de ES y el lint ES de hoy la re-fechó al
    26-11 → alineada en la fila del nodo.
- Nodos EN > 30 d sin tocar: ninguno. 🟡 vencidos: ninguno.
- Vencen mañana 23-11: Fingerstyleguitarschool, Nonna Sweets · The art of tarot · Presence College, Music
  Solved (`lectura-partitura`), `hogar/cosmetica-natural-recetas` (las toma la próxima C; la del lunes es A
  huella, así que quedan para la C del miércoles 25-11 junto con las 8 que ya pasaron ahí).

## Decisión

Sin cambios de estado. Próximo B: `negocios/guias-management-pdf` (superficial más viejo, 11-11), como fijó el
lint de la mañana.

## Nota técnica

El primer push chico fue rechazado porque el clon quedó con HEAD separado de `main` tras el `pull --rebase`;
se apuntó `main` al commit y se empujó sin forzar.

## Cambios escritos

- `cazas/cola.md`: 2 alineaciones de fecha y la línea de la bitácora.
- `cazas/bandeja.md`: una línea bajo `TARJETAS-EN`.
- `log.md`: una línea. `cazas/nube/log-nube.md`: no se toca (`cazas/nube/` es de solo lectura para la rutina).
