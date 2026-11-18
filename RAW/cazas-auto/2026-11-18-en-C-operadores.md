# Caza EN · 2026-11-18 · C operadores (mañana)

Sesión EN en la nube, miércoles → modo C operadores. La agenda del hub está vacía, así que se barrió la tabla
«Operadores a seguir» con mercado US/GB: todos los operadores EN, las re-mediciones vencidas o de esta semana
primero, y los ya tarjeteados solo para ver si hay SKU nuevo, si crecieron o si se apagaron.
Corte de cohorte: `ad_delivery_start_time` ≤ 2026-11-11 09:40 UTC. `ACTIVE`, `limit 50`, un país por consulta.
4 subagentes de lectura (~100 consultas `page_ids` + país, ~10 sondeos `search_terms`) + re-conteo propio de
The Printed Kitchen GB, Presence College GB y Mary Simmons US + controles de destino (IE/AU/CA/NZ por page_id; MX
con `mezclas caseras recetas` y `plan de cenas semanal` en ALL).

Limitación de hoy: la API devolvió solo `ad_creative_link_title`, fechas, moneda y snapshot (sin cuerpo ni URL).
Ninguna landing se pudo verificar con WebFetch: las búsquedas web de «The Printed Kitchen» y del título de Mary
Simmons/Claudia Williams no devolvieron la tienda.

## Shortlist

