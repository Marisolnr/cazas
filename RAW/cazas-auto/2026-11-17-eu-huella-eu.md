# Caza automática — EU · huella (A) · — (IT FR DE PT) — 2026-11-17

Corrida de la mañana (07:08 ART). El martes toca **B perforar**, pero la cola no tiene ningún nodo con mercado EU
(es la primera corrida de la sesión EU), así que, según `prompts/eu.md` §6 («cola vacía → modo A»), se hizo **A huella**
y los nichos que emergieron entran a la cola. Evidencia 100 % por API (`ads_library_search`); sin navegador: snapshots
y embudos **no verificados desde la nube**. Cohorte = ads con `ad_delivery_start_time` ≤ 2026-11-10 10:09 UTC (7+ días)
y todavía activos. 3 subagentes de lectura + re-conteo propio de los 3 que pasan la vara.

## Shortlist

### 1. Die Kunst des Tarot — DE — `esoterismo/tarot-guias-eu`
- Ads Library: https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=DE&view_all_page_id=1401739863026385&search_type=page&media_type=all
- Cohorte 7+/activos: **≥12 / ≥50 visibles (82 estimados)** — re-conteo propio. Piso: la API devuelve los 50 más nuevos; los 32 que no se ven son más viejos, así que la cohorte real es mayor.
- Escalonamiento visible: tandas creadas el 05-11, 07-11, 08-11, 10-11, 11-11, 12-11, 13-11, 14-11, 15-11 y 17-11 (10 fechas). Ad más viejo visto: 07-11 (10 días). Operador vivo (tanda hoy). No es zombi.
- Página de marca (sin persona). Copy en primera persona en algunos títulos («Ihr habt gefragt, ich lese»), pero ningún nombre ni cara en los títulos. Cobra en USD.
- Oferta: método para leer tarot «sin memorizar» («Tarot lesen ohne Auswendiglernen», «Jede Karte mit einem Plan lesen», «Die 16 Hofkarten mit einer Formel», «Buch vs. Methode», «Das Geschenk für Tarot-Fans»). Precio no visible en DE; el mismo operador acaba de lanzar en IT **La Mappa dei Tarocchi** (1504273442761198, 0/6, nació hoy) con «La Mappa dei Tarocchi + 6 regali a 18 €».
- Mismo molde en EN: The art of tarot (1395155533680469), ≥28/96 en GB el 16-11 (ya está como señal EN).
- Duplicación: cada ángulo corre en tandas de 4-5 copias («5 Fragen, jede Karte» ×5, «Jede Karte in der richtigen Reihenfolge» ×5, «Dein Deck in der Schublade?» ×5, «Wähle eine Karte: 1, 2 oder 3» ×5).
- Embudo: no verificado desde la nube (sin URL de landing en la API).
- Score: ① no (10 d visibles) · ② no (≥12) · ③ no (5 copias por ángulo) · ④ sin medir → 0-1/4. Pasa la vara (10+ de un solo page_id).

### 2. Isabel Martins — PT — `manualidades/patrones-tricot-pt`
- Ads Library: https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=PT&view_all_page_id=1431639723356021&search_type=page&media_type=all
- Cohorte 7+/activos: **16 / 27** (conteo completo, 27 estimados) — re-conteo propio.
- Escalonamiento: ads de 14-10, 15-10, 18-10 (×3), 19-10, 23-10, 24-10 (×2), 30-10, 04-11, 08-11, 09-11, 10-11; tandas nuevas el 11-11, 12-11, 13-11, 15-11 y 17-11. Ad más viejo: **14-10 (34 días)**. Operador vivo, ~19 fechas distintas.
- Página con nombre de persona, pero ningún título usa el nombre ni la cara: un solo título repetido («A Bíblia do Tricot – mais de 2000 modelos 🧶»). Cobra en USD (probable operador brasileño apuntando a Portugal).
- Oferta: colección digital de más de 2000 modelos de tricot (dos agujas), un solo SKU; precio no visible por API.
- Duplicación: el mismo título en 26 de 27 ads, 16 de ellos en la cohorte.
- Embudo: no verificado desde la nube.
- Score: ① no (34 d) · ② no · ③ sí (mismo título ×16 en la cohorte; creativo exacto no verificable) · ④ sin medir → 1/4.

### 3. O Pomar Mês a Mês — PT — `jardineria/poda-frutales-pt` (pasa la vara; no entra por el tope de 2)
- Ads Library: https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=PT&view_all_page_id=1349673428238130&search_type=page&media_type=all
- Cohorte 7+/activos: **10 / 22** (conteo completo). Ad más viejo: 04-11 (13,4 d). Fechas: 04-11, 05-11, 06-11, 09-11, 13-11, 17-11. EUR, página nativa portuguesa, sin persona.
- Oferta: «Poda de Árvores de Fruto Mês a Mês», 14,90 € («O que recebe por 14,90 €», «A figueira, na página 22», «A figueira do avô, em três invernos»). ¿PDF o libro impreso? «na página 22» no decide: verificar en la PC.

