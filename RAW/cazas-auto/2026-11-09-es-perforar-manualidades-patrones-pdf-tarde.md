# Caza automática — ES · B perforar · manualidades/patrones-pdf — 2026-11-09 (tarde)

Corrida de la tarde, en la nube y desatendida. El nodo es el `virgen` más viejo con mercado ES (lo agregó la corrida ES de la mañana por huella). Barrí con `countries: MX CO AR PE CL BO EC GT ES` y `limit 50`.
El corte de cohorte es `ad_delivery_start_time` < 1793655700, o sea 7 días antes de las 21:41 UTC de hoy.
El barrido de keywords lo hicieron 3 subagentes de solo lectura. Los conteos de los dos candidatos los volví a correr en el hilo principal.

## Shortlist

### 1. Crea y Emprende — 1056023200924288 — «Navidad Tejida · +100 patrones» y «Florería Tejida · 50 patrones» (crochet en PDF)
- Ads Library: [AR](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=AR&view_all_page_id=1056023200924288&search_type=page&media_type=all) · [ES](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=ES&view_all_page_id=1056023200924288&search_type=page&media_type=all)
- Cohorte 7+/activos, contando todos los ads:
  - bloque hispano: **19/30**;
  - **AR: 17/20**;
  - ES: 5/13;
  - MX y CO: 0 activos.
- Por oferta, dentro del bloque hispano: Navidad Tejida 14 en cohorte y Florería Tejida 5.
- Escalonamiento:
  - Florería, el más viejo: 20,5 d (1983739988960150).
  - Navidad, el más viejo: 19,4 d (1397980735440944).
  - 14 fechas de creación, del 20-10 al 06-11. Operador vivo.
- Página fantasma: marca genérica, sin nombre de persona. Moneda USD. No hay precio en los títulos.
- Embudo: link. La API no trae la URL, así que no se verificó desde la nube.
- Hook: «Navidad Tejida · +100 patrones», es decir, patrones para tejer adornos y regalos de Navidad para vender o regalar. Es estacional y la ventana se cierra a fines de diciembre.
- Score 2/4: volumen ✓, longevidad ✓ (corta), embudo ✗ (no verificado), precio ✗.

### 2. Cursos Online — 512123288644096 — Mega Pack Papercraft / Pueblito Navideño (plantillas papercraft)
- Ads Library: [MX](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=MX&view_all_page_id=512123288644096&search_type=page&media_type=all)
- Cohorte 7+/activos:
  - bloque hispano: **11/24**;
  - MX: 20 activos;
  - AR y ES: 0.
- Qué hay dentro de la cohorte de 11:
  - 5 «Crea tu Pueblito Navideño», que acaban de pasar los 7 días (7,0-7,2 d);
  - 4 de papercraft («Mega Pack Papercraft» ×3 + «Miniaturas Papercraft»);
  - 2 «Chatea con nosotros».
- Además corren SKUs nuevos: «120 patrones de casitas navideñas» (6,4 d), «Mostacillas 3D» y «Mega kit navideño 2 en 1».
- El ad más viejo que vende tiene 17,3 d (1823877388628931). Hay 6 fechas de creación, la última del 07-11.
- Riesgos:
  - el nombre de la página, «Cursos Online», puede indicar que vende un mini-curso (grabado o en vivo, no se sabe);
  - es multi-SKU;
  - la mitad de la cohorte apenas pasó el corte.
- Moneda MXN.
- Score 1/4.

## Veredicto provisorio

- **Crea y Emprende**: ENTRAR en evaluación (para Marisol).
  - Ya corre en los dos destinos: AR 17/20, ES 5/13. No hay hueco para la misma oferta.
  - Lo modelable es el molde, «biblioteca temática de patrones tejidos» por ocasión: Navidad, flores, bebé, Día de la Madre.
  - Destino: **ES**, donde su cohorte es chica. O AR con otro tema.
- **Cursos Online**: observar / SUBNICHO.
  - Papercraft navideño (pueblito de casitas para imprimir y armar) en MX.
  - En AR y ES no corre: es hueco de destino si se verifica que es PDF y no curso.
- Nada DESCARTAR.

## Cobertura

Hay 8 subnichos y 37 keywords. Ninguna dio cero en ACTIVE. Corrí ALL en `patrones tricot` (4 → 121) y en `bordado mexicano patrones` (2 → 27).