### 1. The Printed Kitchen (1242454385622632) · GB
- [Ads Library GB](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=GB&view_all_page_id=1242454385622632&search_type=page&media_type=all)
- Cohorte 7+/activos **22/22** (conteo completo, est. 22). El más viejo: 02-10 (47,1 d), [2576255526134418](https://www.facebook.com/ads/library/?id=2576255526134418).
- Escalonamiento: 4 fechas de creación (02-10 ×9, 27-10 ×1, 09-11 ×1, 10-11 ×11). La última fue hace 8 d, así que el operador está vivo.
- Ofertas: «Four weeks of dinners, already planned» **14/14** (9 del 02-10 + 5 del 10-11); «Gluten-free sourdough, step by step» 6/6 (10-11, SKU nuevo); «One shop. Five dinners. Sorted.» 2/2.
- Moneda GBP. Página de marca, sin persona. Formato sin ver: el nombre «Printed» puede indicar un producto impreso.
- Solo corre en GB: en US da 0 con ALL, y en IE/AU/CA/NZ da 0 activos.
- Score: ① sí (47 d) · ② no · ③ sí (14 en cohorte) · ④ probable en IE/AU/NZ (el operador no está; no se midió la competencia local) → 2/4.

### 2. Mary Simmons (1090803100784042) + Claudia Williams «The Dry Mix Mom» (1360700847131953) · US
- [Mary Simmons US](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=US&view_all_page_id=1090803100784042&search_type=page&media_type=all) · [Claudia Williams US](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=US&view_all_page_id=1360700847131953&search_type=page&media_type=all) · [Graceshopfinds US](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=US&view_all_page_id=1225217784003234&search_type=page&media_type=all)
- **Mary Simmons: 40/40** (conteo completo, est. 40). El más viejo: 16-10 (32,9 d), [2500734220419856](https://www.facebook.com/ads/library/?id=2500734220419856). Tiene 6 fechas (15, 16, 24, 25, 26 y 28-10). Último ad hace 21 d, así que pasa el filtro de zombi, aunque sin tanda nueva en 3 semanas.
  - Ofertas: sin título 22/22; «Bring Mediterranean Flavors to Your Table» 10/10; «Bring Gluten-Free Flavors to Your Table» 8/8.
- **Claudia Williams: 36/≥50** (piso, est. 165). El más viejo: 20-10 (28 d), [2038246323646277](https://www.facebook.com/ads/library/?id=2038246323646277). Tiene 7 fechas, la última el 15-11.
  - Ofertas: «Your Pantry Can Replace The Box Aisle» 22/25; «Bring Mediterranean…» 7/8; «Bring Southern Favorites…» 3/12; «More Protein…» 0/1 (nuevo).
- Graceshopfinds: 0/50 piso (est. 361), con los mismos títulos. Rota a diario y no se le ve la cohorte.
- Tres páginas con títulos idénticos: es un operador con fachadas, no una marca personal consolidada. Dos de las páginas tienen nombre de persona («Mom»), pero no hay caras verificables por API.
- Moneda USD. Formato sin ver (recetario de mezclas secas y sabores por cocina; puede ser libro impreso).
- No corre en GB ni en IE/AU/CA/NZ.
- En MX hay testers en español (Warehousy «Cuatro pasteles con un solo frasco», MXN; Recetas Al Rescate «El sazón que cambia todo», 8 ads de 0-6 d). Ninguno tiene cohorte visible.
- Score: ① no (33 d) · ② no · ③ sí (22 duplicados en Claudia, 22 sin título en Mary) · ④ probable → 1-2/4.

## Veredicto provisorio
- The Printed Kitchen → ENTRAR, llevándolo tal cual en inglés a **Irlanda** y **Australia/Nueva Zelanda**. Primero hay que verificar en la PC que sea PDF.
- Mezclas secas (Mary Simmons + Claudia Williams) → ENTRAR con un recetario digital en **Italia** o **Portugal**. En el mercado hispano hay testers en MX sin cohorte. Primero hay que verificar en la PC que no sea un libro impreso.

## Cobertura

Conteo de los operadores EN. Los tarjeteados antes van solo como seguimiento.

| Página | page_id | País | Cohorte/activos | Est. | Ad más viejo | Fechas/última | Nota |
|---|---|---|---|---|---|---|---|
| Donna Whitfield | 1180278161845468 | US | 0/50 | 204 | 6 d | 6 / 18-11 | rota; persona en primera persona («my husband») |
| The EaseUp Planners | 1194131877121706 | US | 0/50 | 149 | 2 d | 1 / 15-11 | relanzó de nuevo |
| Stitch Well | 684792994717005 | US · GB | 0/50 · 0/50 | 591 · 554 | 1 d | 1-3 | rota a diario |
| Elsie Brooks | 269275822943681 | US | 0/50 | 577 | 1 d | 2 | mismo molde |
| Visual Guide Lab | 1467890346400480 | US | 0/50 | 170 | 1 d | 2 | rota |
| In pictures books | 1354208894450767 | US | 0/50 | 184 | 6 d | 1 | 11 oficios ×5 |
| Illustrated Manuals | 1459350803924436 | US | 9/50 piso | 51 | 10 d | 9 / 16-11 | SIE 4/11; USMLE nuevo |
| Food Storage Tips | 724248187440810 | US | 0/50 | 317 | 6 d | 2 | suena a físico |
| Revelation Unsealed 3D | 1345541285309886 | US | 8/22 | 22 | 43 d | 8 / 17-11 | sigue < 10 |
| HeroeDigitals | 1258628903995580 | US | 29/38 | 38 | 26 d | 6 / 18-11 | fútbol, títulos tipo app; natación nueva 0/4 |
| Claudia Williams | 1360700847131953 | US | 36/50 piso | 165 | 28 d | 7 / 15-11 | → tarjeta (con Mary Simmons) |
| Graceshopfinds | 1225217784003234 | US | 0/50 | 361 | 1 d | 2 | mismos títulos |
| Mary Simmons | 1090803100784042 | US · GB | 40/40 · 0 (ALL) | 40 | 33 d | 6 / 28-10 | → tarjeta |
| Soccer Training Pro | 1234094106455284 | US | 22/22 | 22 | 91 d | 8 / 29-09 | posible zombi (50 d sin ads nuevos) |
| Recipes From The Bible | 1523445677509859 | US · GB | 0/50 · 0/50 | 624 · 567 | 2 d | 3 | rota; mismos creativos que Cooking With Jesus |
| Cooking With Jesus | 1485183781338862 | US | 0/50 | 601 | 2 d | 3 | ídem |
| Chef Anna Collins | 1283746054814175 | US | 13/29 | 29 | 18 d | 4 / 16-11 | nombre de persona; «Thanksgiving Offer» |
| **The Printed Kitchen** | 1242454385622632 | GB · US · IE/AU/CA/NZ | **22/22** · 0 (ALL) · 0 | 22 | 47 d | 4 / 10-11 | → tarjeta |
| The Cookbook Store | 1347654908420844 | GB | 17/50 piso | 62 | 11 d | 4 / 18-11 | físico («Delivered to Your Door») |
| The Light Table Kitchen | 1336852769517463 | GB | 0/5 | 5 | 1 d | 1 | |
| Soul Made Press | 290857440783698 | US | 13/22 | 22 | 65 d | 11 / 17-11 | repartido; «Bible Study Workbook» nuevo 0/6 |
| Eureka.labs | 1093038623903745 | US | 20/27 | 27 | 53 d | 9 / 18-11 | repartido; tarot nuevo 0/4 |
| The art of tarot | 1395155533680469 | GB · US | 25/50 · 25/50 piso | 102 · 101 | 13 d | 13-14 | red ya vista con EU |
| Presence College | 553429274518110 | GB | 31/50 piso | 56 | 30 d | 6 / 17-11 | «Get Instant Access» 31/31 (4 tandas); BF «80% OFF + FREE ebook» 0/19; producto invisible |
| Afterpath | 1016389298235387 | US | 5/8 | 8 | 16 d | 4 | |
| Ultimate Notion Planner | 425210960671076 | US | 13/13 | 13 | 22 d | 1 / 27-10 | 1 sola fecha → no cumple ≥3 |
| Download Studio | 1344017652136102 | US | 0/50 (23/39 con `Planned`) | 115 | 14 d | 8 | repartido entre SKUs |
| Creative Library | 1362229870302077 | US | 2/3 | 3 | 27 d | 3 | BRL |
| The Custody Keeper · Shielded · AntiAlienate | 1366011646600864 · 1280648655122547 · 1066259219910194 | US | 0/0 · 3/5 · 0/0 | | | | apagados o mínimos |
| Fingerstyleguitarschool | 109749731564018 | US · GB | 31/34 · 31/34 | 34 | 46 d | 7 / 17-11 | Starter Kit 4/7 |
| Acordes en Claro | 1205940002609789 | US | 0/50 | 702 | 2 d | 2 | abrió oferta en inglés (fretless, «226 pages») |
| Honey Home | 1334135786448993 | US | 2/5 | 5 | 8 d | 2 | se cae; guía de manchas 0/3 |
| Dragon Fire Method | 163589696835008 | GB | 34/50 piso | 62 | 50 d | 15 | SKU nuevos < 10 |
| Your Consulting Management Guide | 1097413493462052 | US · GB | 37/40 · 29/30 | | 130 d | 12 · 7 | estable |
| Linda Harrison | 778821148649074 | US | 32/34 | 34 | 54 d | 15 | estable |
| Heroic Husband | 234796816378250 | US | 30/50 piso | 59 | 79 d | 6 | sin SKU nuevo |
| This & That Planners | 1007996855726476 | US | 0 (ALL 12, último 02-10) | | | | apagada |
| Planner Lovers | 128972030308501 | US | 29/29 | 29 | 20 d | 2 | |
| Knitting Art Studio | 852298534641160 | US | 0 (ALL 0) | | | | apagada |
| The Crochet Nook | 534358449768435 | GB | 18/28 | 28 | 292 d | 7 | cárdigan mariposa 7/8 (+10 sin título) |
| Sewing Lovers | 1341379315722832 | US | 0 (ALL 48, último 12-11) | | | | apagada |
| RootedinFaith | 1339338722596915 | GB | 2/39 | 39 | 12 d | 4 / 18-11 | relanzó («God's Word Made Simple» 0/32) |
| My Estate Kit | 1091977304009213 | GB | 41/41 | 41 | 148 d | 17 | estable |
| Cosmo Studio | 209343218938190 | US | 21/35 | 35 | 79 d | 5 | SKU patrón crochet PDF 0/13; Canva ya no aparece |
| The Ascent Club | 102421131594782 | US | 0/50 | 246 | 5 d | 4 | muchos verticales nuevos, ninguno en cohorte |
| CustodyLogs | 959544217247977 | US | 35/44 | 44 | 278 d | 19 | estable |
| Isabella Francis | 201865639680760 | US | 30/35 | 35 | 95 d | 6 | un título dice «Paperback» |
| Basketball Coach Pro | 1373186709203115 | US | 27/31 | 31 | 44 d | 6 | |
| Digital Academy (EF) | 1340771395780798 | US · GB | 23/25 · 22/23 | | 16 d | 5 | creció |
| The Lost Skills of Independence | 984264748113661 | US | 0/50 | 810 | 2 d | 2 | rota |
| Fallback Book | 1388539597681148 | GB | 14/14 | 14 | 18 d | 3 / 02-11 | sin ads nuevos en 16 d |
| The Beauty Crafts | 889621137558075 | GB · US | 45/50 · 42/50 piso | 77 · 83 | ≥86 d | 10 · 9 | primer conteo en US; línea capilar 11/11 GB, 10/10 US |
| Pattern Quilt Studio | 1218499961347502 | US · GB | 0/34 · 0 | 34 | 0 d | 1 | relanzó todo el 17-11; nunca corrió en GB |
| Elisabeth.says | 973401275857984 | US | 34/43 | 43 | 68 d | 17 | |
| Nonna Sweets | 1519806301205219 | GB · US | 32/45 · 31/50 | 45 · 60 | 12 d | 5 | |
| Relief On Every Plate | 1191202924084648 | US | 37/48 | 48 | 78 d | 11 | |
| Realifestation | 1345136965345763 | US | 41/46 | 46 | 56 d | 7 | |
| Emily D | 992566507281610 | US | 20/32 | 32 | 40 d | 5 | |
| Valentina Ríos | 1280761195116636 | US | 9/21 | 21 | 7 d | 2 | cambió a «Make your own mini Bibles at home» (BRL) |
| My Nurse Notes | 107734932379817 | US | 34/34 | 34 | 137 d | 5 / 05-11 | |
| LCSW Strategy | 1071328126064642 | US | 21/21 | 21 | 159 d | 13 | Retaker's Edition bajó a 1 |

Controles de destino:
- `mezclas caseras recetas` MX (ALL, 755 est.): testers de 0-6 d, sin cohorte.
- `plan de cenas semanal` MX (ALL, 490 est.): Despensa de un Año, Sanito Gourmet, «1000+ recetas en PDF US$1.99»; ninguno con el molde «4 semanas de cenas ya planificadas».
- `dinners already planned` AU: solo short-dramas (trampa).
- `dry mix recipes` MX: ruido navideño y short-dramas.

Trampas nuevas: `dinners already planned` (AU) trae short-dramas «Novels Lover».
Nodos nuevos propuestos: ninguno (ambos caen en `recetas/`).

## Lo que no se pudo verificar
- No se vieron las landings (la API no trajo URL) ni el formato (PDF o impreso) de las dos tarjetas.
- Tampoco se vio el producto de Presence College.
- Las cohortes de las páginas que rotan a diario (Stitch Well, Elsie Brooks, Graceshopfinds, Lost Skills, Recipes From The Bible, Acordes en Claro y Ascent Club) no se pueden medir por API.
