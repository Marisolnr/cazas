# Caza EN · 2026-11-22 (domingo) · lint de la cola

Corrida de la mañana (06:38 America/Argentina/Buenos_Aires). Domingo = lint de la cola de EN y nada más
(`cazas/nube/NUBE.md` §5). No se corrió ninguna búsqueda en la Biblioteca de anuncios; el conector de Meta
(`ads_library_search`) se cargó bien. Las mediciones citadas abajo salen de los informes de las corridas C del
18-11 (`2026-11-18-en-C-operadores.md`) y del 21-11 (`2026-11-21-en-C-agenda.md`), no de consultas nuevas.

## Cobertura

- Nodos EN revisados: 122 en el árbol de `cazas/cola.md` (18 `profundo`, 104 `superficial`, 0 `virgen`).
- Operadores EN (US/GB) revisados en «Operadores a seguir»: 62 filas.
- Cruces: `cazas/descartados.md`, agenda de `cazas/cazas.md` (vacía), bandeja EN (40 tarjetas pendientes),
  informes EN del 18 al 21-11.

## Hallazgos del lint

1. **Nodos sin tocar > 30 días:** ninguno. Los más viejos son del 2026-11-09 (13 días).
2. **🟡 vencidos:** ninguno; no hay 🟡 en la cola, en `descartados.md` ni en la agenda del hub.
3. **Re-mediciones vencidas que ya se hicieron pero no se habían anotado** (se alinearon, con «lint 22-11»):
   - Donna Whitfield (`workbooks-conexion`, vencía 17-11): 0/50 el 18-11 (204 est.) y el 21-11 (247), rota a
     diario → re-medir 2026-12-05.
   - The EaseUp Planners (`digital-tablet`, vencía 16-11): 0/50 el 18-11 (149) y el 21-11 (126); su tanda única
     del 15-11 cumple 7 d hoy → re-medir 2026-11-25.
   - Stitch Well / Elsie Brooks (`ropa-mujer`/`tejido-crochet`, vencía 17-11): 0/50 US·GB el 18-11, rotan a
     diario → re-medir 2026-12-02.
   - Mariana Williams (`fieltro-peluches`, vencía 17-11): 0/50 visibles el 21-11 (254 est.) → 2026-11-27, junto
     con `adviento`.
   - Clones de CustodyLogs (`registro-juicio`, vencía 20-11): apagados o mínimos el 21-11 → mensual.
   - Fingerstyleguitarschool y la fila Nonna Sweets · The art of tarot · Presence College: se les sumaron los
     conteos del 21-11 (Fingerstyle bajó de 31/34 a 12/30 US · 12/16 GB).
4. **Re-mediciones vencidas que nadie hizo** (pasan a la corrida C del miércoles 2026-11-25):
   - `examenes-ilustrados/enfermeria-nclex`: Med Notes Guide, PassPath (vencía 21-11).
   - `examenes-ilustrados/trabajo-social-salud-mental`: LCSW Study Notes (21-11).
   - `examenes-ilustrados/oficios-licencias`: Studio Facile GB (21-11).
   - `examenes-ilustrados/formato-visual-fabricas`: la red «Illustrated» (21-11; el 18-11 solo se midieron Visual
     Guide Lab 0/50, In pictures 0/50 e Illustrated Manuals 9/50 piso).
   - `hogar/preparacion-emergencias/planes-apagon-72h`: Smart Library, Handled Simply, Grid Down Plan, Gridfall,
     READY GB (19-11).
   - `hogar/preparacion-emergencias/habilidades-perdidas`: ola hispana de clones (19-11; también le sirve a ES).
   - `manualidades/patrones-costura-pdf/tejido-crochet`: All Knittings y Knitter's Treasure Chest (17-11).
   - `deportes/.../educacion-fisica-docentes`: Digital Academy (20-11; último conteo 18-11: 23/25 US · 22/23 GB).
   - Fuera de EN: Escuela Fingerstyle (AR, vencía 21-11) figura en el nodo `musica/teoria-workbooks/guitarra`
     pero su fila de operador es hispana; le toca a ES.
