# Caza ES · 2026-11-15 (domingo) · lint de la cola

Corrida de la mañana (06:40 America/Argentina/Buenos_Aires). Domingo = lint de la cola de ES y nada más
(`cazas/nube/NUBE.md` §5). No se corrió ninguna búsqueda en la Biblioteca de anuncios; el conector de Meta
(`ads_library_search`) se cargó bien.

## Cobertura

- Nodos ES revisados: 67 (filas 147-188 y 204-226 de `cazas/cola.md`, más los compartidos EN · ES
  `religion/papeleria-cristiana-reventa` y `hogar/preparacion-emergencias/habilidades-perdidas`):
  8 `profundo`, 58 `superficial`, 1 `virgen`.
- Operadores con país hispano en «Operadores a seguir»: ~42 filas.
- Cruces: `cazas/descartados.md` (solo la fila 🔴 de neurokids), agenda de `cazas/cazas.md` (vacía), bandeja ES.

## Hallazgos del lint

1. **Nodos sin tocar > 30 días:** ninguno. El más viejo es del 2026-11-09 (6 días): `manualidades/patrones-pdf` y sus hijos.
2. **🟡 vencidos:** ninguno; no hay 🟡 en la cola ni en `descartados.md`.
3. **Re-mediciones con fecha cumplida (≤ 2026-11-15):** ninguna en ES.
4. **Arreglos de fecha:**
   - `oficios-digitales/guias-cricut/laser-cnc-archivos`: «re-medir» sin fecha (Planos & Proyectos, The Leather
     Blueprint) → 2026-11-24 (quincenal desde el 10-11).
   - `educacion-profesional/fichas-visuales-estudio/oposiciones-examenes`: Mapasyresumenes decía 18-11 en el nodo
     y 19-11 en «Operadores a seguir» → alineado al 2026-11-19.
5. **Re-mediciones ES que vencen esta semana (para la corrida C del lunes y la del jueves):**
   - 2026-11-16: ola navideña de amigurumi (`crochet-amigurumi`), Educa Online (`costura-moldes`), lanzamientos
     navideños/pesebre (Digital Shop, Santos En Punto, Puntada Maestra), Med Spa Documents Kit.
   - 2026-11-17: Neutral Nature ES/MX (cohorte oculta).
   - 2026-11-18: Sector Digital adicciones, ola de pareja sistémica (Clínica del vínculo, Kit Graduación Listo,
     Psicologia & Recursos 2025), Consultorio Nutri Listo, Studio Facile ES.
   - 2026-11-19: clones hispanos de habilidades perdidas (Maestro del Oficio, Mauricio Rios, Jime Bauer, Lucas
     Rossi), Mente Ordenada, retos de ahorro (Ositos de Entrecasa), Odonto en Orden, Lash Pro / Nail Pro Catálogo,
     Mapasyresumenes, El Bolso del Profe (primera medición de cohorte).
   - 2026-11-20: Mind Digital Studio, LaOfi, Cristianas con Poder, Axo y Yo.
   - 2026-11-21: Bendiciones creativas · Daniela Ramírez J., calendarios católicos 2027, ola de tarot (Arcano Luz,
     Mi Tarot Guiado, Izabel Allencar), Caja del Terapeuta, Tienda de Hechizos, Regarte, Reino Hub.
   La agenda del hub (`cazas/cazas.md`) sigue vacía: estas fechas viven solo en la cola. No se tocó el hub.
   El lunes (C operadores) carga con 16-11 y 17-11 y puede adelantar las del 18-11; el jueves (C), 19-21/11.
6. **Orden de perforado (próximas corridas B de ES):** primero `tecnologia/electronica-programacion-pdf` (único
   `virgen` ES, del 13-11; Macro Aula 5/20, sin cohorte de 10 todavía). Después los `superficial` de primer nivel
   sin perforar, del más viejo: `manualidades/plantillas-ceramica` y `docentes/dinamicas-grupales` (10-11),
   `deportes/planificacion-entrenadores` (11-11), `productividad/plantillas-notion-oficios` (12-11),
   `educacion-emocional/actividades-imprimibles` (13-11; ojo con el roce con neurokids al elegir avatares).
   Los compartidos EN · ES (`papeleria-cristiana-reventa`, `habilidades-perdidas`) quedan detrás.
7. **Cobertura floja dentro de nodos perforados:** `salud-mental/sistemas-de-sesiones/deportiva` y
   `pareja-sistemica` (2 kw), `adicciones` (3 kw), `esoterismo/grimorio-brujeria/pendulo-radiestesia` (1 kw +
   conteo de Regarte). Completar si se vuelve a esos ejes.
8. **Pendientes que solo se cierran en la PC** (oferta invisible por API o duda de formato): Taller Creativo,
   Tendencias Online / Cristiano Digital, IA Programas, Pack Digital Emprendor, Cristianas con Poder,
   Universo Digital («recibes y luego aportas»), Aprende Astrología (¿informe automático o servicio?), Laura Educa
   (¿marca personal? ¿roza neurokids?), Digital Academy MX (qué SKU se queda con la cohorte).
9. **Posibles zombis:** La Biblioteca Definitiva De Tejido (sin ads nuevos desde ~fines de septiembre), Café con
   Jesús, Soy Nutri Digital, Edwindigital, Smartsubli. Se dejan; Marisol decide si salen de la tabla.
10. **Bandeja:** 21 tarjetas ES pendientes desde el 09-11 y la tabla «Revisiones» vacía, así que la tasa de
    aprobación todavía no puede calibrar la vara.
11. **Exclusiones:** ningún nodo ni operador ES perfora neurokids; los dos que rozan (`educacion-emocional`,
    `fe/.../ninos-escuela-dominical`) ya llevan la advertencia en la cola.

## Cambios escritos

- `cazas/cola.md`: dos arreglos de fecha (punto 4) y la línea de la bitácora.
- `cazas/bandeja.md`: una línea bajo `TARJETAS-ES`.
- `log.md`: una línea.