## Veredicto provisorio
- Die Kunst des Tarot: **WHALE en formación / ENTRAR en destino** — el molde «tarot sin memorizar» corre en GB, DE y arranca en IT: la ventana se va cerrando en Europa occidental. Par sugerido DE → **Rumania** o **Grecia** (validados; hueco no medido desde la nube).
- Isabel Martins: **ENTRAR en destino** — Par PT → **Italia** o **Rumania** (validados). En FR ya corre Sylvie Moreau (tricot) y en ES La Biblioteca Definitiva De Tejido es posible zombi.
- O Pomar Mês a Mês: observar (señal).
Nunca DESCARTAR.

## Cobertura

| Keyword | País | ACTIVE (est.) | ALL | Qué trajo |
|---|---|---|---|---|
| `guida pdf` | IT | 1527 | — | Mappa dei Tarocchi, Francese Illustrato, Creative Factory (Cricut), learndigital.shop (atlas), Visualia Books, Growth Lab (bigino tagli), CreativoMundial, Maestrías Digitales; Neuralforkids (excluido, ignorado) |
| `download immediato` | IT | 1993 | — | ebook arquero 29,90 €, Success Food Truck, Accademia Acquerello (MXN), Cine SFX; L'Officina del Metallo (excluido, ignorado) |
| `ebook pdf` | IT | 587 | — | Atelier dei Biscotti (BRL), Mister Shop, O Pomar Mês a Mês (PT), páginas de PDFs médicos/piratería |
| `accesso immediato` | IT | 5205 | — | mapas de inglés con nombres de persona, Immagina e Crea (crochet), Silvia Moretti (musicogrammi 6,90 €), Clara Zuhause |
| `pdf scaricabile` | IT | 405 | — | casi todo Studio Facile (563 est.) |
| `mappe illustrate` | IT | 451 | — | Mappa dei Tarocchi, Francese/Spagnolo Illustrato, Mente Accademica (BRL), Mappe per Concorsi |
| `guide pdf` | FR | 1917 | — | Camille Laurent FR, Camille-Autonomie (17 €), Trenly Group (Inkscape), Elsa Rivière, Harmonia Studio, Dra. Angela Barros (persona), CreativoMundial |
| `téléchargement immédiat` | FR | 1595 | — | Éditions Rémanence, Kit Comptable (Anna herrero / Amélie Boissieu); Université du Ferronnier (excluido, ignorado) |
| `ebook pdf` | FR | 442 | — | Easy Language Books, Hidjer Edition, Zenbrik (9 €), Rituali e Candele |
| `accès immédiat` | FR | 3688 | — | La Bible des Patrons, Clara Zuhause, Sylvie Moreau (tricot), Antoine Lefebvre Petit |
| `guide illustré` | FR | 230 | — | Camille-Autonomie, Re.construirte, dermatoscopía |
| `fiches pdf` | FR | 795 | — | Manuels Illustrés, Atelier Nova, Studio Facile FR; Labdigital (HVAC, excluido, ignorado) |
| `pdf ratgeber` | DE | 234 | — | lead magnets gratis (Beamte, PRO Schule), Hellhörig Ratgeber, Petra Weber; poco infoproducto pago |
| `sofort download` | DE | 2549 | — | ruido: short-dramas, juegos, apps |
| `ebook pdf` | DE | 734 | — | **Die Kunst des Tarot**, German Grammar Made Visual, Easy Language Books, MallorcaWise 3,49 € |
| `pdf vorlagen` | DE | 313 | — | Keksatelier (BRL), Anna Müller (Kreuzstich), Spürbare Anatomie, Vorlagen-Set Psychotherapie |
| `digitaler download` | DE | 99 | — | Stitchy (crochet 17,99 €), weddingtree.de, ruido físico |
| `anleitung pdf` | DE | 661 | — | Rachel Bennett (Kita 5 €), 21-Tage-Leber-Plan, KogniBlätter; Neuralforkids (excluido, ignorado) |
| `acesso imediato` | PT | 3000 | — | desborde BR (BRL): Mariana Melo, Vovó Sofia; Renata almaral (4,90 €), **Isabel Martins**, Luxe Resin, Chef Tiago |
| `ebook pdf` | PT | 414 | — | **O Pomar Mês a Mês**, O Último Maço (EUR), Menu 5€, A Casa Não Se Gere Sozinha |
| `guia pdf` | PT | 900 | — | mayormente BRL/LatAm; Psicólogo em Ordem (EUR), The Hoord 9,90 € |
| `download imediato` | PT | 234 | — | desborde BR; A Universidade do Serralheiro (excluido, ignorado) |
| `moldes pdf` | PT | 90 | — | Renata almaral, Prof. Sabrina Maia |