5. **Re-mediciones EN que vencen esta semana (corridas C del miércoles 25 y sábado 28):**
   - 2026-11-23: Fingerstyleguitarschool, Nonna Sweets · The art of tarot · Presence College, Music Solved
     (`lectura-partitura`), `hogar/cosmetica-natural-recetas`.
   - 2026-11-24: Elisabeth.says · Nonna Sweets, Realifestation · Emily D · Eureka.labs, ola de péndulo.
   - 2026-11-25: Claudia Williams, The Printed Kitchen, Presence College, The Lighter House, The Savvy Mama ·
     Everyday Home Reset, `sistema-casa-entera`, EaseUp + las 8 pendientes del punto 4.
   - 2026-11-26: Printable WITH Lisa, Sarah Whitfield, Contador en Acción, ELA Skill Builder · Build The Past.
   - 2026-11-27: Excel Sheets Pro · Sunday Budget, Darlene Fisk, HookieNest, ZeroGluten Chef, Paper Lunera ·
     ZapiFun · Grace Miller, Mariana Williams, lanzamientos de `navidad`.
   - 2026-11-28: Sproutpals, Made for Pre-K, ELA Skill Builder (`homeschool`).
   - Operadores EN sin fecha propia medidos por última vez el 18-11 (cadencia quincenal): vencen el 2026-12-02.
6. **Tarjetas de la bandeja cuya página ya se apagó o cayó** (dato de las corridas C del 18 y 21-11; sirve para
   decidirlas): This & That Planners (09-11, apagada), Knitting Art Studio (10-11, apagada), Sewing Lovers (11-11,
   apagada), HookieNest (20-11, apagado el 21-11), Honey Home (09-11, 2/5), Pattern Quilt Studio (16-11, relanzó
   todo el 17-11: 0/34), RootedinFaith (11-11, relanzó: 2/39), Fingerstyleguitarschool (16-11, 12/30).
7. **Orden de perforado (próximas corridas B):** no queda ningún `virgen` EN. Los `superficial` nunca perforados,
   del más viejo: `negocios/guias-management-pdf` (11-11), `religion/papeleria-cristiana-reventa` (11-11, destino
   ocupado en AR/ES), `hogar/kit-sucesion-familia` y `productividad/planillas-vida` (12-11),
   `hogar/cosmetica-natural-recetas` (16-11), `negocios/canastas-regalo-plantillas` y
   `salud-profesional/atlas-esteticos` (19-11), `manualidades/svg-cricut-laser` (20-11).
8. **Cobertura floja dentro de nodos perforados:** `planners-imprimibles-2027/fe-oracion` (1 kw, 09-11) es el
   hijo más viejo y más flojo de la cola EN; `digital-tablet` (4 kw, 09-11) y los hijos de
   `ciberseguridad/plantillas-nist` (09-11) le siguen.
9. **Pendientes que solo se cierran en la PC** (sin cambios desde el 15-11, más los nuevos): CustodyLogs (¿app o
   PDF?), HeroeDigitals (¿app?), Isabella Francis (¿persona? un título dice «Paperback»), Linda Harrison, Heroic
   Husband, RootedinFaith, My Nurse Notes (¿impreso?), Growing in Faith, Food Storage Tips, Revelation Unsealed 3D
   (¿PDF o libro?), Ultimate Life OS (precio y entrega Canva), Emily Makes / Craft By Melanie Smith (caras).
10. **Bandeja:** 40 tarjetas EN pendientes desde el 09-11 y la tabla «Revisiones» sigue vacía: la tasa de
    aprobación todavía no puede calibrar la vara.

## Cambios escritos

- `cazas/cola.md`: 17 alineaciones de fecha o conteo en nodos y operadores EN (puntos 3 y 4, marcadas «lint
  22-11») y la línea de la bitácora.
- `cazas/bandeja.md`: una línea bajo `TARJETAS-EN`.
- `log.md`: una línea.
