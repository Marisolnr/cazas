# Caza BR · 2026-11-22 (domingo) · lint de la cola

Corrida de la mañana (06:35 America/Argentina/Buenos_Aires). Domingo = lint de la cola de BR y nada más
(`cazas/nube/NUBE.md` §5). No se corrió ninguna búsqueda en la Biblioteca de anuncios; el conector de Meta
(`ads_library_search`) se cargó bien.

## Cobertura

- Nodos BR revisados en «El árbol»: 108 (15 `profundo`, 93 `superficial`, 0 `virgen`).
- Operadores BR revisados en «Operadores a seguir»: 63 filas.
- Cruces: `cazas/descartados.md` (solo los 🔴 de nicho entero del dueño), agenda de `cazas/cazas.md` (vacía),
  bandeja BR (36 tarjetas pendientes).

## Hallazgos del lint

1. **Nodos sin tocar > 30 días:** ninguno. Los más viejos son del 2026-11-09 (13 días).
2. **🟡 vencidos:** ninguno; no hay 🟡 BR en la cola ni en `descartados.md`.
3. **Re-mediciones con fecha cumplida (≤ 2026-11-22), re-fechadas al C operadores del martes 2026-11-24:**
   - Árbol: Estante (`psicologia/materiais-psicanalise/psicanalise`, vencía 18-11); Escola da Prevenção /
     Mundo do Aço (`seguranca-trabalho/cartilhas-sst/dds-prontos`, 21-11); Campo Vibracional
     (`esoterismo/radiestesia-mapas`, 21-11).
   - Operadores: Clube do Devocional (18-11), Edufisicavisual (20-11), Tia Juliana (21-11), Sinapse Visual
     (21-11), Riscos para Bordar (21-11).
   - Las corridas del 20-11 (C) y del 21-11 (A + B) no las re-sellaron; puede que se hayan mirado sin dejar
     fecha nueva. Se re-fechan en vez de medirlas hoy (el lint no busca).
4. **Desalineación árbol ↔ operadores:** `receitas/ebooks-fit/colecoes-packs` seguía con «re-medir 2026-11-19»
   para Cozinhanoprato, pero la tabla de operadores ya lo había medido el 20-11 (14/14 sin ads desde el 20-10,
   posible zombi, mensual). El nodo quedó alineado: re-medir 2026-12-20.
5. **Fecha en formato corto:** `qualidade/kits-documentos-editaveis/gestao-rh-pme` decía «re-medir 28-11» →
   2026-11-28 (coincide con la fila de RH Performa).
6. **Operadores sin fecha explícita de re-medición:** 34 filas BR (cadencia quincenal por defecto). La pasada C
   del 20-11 barrió la tabla entera, así que el C del 24-11 vuelve a cubrirlas; no se les inventó fecha.
   Con dos mediciones seguidas en 0 con ALL: Mestre da Madeira y Mamãe que fez (páginas borradas o
   renombradas); posibles zombis ya marcados: Cozinhanoprato, Pequenos Leitores. Se dejan; decide Marisol.
7. **Orden de perforado (próximas corridas B BR):** no hay `virgen` BR. Los `superficial` más viejos son los
   hijos de `educacao/atividades-prontas-professores` del 09-11: primero `datas-e-escola-dominical`, luego
   `educacao-infantil`, `matematica`, `planos-de-aula`, `portugues-fund2`.
8. **Bandeja:** 36 tarjetas BR pendientes desde el 09-11 y la tabla «Revisiones» vacía: la tasa de aprobación
   todavía no puede calibrar la vara.

## Cambios escritos

- `cazas/cola.md`: 8 re-fechas, 1 alineación (Cozinhanoprato), 1 fecha normalizada y la línea de la bitácora.
- `cazas/bandeja.md`: una línea bajo `TARJETAS-BR`.
- `log.md`: una línea. `cazas/nube/log-nube.md`: una línea (HEAD desprendido al arrancar).