| Keyword | ACTIVE | ALL | Qué trajo |
|---|---|---|---|
| patrones amigurumi | 325 | – | Academia Infinita, Forgium, Digital Shop, Santos En Punto, Amigurumi Terapia, Club creativo; todo < 3 d |
| patrones crochet | 1081 | – | Sofía Ramírez (WA, tapa el top 50), Croché Navidad, varias BRL |
| amigurumi PDF | 246 | – | los mismos de arriba + ruido Etsy EN |
| patrones ganchillo | 121 | – | Digital Shop, Nora Holm, Puntada Maestra (EUR), Mundo Crochet |
| amigurumis venden | 44 | – | Forgium, Aprende y Juega, Tramnomy, Crea y Emprende |
| crochet PDF | 954 | – | Sofía Ramírez, Creativamente digital («+450 patrones por $6.900») |
| patrones palillos | 15 | – | universo chico, casi todo de Chile |
| tejido agujas PDF | 25 | – | La Biblioteca Definitiva De Tejido, Educa Online |
| patrones dos agujas | 78 | – | Mari Carmen Ortega («La Biblia del Punto +2.500»), Plato Lleno |
| patrones tricot | 4 | 121 | cementerio (Maestras del Tricot inactiva, Hobbii EN) |
| patrones bordado | 118 | – | El Taller de Maricarmen, Puntada a Puntada (EUR), Taller Lucía; todo nuevo |
| punto cruz PDF | 18 | – | ruido |
| bordado mexicano patrones | 2 | 27 | cementerio (Bordado Mexicano Perfecto, BRL, apagado) |
| diseños bordado | 1423 | – | ropa bordada / DTF: no sirve |
| moldes costura | 1142 | – | packs de moldes (Aprende & Emprende 6.000, La Moldería) + ruido BR |
| patronaje PDF | 37 | – | academias + Patrones de Moda 7/7 |
| moldes ropa | 678 | – | Premium Master Academy (1500 moldes, 0/19), Educa Online |
| moldes imprimibles | 405 | – | muñecas de papel, cerámica, Digital LAB «$6.990» |
| moldes bebé | 209 | – | Educa Online «MEGA PACK $4», Arte entre Hilos «15 Bs / $2.000 ARS» |
| macramé patrones | 141 | – | emprender con manualidades, Alma de Hilo (clon) |
| macramé PDF | 48 | – | Crea y Emprende, Zapora |
| bisutería PDF | 97 | – | EpoxyResin presencial: basura |
| pulseras patrones | 60 | – | ruido |
| moldes goma eva | 89 | – | Hecho por vos «Kit Papá Noel 150 moldes» 0/48 |
| moldes fieltro | 319 | – | Isabela Costurera; libros sensoriales TEA (excluido, ignorado) |
| moldes foami | 77 | – | Recursos creativos 8/≥50, Edupro «500 moldes $50 MXN» |
| moldes fomi | 14 | – | Activo Store «+850 moldes navideños» |
| fieltro patrones | 27 | – | ruido |
| pesebre crochet | 94 | – | Digital Shop, Santos En Punto, Puntada Maestra |
| moldes navideños | 699 | – | Library Lerner (WA, todo de hoy), tiendas físicas |
| patrones navideños | 866 | – | Sofía Ramírez tapa el top 50 |
| adornos navideños PDF | 398 | – | Mismo Idioma «+370 recuerdos por US$ 6,99» |
| belén ganchillo | 29 | – | Puntada Maestra, Digital Shop |
| cajas imprimibles | 104 | – | plantillas de cerámica; Cajas Para Imprimir Creativas (3 ads) |
| papercraft plantillas | 41 | – | Cursos Online, Rincón creativo, Seminarios Jireh |
| kit imprimible | 995 | – | kits educativos: trampa |
| toppers imprimibles | 27 | – | Activa Academy «Mega Kit de Fiesta +10,000» |
| plantillas cajas | 506 | – | Canva, cerámica: trampa |

### Páginas contadas (page_ids + 9 países, ACTIVE)

