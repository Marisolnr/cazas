# Caza automática — ES · huella (A) · hispano (CO ES) — 2026-11-20

Corrida de la mañana (viernes = A huella). Países: CO y ES (decisión de Marisol del 17-11). 16 huellas nuevas
(distintas de las del 09, 10, 13 y 17-11), cada una × CO y ES = 32 consultas `search_terms`, más ~31 páginas
contadas con `page_ids` + un país (3 subagentes de lectura) y re-conteo propio de Rachel Bennett en ES, CO, MX, FR
y RO, más 2 sondas de destino (RO, GR).

**Límite de la API hoy:** igual que en las corridas anteriores, la API solo devolvió `ad_creative_link_title`, la
página, las fechas, la moneda y el `ad_snapshot_url`. No trajo el texto del creativo ni la URL de destino, así que
**ningún embudo se pudo verificar desde la nube** y el precio solo se ve cuando está en el título.

## Shortlist

### 1. Rachel Bennett — «+500 actividades de planificación para Inicial / preescolar» (multi-idioma)
- page_id `280579905138659`. Links:
  [ES](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=ES&view_all_page_id=280579905138659&search_type=page&media_type=all) ·
  [CO](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=CO&view_all_page_id=280579905138659&search_type=page&media_type=all)
- **ES: cohorte 7+ 21 / ≥50 visibles (76 estimados).** Tandas visibles: 11-11 (6, IT), 13-11 (10 en español
  «Tu planificación de Inicial lista: +500 actividades a $9.90» + 5 en alemán), 15-11 (5 IT), 17-11 (5 DE),
  19-11 (8 PT), 20-11 (8 ES + 3 IT). Los 26 estimados que no entran en el tope de 50 serían más viejos: la cohorte
  real es mayor (21 es piso).
- **CO: cohorte 7+ 18 / 19** (todo en español, «Inicial», $9.90): 8 del 02-11 (18 d), 10 del 13-11, 1 del 20-11.
- MX: 25 estimados (español). FR: 52 estimados y RO: 49 estimados, pero con los mismos ads en italiano, alemán y
  portugués: la segmentación es amplia, Europa + LatAm, con creativos en 4 idiomas (ES, IT, PT, DE).
- Precio en el título: **$9.90** (versión español) y **5 €** (IT/PT/DE, «Oggi solo 5 €», «hoje só 5 €»).
- Zombis por API: 6 fechas distintas en ES, 3 en CO; ads creados hoy (20-11) → operador vivo. Pasa.
- Tipo de página: nombre de persona, pero corre la misma oferta en 4 idiomas con títulos de producto, sin
  autoridad ni «mi método» en los títulos. Por el caso Ana Valentina Lima (SKILL.md), un nombre de persona solo no
  alcanza para marca personal. **No se pudo ver si el creativo usa una cara: verificar en la PC.**
- Embudo: no verificado desde la nube (la API no trae URL).
- Hook: «Tu planificación de Inicial lista» / «Deine Kita-Planung ist fertig» → la docente de nivel inicial que no
  quiere armar la planificación desde cero.
