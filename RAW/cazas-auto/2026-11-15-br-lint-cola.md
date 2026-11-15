# Caza BR · 2026-11-15 (domingo) · lint de la cola

Corrida de la mañana (06:36 America/Argentina/Buenos_Aires). Domingo = lint de la cola de BR y nada más
(`cazas/nube/NUBE.md` §5). No se corrió ninguna búsqueda en la Biblioteca de anuncios; el conector de Meta
(`ads_library_search`) se cargó bien.

## Cobertura

- Nodos BR revisados: 55 (filas 92-146 de `cazas/cola.md`): 7 `profundo`, 47 `superficial`, 1 `virgen`.
- Operadores BR revisados en «Operadores a seguir»: 37 filas.
- Cruces: `cazas/descartados.md` (solo la fila 🔴 de neurokids), agenda de `cazas/cazas.md` (vacía), bandeja BR.

## Hallazgos del lint

1. **Nodos sin tocar > 30 días:** ninguno. El más viejo es del 2026-11-09 (6 días).
2. **🟡 vencidos:** ninguno; no hay 🟡 en la cola ni en `descartados.md`.
3. **Re-mediciones con fecha cumplida (≤ 2026-11-15):** ninguna en BR.
4. **Re-mediciones sin fecha (arregladas):**
   - `educacao/atividades-prontas-professores/alfabetizacao`: «re-medir» sin fecha → 2026-11-23 (quincenal desde el 09-11).
   - `receitas/ebooks-fit/restricoes`: «re-medir con `page_ids`» sin fecha → 2026-11-26 (quincenal desde el 12-11).
5. **Re-mediciones BR que vencen esta semana (para la corrida C del martes y la del viernes):**
   - 2026-11-18: Estante (psicanálise), Clube do Devocional, Brinca e Aprende.
   - 2026-11-19: Cozinhanoprato.
   - 2026-11-20: Mamãe que fez, Edufisicavisual.
   - 2026-11-21: Tia Juliana, Sinapse Visual, Riscos para Bordar, ComportaMente, Escola da Prevenção / Mundo do Aço (DDS), Campo Vibracional (nodo `esoterismo/radiestesia-mapas`).
   La agenda del hub (`cazas/cazas.md`) sigue vacía: estas fechas viven solo en la cola. No se tocó el hub
   (el lint es solo de la cola).
6. **Orden de perforado (próximas corridas B):** primero `esoterismo/radiestesia-mapas` (único `virgen` BR,
   del 14-11; ojo: su único operador estaba 0/32 y se re-mide el 21-11). Después los `superficial` más viejos
   sin perforar: `escrita-criativa/estruturas-narrativas` y `produtividade/planner-rotina-estudos` (09-11,
   1 huella cada uno), `design-digital/packs-stories-templates` y `oficios/moldes-marcenaria-pdf` (11-11),
   `saude/cartoes-consulta-enfermagem` (14-11).
7. **Cobertura floja dentro de un nodo perforado:** `seguranca-trabalho/cartilhas-sst/nr1-psicossocial` quedó
   con 2 kw (los hermanos tienen 5). Completar si se vuelve a ese eje.
8. **Pendientes que solo se cierran en la PC** (la nube no ve embudos sin URL): Criativizando e Educando,
   Atividades infantil, Ana Beatriz (moldes), Arquivos que encantam, Mariana Fonseca, SST Online Gold ·
   Escola da Prevenção, Receitas Emagrecedoras / Saúde em Forma, Mapas Visuais & ilustrados.
9. **Posibles zombis en la tabla de operadores:** Pequenos Leitores (sin ads en 70 d, ya marcado «bajar a
   mensual»), Regina Alves (sin ads nuevos en 30 d), FitFlow y Comida Saudável. Se dejan; Marisol decide si
   salen de la tabla.
10. **Bandeja:** 19 tarjetas BR pendientes desde el 09-11 y la tabla «Revisiones» vacía, así que la tasa de
    aprobación todavía no puede calibrar la vara.
11. **Nombre de nodo:** `mapas-visuais-r10` tiene padre `educacao` pero el nombre no lleva el prefijo. No se
    renombró (lo usan las tarjetas y la bitácora).

## Cambios escritos

- `cazas/cola.md`: dos fechas de re-medición (punto 4) y la línea de la bitácora.
- `cazas/bandeja.md`: una línea bajo `TARJETAS-BR`.
- `log.md`: una línea.
