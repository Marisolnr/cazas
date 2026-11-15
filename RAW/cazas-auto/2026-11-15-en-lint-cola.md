# Caza EN · 2026-11-15 (domingo) · lint de la cola

Corrida de la mañana (06:38 America/Argentina/Buenos_Aires). Domingo = lint de la cola de EN y nada más
(`cazas/nube/NUBE.md` §5). No se corrió ninguna búsqueda en la Biblioteca de anuncios; el conector de Meta
(`ads_library_search`) se cargó bien.

## Cobertura

- Nodos EN revisados: 68 en el árbol de `cazas/cola.md` (10 `profundo`, 57 `superficial`, 1 `virgen`).
- Operadores EN (US/GB) revisados en «Operadores a seguir»: 30 filas.
- Cruces: `cazas/descartados.md` (solo la fila 🔴 de neurokids), agenda de `cazas/cazas.md` (vacía), bandeja EN.

## Hallazgos del lint

1. **Nodos sin tocar > 30 días:** ninguno. Los más viejos son del 2026-11-09 (6 días).
2. **🟡 vencidos:** ninguno; no hay 🟡 en la cola ni en `descartados.md`.
3. **Re-mediciones con fecha cumplida (≤ 2026-11-15):** una, `religion/biblia-visual/visual-ilustrada`
   decía «re-medir 2026-11-14» para Revelation Unsealed 3D. Ya se re-midió el 14-11 (9/33, figura en
   «Operadores a seguir» con nueva fecha 2026-11-21) pero el nodo no se actualizó: se alineó a 2026-11-21.
4. **Re-medición sin fecha concreta (arreglada):** `planners-imprimibles-2027/navidad` decía «antes del
   2026-11-30» → 2026-11-21 (corrida C del sábado), porque es estacional y la ventana se cierra.
5. **Re-mediciones EN que vencen esta semana (corridas C del miércoles 18 y sábado 21):**
   - 2026-11-16: The EaseUp Planners (`digital-tablet`), `musica/teoria-workbooks` (Acordes en Claro, Music Solved, Daniel Brooks).
   - 2026-11-17: Donna Whitfield (`workbooks-conexion`), Stitch Well / Elsie Brooks, All Knittings y Knitter's Treasure Chest (`tejido-crochet`), Mariana Williams (`fieltro-peluches`).
   - 2026-11-19: ola de planes de apagón (Smart Library, Handled Simply, Grid Down Plan, Gridfall, READY GB) y ola hispana de «habilidades perdidas».
   - 2026-11-20: Digital Academy (EF), clones de CustodyLogs.
   - 2026-11-21: My Nurse Notes / Med Notes Guide / PassPath, LCSW Study Notes, Studio Facile, red de fábricas «Illustrated / Visual Explainer», Revelation Unsealed 3D, `navidad`.
   - Operadores EN sin fecha propia (cadencia quincenal): los del 09-11 al 11-11 (Honey Home, Dragon Fire Method,
     Practical Accounting Kit, This & That, Planner Lovers, Heroic Husband, Linda Harrison, Knitting Art Studio,
     The Crochet Nook, Sewing Lovers, Your Consulting Management Guide, RootedinFaith) vencen entre el 23 y el 25-11.
6. **Orden de perforado (próximas corridas B):** primero `musica/teoria-workbooks` (único `virgen` EN, del 09-11).
   Después los `superficial` nunca perforados, del más viejo: `hogar/planner-limpieza` y
   `educacion-profesional/contabilidad-workbooks` (09-11), `negocios/guias-management-pdf` y
   `religion/papeleria-cristiana-reventa` (11-11, destino ya ocupado en AR/ES), `hogar/kit-sucesion-familia` y
   `productividad/planillas-vida` (12-11).
7. **Cobertura floja dentro de un nodo perforado:** en `planners-imprimibles-2027` los hijos `navidad` (0 kw
   propias), `presupuesto`, `docente` y `fe-oracion` (1 kw cada uno) quedaron muy por debajo de 4-5 kw; con la
   ventana estacional hasta enero conviene completarlos antes que otros hijos. `educacion-fisica-docentes`
   quedó con 2 kw.
8. **Posibles zombis anotados en nodos EN** (no pasan a tarjeta hasta ver ads nuevos): Soccer Training Pro
   (sin ads nuevos en 45 d, hermana de Basketball Coach Pro), Kinley's Lane, Calm sphere, Shining Light
   Printables, Catholic Roots, My Digital Prayers, Go CDL Pro.
9. **Pendientes que solo se cierran en la PC** (la nube no ve embudos sin URL): CustodyLogs (¿app o PDF?),
   HeroeDigitals (¿app o PDF?), Isabella Francis (¿persona?), Linda Harrison (formato y cara), Heroic Husband
   (¿libro digital? ¿«7 Day Trial»?), RootedinFaith (formato), My Nurse Notes (¿impreso?), Growing in Faith
   (producto no visible), Food Storage Tips (producto no visto).
10. **Bandeja:** 22 tarjetas EN pendientes desde el 09-11 y la tabla «Revisiones» vacía: la tasa de aprobación
    todavía no puede calibrar la vara.
11. **Operadores con mercado compartido:** Planner Lovers, Valentina Ríos y Digital Academy (clon AR El Bolso
    del Profe) figuran también para ES; no se tocó nada, solo se deja la nota para no contarlos dos veces.

## Cambios escritos

- `cazas/cola.md`: dos fechas de re-medición (puntos 3 y 4) y la línea de la bitácora.
- `cazas/bandeja.md`: una línea bajo `TARJETAS-EN`.
- `log.md`: una línea.
