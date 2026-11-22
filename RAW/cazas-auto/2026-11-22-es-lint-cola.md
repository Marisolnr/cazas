# Caza ES · 2026-11-22 (domingo) · lint de la cola

Corrida de la mañana (06:40 America/Argentina/Buenos_Aires). Domingo = lint de la cola de ES y nada más
(`cazas/nube/NUBE.md` §5). No se corrió ninguna búsqueda en la Biblioteca de anuncios; el conector de Meta
(`ads_library_search`) se cargó bien.

## Cobertura

- Nodos del árbol con mercado ES (incluye los compartidos EN · ES y los 🔴 «todas»): 124 → 101 `superficial`,
  16 `profundo`, 7 🔴. Ningún `virgen` ES.
- Operadores con país hispano en «Operadores a seguir»: 74 filas.
- Cruces: informe C del 19-11 (`2026-11-19-es-C-operadores.md`) para saber qué re-mediciones vencidas ya se
  hicieron; bitácora de la cola; bandeja ES (33 tarjetas con «Decisión: —»).

## Hallazgos del lint

1. **Nodos sin tocar > 30 días:** ninguno. Los más viejos son del 2026-11-09 (13 días):
   `manualidades/patrones-pdf/goma-eva-fieltro` y `manualidades/patrones-pdf/papercraft-fiesta`.
2. **🟡 vencidos:** ninguno; no hay 🟡 en la cola.
3. **«re-medir» sin fecha:** ninguno en ES.
4. **Re-mediciones vencidas de operadores (≤ 2026-11-22): 14.**
   - Ya medidas en CO/ES por el C del 19-11 y con señal viva → se anotó el dato y se re-fecharon al **2026-11-26**:
     Escuela Fingerstyle (CO 0/4, 2 SKU nuevos), Regarte (CO 0/46, ES 0/50 tope, todo relanzado el 18-11),
     Neutral Nature (CO 27/31, ES 42/50 tope, 102 est.), Planos de Barro (CO 10/17), Reino Hub (CO 31/31 = ES
     31/31), Bendiciones creativas (CO 0/50 tope, ES 1/46: quema creativos a diario).
   - Medidas el 19-11 con **0 en CO y ES** y país principal fuera de CO/ES (desde la decisión del 17-11 la sesión ES
     solo mira CO y ES) → **mensual, re-medir 2026-12-19**: Tienda de Hechizos (MX), Mind Digital Studio (AR),
     Consultorio Nutri Listo (AR), Cristianas con Poder (MX/AR/CL), Axo y Yo (MX), Colección Digital Plus (CL),
     Edutechdigital (PE; 19 históricos en ALL CO de 04-16/09).
   - Sin medir y vence hoy: ola navideña Digital Shop · Santos En Punto · Flavia da Silva Araujo · Amigurumi Terapia
     → **C del lunes 2026-11-23**.
5. **Re-mediciones vencidas dentro de nodos del árbol (16-21/11): 17 en 16 nodos** → marcadas «→ 2026-11-23 (C del
   lunes; lint ES 22-11)»: sistemas-de-sesiones/adicciones, pareja-sistemica, nutricionistas;
   patrones-pdf/navideno-pesebre; planner-vaciar-cabeza (padre) y finanzas-plantillas; plantillas-ceramica/
   placas-plantillas; fichas-visuales-estudio/oposiciones-examenes y derecho-contabilidad; kits-por-oficio/
   salud-terapeutas (×2) y belleza-estetica; material-cristiano-imprimible/ninos-escuela-dominical y
   calendarios-fechas; grimorio-brujeria/tarot-guias y astrologia-numerologia; electronica-programacion-pdf/
   arduino-esp32-maker. `hogar/preparacion-emergencias/habilidades-perdidas` ya la había pasado el lint EN al 25-11.
   Varias de estas pueden estar ya cubiertas por el C del 19-11; el C del lunes decide.
6. **Decisión por default (sesión desatendida):** los operadores con país principal fuera de CO/ES no se borran de la
   tabla; pasan a mensual hasta que Marisol diga si los quiere seguir desde otra sesión.
7. **Próxima corrida B de ES (tarde):** `manualidades/patrones-pdf/goma-eva-fieltro` (superficial más viejo,
   2026-11-09; nadie lo tocó en 7 días); después `manualidades/patrones-pdf/papercraft-fiesta`.

## Cambios de estado

Ninguno. Solo fechas y anotaciones en «Operadores a seguir» y en la columna «Próxima acción» de 16 nodos.