| Página | page_id | cohorte/activos | más viejo | nota |
|---|---|---|---|---|
| Crea y Emprende | 1056023200924288 | 19/30 (AR 17/20, ES 5/13) | 20,5 d | tarjeta |
| Cursos Online | 512123288644096 | 11/24 (MX 20) | 17,3 d | tarjeta |
| La Biblioteca Definitiva De Tejido | 1151253608079340 | 23/23 | 57,5 d | **posible zombi**: 3 fechas, ningún ad nuevo en ~49 d → no pasa a tarjeta |
| Aprende y Juega | 1221090801091643 | 9/9 | 41,5 d | «Empieza a Tejer tu Navidad», «Método Hoja & Hilo» |
| Educa Online | 880717081793459 | 9/43 | 24,5 d | «MEGA PACK POR $4» moldes |
| Recursos creativos | 708050409060790 | 8/≥50 (piso) | 33,4 d | moldes foami, «Descarga aquí» |
| Tramnomy | 898523856677651 | 7/13 | 81,6 d | «Curso Virtual»: verificar formato |
| Patrones de Moda | 671011352760426 | 7/7 | 7,4 d | 1 fecha |
| Activa Academy | 881747588346031 | 7/7 (4 de fiesta) | 81,6 d | Mega Kit de Fiesta |
| emprender con manualidades | 116221641477307 | ≥6/≥50 (piso) | 13,3 d | macramé + navideños; sube desde 5 |
| Rincón creativo | 1272095705994400 | 6/21 | 49,6 d | producto no visible |
| Emprendedores | 1480856945104585 | 6/6 | 21,4 d | «+6.000 moldes de costura», Bs 12 / $2.000 |
| Puntada Maestra | 1314855495043139 | 4/23 | 21,4 d | belén crochet 30 figuras PDF, EUR (España) |
| Academia Infinita | 1022451970958750 | 10/≥50 (piso) | 62,5 d | multinicho; los 10 de la cohorte no son de patrones |
| Mundo Creativo Online | 827678297092940 | 3/25 | 13,7 d | multinicho |
| Sor. Margarita | 1377555728769070 | 1/15 | 10,8 d | producto no visible |
| Forgium, Digital Shop, Santos En Punto, Amigurumi Terapia, Club creativo, Mundo Amigurumi, Tejidos con Amor, Hecho por vos, Premium Master Academy, Isabela Costurera, Innovarte, Puntada a Puntada, Batto, Loopavie, Seminarios Jireh | — | 0-1 | < 7 d | ola navideña de esta semana: re-medir 16-11 |
| Sofía Ramírez | 1386276927902506 | indeterminada (50 vistos de ~180, todos < 2,2 d) | — | WA; cohorte oculta detrás del tope |

### Trampas nuevas

- `diseños bordado` trae ropa bordada y DTF.
- `agujas` trae estética facial («sin agujas»).
- `kit imprimible` trae kits educativos de lectoescritura.
- `plantillas cajas` y `cajas imprimibles` traen plantillas de cerámica y Canva.
- `bisutería PDF` trae EpoxyResin con cursos presenciales.
- `moldes fieltro` trae libros sensoriales TEA (nicho excluido, ignorado).
- `patrones navideños` y `patrones crochet`: una sola página de WA (Sofía Ramírez) se come el top 50.
- `crochet PDF` y `amigurumi PDF` traen listados de Etsy en inglés.
- `tricot` casi no se usa en el hispano.

### Hijos del nodo

| Hijo | Estado | Por qué |
|---|---|---|
| crochet-amigurumi | superficial | tarjeta Crea y Emprende; la ola navideña está toda < 7 d |
| tejido-dos-agujas | superficial | hay un posible zombi (Biblioteca Definitiva) |
| bordado | superficial | todo nuevo; bordado mexicano es cementerio |
| costura-moldes | superficial | Educa Online 9/43, Emprendedores 6/6 |
| macrame-bisuteria | superficial | solo emprender con manualidades (piso) |
| goma-eva-fieltro | superficial | Recursos creativos 8/≥50 piso; Hecho por vos 0/48 de esta semana |
| navideno-pesebre | superficial | ola de lanzamientos, re-medir 16-11 |
| papercraft-fiesta | superficial | tarjeta Cursos Online |

El padre pasa a `profundo`.

## Lo que no se pudo verificar

- Landings y precios de las dos tarjetas: la API no trae URL y no hay navegador.
- En Cursos Online no se sabe si vende PDF o mini-curso grabado.
- La cohorte de Sofía Ramírez queda oculta detrás del tope de 50.
- Que La Biblioteca Definitiva De Tejido sea zombi es una inferencia por fechas: hay que abrir el snapshot.