Sin ceros: `ALL` no hizo falta.

### Páginas contadas con `page_ids` + país (cohorte 7+ / activos)

| Página | page_id | País | Cohorte | Más viejo | Nota |
|---|---|---|---|---|---|
| Die Kunst des Tarot | 1401739863026385 | DE | ≥12/≥50 (82) | 10 d visto | tarjeta |
| Isabel Martins | 1431639723356021 | PT | 16/27 | 34 d | tarjeta |
| O Pomar Mês a Mês | 1349673428238130 | PT | 10/22 | 13 d | señal (tope de 2) |
| Prof. Sabrina Maia | 1442918862233237 | PT | 14/27 | 10 d | solo 2 fechas de creación → no pasa el filtro zombi; «Prof.» persona; estacional (Navidad 5,90 €) |
| Rachel Bennett | 280579905138659 | DE | 6/≥50 (68) | 10 d visto | Kita-Aktivitäten 5 €, multiidioma; cohorte oculta |
| Elsa Rivière · Pilates et Yoga | 1498431200011027 | FR | 7/12 | 14 d | app de clases para instructores; nombre de persona |
| La Bible des Patrons | 1418428721348749 | FR | 5/21 | 18 d | 156 patrones imprimibles |
| Clara Zuhause | 1341978468987935 | FR | 4/25 | 13 d | planner de limpieza (FR/IT) |
| Creative Factory | 883400961532439 | IT | 3/10 | 26 d | 130 guías Cricut (molde de Biblioteca Creativa ES) |
| CreativoMundial | 482143334974950 | IT · FR | 3/26 · 0/10 | 8 d | multi-SKU |
| Stitchy | 1147506285104017 | DE | 3/≥50 (59) | 12 d | crochet 7 por 17,99 € |
| Harmonia Studio | 606744882527931 | FR | 2/15 | 8 d | acuarela |
| Spagnolo Illustrato | 1383450134858331 | IT | 1/10 | 10 d | clon de Francese Illustrato |
| Maestrías Digitales | 1242730725591726 | IT | 1/17 | 7 d | homilías |
| learndigital.shop | 1053888401135256 | IT | 0/≥50 (102) | 3 d visto | atlas visuales salud; cohorte oculta |
| Studio Facile | 1232011766670582 | IT | 0/≥50 (563) | <1 d visto | catálogo de PDFs ilustrados; parte en nichos excluidos |
| Mente Accademica | 874820029047521 | IT | 0/≥50 (244) | 6 d visto | BRL; mapas neuroanatomía/informática |
| Dra. Angela Barros | 1378520662003518 | FR | 0/≥50 (84) | 6 d visto | persona |
| Resto (0 en cohorte) | — | — | — | — | Mappa dei Tarocchi, Francese Illustrato, NexusStore, Visualia Books, Growth Lab, Clara Valmer, Giardino delle Intenzioni, Camille Laurent FR, Camille-Autonomie, Trenly, Premium Digital, Éditions Rémanence, Manuels Illustrés, Antoine Lefebvre Petit, Anna herrero, Cine SFX, Atelier dei Biscotti, Re.construirte, Accademia Acquerello, Success Food Truck, Renata almaral, Rosa Almeida, Autocolantes, Luxe Resin, Chef Tiago, Chef Marina, Rowan House Press, Anna Müller, Keksatelier, Spürbare Anatomie, Digital Books, Hellhörig |

Trampas nuevas: `sofort download` (DE) = short-dramas y apps; `pdf scaricabile` (IT) = solo Studio Facile; `acesso imediato` / `guia pdf` / `download imediato` (PT) = desborde brasileño en BRL; `pdf ratgeber` (DE) = lead magnets gratis.
Nodos nuevos propuestos para la cola: `esoterismo/tarot-guias-eu`, `manualidades/patrones-tricot-pt`, `jardineria/poda-frutales-pt`, `educacion/actividades-imprimibles-eu`, `idiomas/mapas-ilustrados-it`, `hogar/planner-limpieza-eu`, `manualidades/patrones-costura-fr`.

## Lo que no se pudo verificar
- Sin navegador: ningún `ad_snapshot_url` abierto (403 desde la nube); landings y precios de Die Kunst des Tarot e Isabel Martins no vistos; la API no trae la URL de destino.
- Si O Pomar vende PDF o libro impreso.
- Cohortes ocultas detrás del tope de 50: Die Kunst des Tarot (82), Rachel Bennett (68), Stitchy (59), learndigital.shop (102), Studio Facile (563), Mente Accademica (244), Angela Barros (84).
- Hueco en los destinos sugeridos (Rumania, Grecia, Italia) no medido con `ALL`.