- Snapshots: más viejo en CO [02-11](https://www.facebook.com/ads/library/?id=1825883255210771) · tanda del 13-11
  en español [ad](https://www.facebook.com/ads/library/?id=1294908656154421) · alemán
  [ad](https://www.facebook.com/ads/library/?id=2367774614055087).
- Duplicación: el mismo título ×18 dentro de la cohorte en CO y ×10 en ES (versión español) → por título; el
  creativo no se vio.
- Score: longevidad 0 (18 d) · volumen 0 (21 piso, no 50) · duplicación 1 (×18 por título) · hueco 1 (RO, 1 kw)
  = **2/4 → observar/B**. Pasa la vara de tarjeta (≥10 de un solo page_id en CO y en ES).

## Veredicto provisorio
**Observar → ENTRAR en destino.** El operador ya cubre ES, IT, PT, DE y LatAm en español: no se le compite en esos
idiomas. Par fuente → destino: **ES/CO → Rumania** (en rumano): con `activități grădiniță` RO aparecen juguetes
físicos (Jumbolino), jardines de infantes (servicio), libros físicos (Seladin) y un solo tester digital de 0 d con
otro SKU (Atelierul Educatoarei, «55 jocuri scurte pentru tranziții»). Segunda opción: **Grecia**, pero con
`δραστηριότητες νηπιαγωγείου` GR ya aparece **Mesa Ligera** (página con nombre en español) con «Όλη η χρονιά στο
νηπιαγωγείο: 200 δραστηριότητες» (2 ads de 4 d): un clon hispano traduciendo al griego, la ventana se está abriendo
para otros. Nicho: docentes de inicial, no neurokids (es planificación de aula para la maestra, no terapia).

## Señales (sin tarjeta)
- Planner Hoy Solo 3 (1280820831792286): **ES 39/49** (13 fechas, 21-10 a 19-11). Ya tuvo tarjeta el 10-11 (21/35)
  y 30/41 el 12-11: sigue creciendo y no apagó tandas.
- Mente Ordenada (1084424138077543): CO 0/16, «Vacía tu cabeza en 10 minutos» (16-11): clon del planner de vaciar
  la cabeza. Re-medir 2026-11-27.
- Atelio Guides (1363006713573237): ES 0/≥50 (67 est.), multiproducto (razas de perro, carpeta familiar/testamento,
  crianza), tandas del 13, 16, 19 y 20-11. Fábrica joven: re-medir 2026-11-27.
- Master Educativo MegaPacks (109636082179917): ES 0/≥50 (66 est.), megapacks educativos, tandas 16-19-11.
  Re-medir 2026-11-27.
- Gestión Profesional con Excel (961233043748737): CO 5/8 (76 d, 5 fechas): plantillas Excel, longevo pero chico.
- Mega Plantillas Digitales (1154408571089804): CO 4/12 (85 d), invitaciones y plantillas.
- Binestar y Belleza (811240618733828): CO 6/15 (41 d). Mezcla Agenda Devocional 2027 con kits infantiles que rozan
  nichos excluidos: no se sigue.
- Biblioteca Creativa (1244762302063129): CO 3/22 (42 d). Operador con tarjeta del 10-11: la cohorte bajó.
- Krealia Digital (1444897762040749): CO 2/10 (dibujo manga, coreano desde cero). Re-medir 2026-11-27.
- Companhia Cozinhando Bem 0/13 y Cocina con ElsyShop 0/20 (recetarios, CO), Renda Extra 0/21 (CO, BRL): todo de
  0-5 d.

## Cobertura

| Huella | País | ACTIVE | Qué trajo |
|---|---|---|---|
| `acceso inmediato` | CO | 50 (11.168 est.) | ~45 de un short-drama; Educación Digital, Recursos Élite |
| `acceso inmediato` | ES | 50 (8.326) | el mismo short-drama; certificaciones de fisio a 397 €, Modo Praktica (ebooks) |
| `hotmart` | CO | 50 (4.233) | negocio digital con marca personal, clases en vivo; Nido Infantil, Mi Recetario Saludable |
| `hotmart` | ES | 50 (1.796) | afiliados y personas; Sapo Zen (77 €), una agenda 2027 |
| `link de descarga` | CO | 50 (785) | Netshort (short-drama), Temu, apps |
| `link de descarga` | ES | 50 (501) | short-dramas, apps; Mástil Claro, Nua Studio |
| `descarga inmediata` | CO | 50 (2.616) | **buena**: Escenario Pro, Biblioteca del Pastor, Páginas Católicas, Naim Lux, PMBOK |
| `descarga inmediata` | ES | 50 (1.695) | **buena**: Atelio Guides, Biblioteca Tech, La Escalera del Lenguaje |
| `kit digital` | CO | 50 (2.331) | físicos y ciberseguridad; Mega Plantillas, Krealia, Portal da Pedagogia |
| `kit digital` | ES | 50 (1.652) | **trampa**: la subvención estatal «Kit Digital» (agencias); algo de infoproducto |
| `plantillas editables` | CO | 50 (775) | **buena**: Canva, papelería, kits profesionales y jurídicos |
| `plantillas editables` | ES | 50 (416) | papelería navideña, Canva; Bendiciones creativas ×16 «RECÍBELO GRATIS» |
| `guía completa` | CO | 50 (7.324) | ~25 short-drama; recetas PDF, guías bíblicas |
| `guía completa` | ES | 50 (5.796) | ~35 short-drama; viajes |
| `manual práctico` | CO | 50 (798) | Renda Extra, Faradayos, cursos de fisio; físicos |
| `manual práctico` | ES | 50 (502) | Faradayos, Kine Práctico, Manual de Instalaciones; físicos y autos |
| `mini curso` | CO | 50 (428) | marca personal, short-dramas, microcursos por WhatsApp a $5.000 COP |
| `mini curso` | ES | 50 (297) | basura: short-dramas, lead magnets, academias |
| `clases grabadas` | CO | 50 (1.577) | capacitaciones médicas, «Dra.»: casi nada de infoproducto |
| `clases grabadas` | ES | 50 (1.117) | basura: oposiciones, universidades |
| `actividades navidad` | CO | 50 (532) | rifas, ecommerce, eventos; algo digital (Marina Duarte, Navidad Mágica Digital) |
| `actividades navidad` | ES | 50 (333) | juguetes físicos; Aprende con Nico (8,99 €), Sunlit Steps |
| `fichas PDF` | CO | 50 (932) | **buena**: kits TCC, Silhouette, péptidos, radiestesia, contabilidad |
| `fichas PDF` | ES | 50 (953) | **buena**: Atlas de Gramática, Rachel Bennett, Silhouette, logopedia |
| `cuaderno imprimible` | CO | 39 (39) | **buena**: Mente Ordenada, bible journaling, primeras letras |
| `cuaderno imprimible` | ES | 50 (52) | **buena**: Planner Hoy Solo 3, Atelio Guides, calendario de Adviento emocional |
| `recibe WhatsApp` | CO | 50 (45.247) | ruido: inmobiliarias, Black Friday, ganadería |
| `recibe WhatsApp` | ES | 50 (7.748) | basura: k-dramas, bolsa |
| `formato digital` | CO | 50 (1.321) | mezcla digital: Portal da Pedagogia, Naim Lux, ElsyShop, kits TCC |
| `formato digital` | ES | 50 (644) | Salud Didáctica, kit EMDR, cursos de software |
| `PDF €` | CO | 50 (14.951) | apps lectoras de PDF (basura); Nido Infantil, Latam Digital |
| `PDF €` | ES | 50 (18.586) | lectores de PDF; Learn with Method, Aula Digital Pro |

Sondas de destino (para Rachel Bennett): `activități grădiniță` RO (15 vistos, 155 est.): juguetes, jardines,
libros físicos, 1 tester digital 0 d · `δραστηριότητες νηπιαγωγείου` GR (9 est.): Mesa Ligera 2 ads 4 d con «200
δραστηριότητες», un seminario, jardines.

Páginas contadas con `page_ids` + país: ~31 (subagentes) + Rachel Bennett en ES, CO, MX, FR, RO (propio).

Trampas nuevas: `acceso inmediato` / `guía completa` / `link de descarga` (short-dramas) · `kit digital` ES (la
subvención estatal) · `mini curso` / `clases grabadas` (academias, marcas personales) · `recibe WhatsApp` (ruido de
45 mil) · `PDF €` (apps lectoras de PDF). Rinden: `descarga inmediata`, `fichas PDF`, `cuaderno imprimible`,
`plantillas editables`, `formato digital`.

Nodos nuevos propuestos para la cola: `docentes/planificacion-inicial` (ES, superficial; apareció por huella el
2026-11-20).

## Lo que no se pudo verificar
- Embudo y precio real de Rachel Bennett (la API no trae URL ni copy). Si el creativo muestra una cara.
- Ningún snapshot verificado desde la nube (403); longevidad por API.
- La cohorte ES de Rachel es un piso (tope de 50; 76 estimados).
