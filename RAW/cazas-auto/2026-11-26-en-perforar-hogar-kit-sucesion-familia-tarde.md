# Caza automática — EN · B perforar (tarde) · hogar/kit-sucesion-familia — 2026-11-26

Nodo elegido: el `superficial` más viejo con mercado EN que no es hijo de un padre ya perforado (2026-11-12, junto con `productividad/planillas-vida`; se tomó el primero de la tabla). El virgen `plantillas-reclamos-veteranos` sigue salteado (re-medición 30-11, mercado de veteranos sin destino).

Método: 6 subnichos × 5 kw × US/GB (60 consultas) + ALL en 2 ceros, con 3 subagentes de lectura (~60 conteos `page_ids` + país). Re-conteo propio: TryLamorial US, Trust Guard US, Thejourney.ie GB, Legaciesbydesign US, My Estate Kit GB. Hay 4 sondas de destino con ALL: TryLamorial en CA/AU/NZ/IE, `legacy planner` en CA/AU/NZ/IE/ZA, `quando non ci sarò` en IT y `cuando yo falte` en MX. Se hicieron 5 búsquedas web y se abrieron con WebFetch 4 páginas que cargaron: advertorial de Lamorial, la página de will kits de My LifeGuard y dos notas de prensa de The Journey. No cargaron thejourney.ie, trylamorial.com ni myestatekit.co.uk.

**Limitación de la API en esta corrida:** devuelve solo el título del link, las fechas y el snapshot. No trae el cuerpo del copy ni la URL de la landing. Los precios salen de los títulos y las landings de búsqueda web.

Corte de cohorte 7+: `ad_delivery_start_time` anterior al 2026-11-20 00:00 UTC. «30 d» = creados desde el 2026-10-27.

## Shortlist

### 1. Lamorial (TryLamorial) — 1377422908778640 — US (tarjeta) · GB
- [US](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=US&view_all_page_id=1377422908778640&search_type=page&media_type=all) · [GB](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=GB&view_all_page_id=1377422908778640&search_type=page&media_type=all)
- Cohorte 7+/activos: **US 39/≥50** (51 estimados; re-conteo propio de los 50 visibles). Tiene tandas el 14-10, 31-10, 01-11, 03-11, 06-11, 07-11, 10-11, 11-11, 12-11, 13-11, 15-11, 16-11 y 17-11 en cohorte, más 11 ads del 20 al 25-11. El ad más viejo es del 14-10 (44 d): «Everything They'll Need. In One Place.». **GB 10/12** (subagente; 42 d, 6 fechas).
- Página de marca sin persona. Los hooks son «Read this if your family would have no idea where to start 👆» (×6 el 01-11), «The planner that doesn't leave you guessing» (×9), «Everything They'll Need. In One Place» (×7), «They'll Be Fine. You Made Sure.», «Leave Nothing Unwritten.», «Not another blank planner.» y «Every page tells you what to write.». Ofertas: «Buy 1, Get 1 50% Off» y «Black Friday: 15% Off Every Planner».
- Embudo (WebFetch de [lamorial.com/pages/advertorial-funeral-director](https://lamorial.com/pages/advertorial-funeral-director)): un advertorial en primera persona de un «funeral director» anónimo que lleva al producto, el «Lamorial End of Life Planner & Journal». Es un planner **físico** anillado de 83 páginas, guiado: dice qué escribir en cada página (contraseña del teléfono, cadena de 2FA, accesos a cuentas). «No app, no subscription», envío gratis, BOGO 50 %. El advertorial no muestra el precio en número. → **FÍSICO cuyo mecanismo es el conocimiento** (qué anotar y en qué orden): se puede convertir a PDF imprimible o rellenable.
- Ya corre en el anglo secundario: 48 ads con ALL en CA/AU/NZ/IE.
- Hay un cluster con los mismos hooks (inferido, no probado): Helen Cartwright 1/≥50 US (blitz del 24-11, «Trusted by 100,000+ Families»), Modern Planning 5/7 US (91 d) y Anna Reid 4/9.
- Snapshots duplicados: [1111655581670973](https://www.facebook.com/ads/library/?id=1111655581670973) («Read this if your family…» ×6), [1396603568870170](https://www.facebook.com/ads/library/?id=1396603568870170) (el más viejo, 44 d).
- Score 1/4: ④ provisorio. ① 44 d, a un día de 45. ② 39, no 50. ③ ningún título llega a ×10 dentro de la cohorte.

## Veredicto provisorio
- **ENTRAR (modelar convirtiendo a digital) → México**, después Italia o Rumania. La pieza es un planner guiado «lo que tu familia va a necesitar saber», en PDF imprimible o rellenable, con los trámites del país.
- El anglo secundario (CA/AU/NZ/IE) ya está tomado por Lamorial y por clones irlandeses (Kinfold/The Kinfold, Thejourney.ie).
- Las sondas de una kw en IT y MX con ALL trajeron solo short-dramas y ruido: **el hueco no está confirmado**. Faltan 4-5 kw nativas por destino.
- El subnicho entero es SUBNICHO/saturado en US/GB: más de 15 operadores entre el 1-11 y el 26-11.

## Otros medidos (señales y descartes)
| Página | page_id | País | Cohorte/activos | Fechas | Más viejo | Qué es | Por qué no es tarjeta |
|---|---|---|---|---|---|---|---|
| Trust Guard | 309841585552351 | US | 28/28 | 4 (02-09, 25-09, 29-10, 11-11) | 84 d | «1 Will Kit. 5 Essential Planning Resources.» + «Veterans: Plan for Your Family» | patrón de will kit gratis que capta leads de seguros (igual a My LifeGuard: «no-cost will kits», «a licensed representative will deliver your kit»); no se confirmó que sea Trust Guard |
| Thejourney.ie | 438194642710874 | GB | 20/22 | 3 (18-09, 12-11, 26-11) | 68 d | «The Journey Folder», carpeta física de cuero sintético con pluma, creada por la abogada Jacquelyn Dunne (Cork); EUR; en IE «€10 off» | físico + autoridad con nombre (Filtro A dudoso); mismo molde que My Estate Kit |
| My Estate Kit | 1091977304009213 | GB | 27/27 | ≥10 | ~158 d (01-07) | ya tiene tarjeta (12-11) | **frenando**: era ≥50/50, ahora 27 y sin ads nuevos desde el 31-10 |
| LifeTrove | 412976791897772 | GB · US | GB 46/49 · US 0/≥50 visibles (147 est.) | 4 | 19 d | «Life Book», organizador físico de ticket alto («$88 Off») | físico de ticket alto; 2.ª página 61564675091960 apagada en GB |
| Noble Estate Guide | 659024560635857 | US · GB | ≥35/≥50 · 21/24 | 3 | 11 d | libro de living trust «$39.95», «Buy 2 for $59.95» | libro físico; cluster con Estate Law Insider (≥40/≥50, «I'm a Probate Attorney») y Garret Hilman (4/14) |
| Legaciesbydesign | 822519780933943 | US | 10/10 | 4 (02-06, 05-09, 12-11, 19-11) | 177 d | «Legacy Blueprint Binder System», «Black Women Secure Your Family's Future» | pasa la vara en número pero el formato es desconocido y uno de los títulos es «Payment Request»; embudo sin verificar |
| ICE Box Shop | 1378685645337212 | US | 20/21 | 3 | 16 d | «Organize Your Family's Paperwork», «Start With One Folder» | formato no claro (¿carpeta física?) |
| Left Tidy | 1222206180986857 | US · GB | 10/20 · 7/7 | 2 · 1 | 10 d · 28 d | guía/test de «family file»; EN + ES para hispanos de US; EUR; página reciclada («Grace Bennett – Gentle Tai Chi») | menos de 3 fechas (filtro zombi) |
| The Family Folder | 487465484456721 | US | 5/14 | 6 | 23 d | clon de los hooks de My Estate Kit | cohorte chica |
| Digital Prosperity Vault | 1381395985055437 | US | 6/24 | 3 | 16 d | checklists de herencia y Medicare, lead magnet | cohorte chica, gratis |
| Ultimate Living Trust Guide | 452465861275411 | US | 8/8 | 1 | 241 d | guía de living trust | una sola fecha (posible zombi) |
| IfEver | 1428320737039942 | US | 1/2 | 2 | 8 d | «printable family emergency binder», «All 3 for $14.99 · Instant download» | el único digital explícito; tester |
| Passing On | 1232702999921553 | GB | 1/5 | 2 | 9 d | «End of Life Planner Bundle», GBP | tester |
| The Aging Parent Guide | 1512730318581915 | US | 0/5 | 1 | 0 d | bundle «$39 (was $83)», EUR | recién nacido |
| Gently Settled | 1430117740188881 | GB | 0/25 | 1 | 1 d | BOGO 50 %, EUR | recién nacido, probable físico |
| Kinfold · The Kinfold | 1467055683157587 · 1414501678416126 | IE | n/c | — | ~3 d | «Will in a drawer? Your family needs a list too» | clones irlandeses nuevos (en la sonda de destino) |
| Excluidos | — | — | — | — | — | Nokbox (caja física), UK Be Ready y American Ready (prepper físico), Caregiver Today (físico), Payne's Education (marca personal), funerarias, aseguradoras, estudios jurídicos | Parent Planners for Neurodivergent Kids: nicho excluido, se ignora |

## Cobertura
| Subnicho | Keywords (US/GB) | Resultado |
|---|---|---|
| legacy-binder | `just in case binder`, `legacy binder`, `estate planning binder`, `in case of emergency binder`, `legacy planner` | solo sirven `legacy binder` y `legacy planner`; el resto son novelas y short-dramas |
| albacea-executor | `executor checklist`, `probate checklist`, `executor guide`, `when someone dies checklist`, `bereavement checklist` (ALL en US: cementerio, Leave It Sorted 0 activos) | `executor checklist` US y `executor guide` US/GB = las más limpias; muchos estudios jurídicos |
| funeral-ultimos-deseos | `funeral planning`, `final wishes`, `end of life planner`, `death planning`, `funeral wishes` | dramas, funerarias, seguros; solo Passing On (GB) |
| padres-mayores-cuidador | `aging parents`, `caregiver binder`, `elderly parents paperwork`, `caregiver planner`, `parents affairs` | `caregiver binder` y `elderly parents paperwork` sirven (US); GB vacío o ruido; ICE Box Shop, IfEver, Aging Parent Guide, Carents (GB, ebooks gratis, 6/6, 354 d) |
| documentos-testamento | `will template`, `estate planning kit`, `living trust kit`, `estate planning pdf`, `will kit` | `will` = verbo modal: miles de ads de ruido; libros de living trust (Noble, Estate Law Insider, Garret Hilman), lead magnets de abogados |
| legado-digital-organizador | `password organizer`, `digital legacy`, `important documents organizer`, `family emergency binder`, `household information binder` (GB = 0 → ALL: cementerio) | LifeTrove domina; libretas de dropship; prepper |
| Sondas de destino (ALL) | TryLamorial en CA/AU/NZ/IE (48); `legacy planner` en CA/AU/NZ/IE/ZA; `quando non ci sarò` IT; `cuando yo falte` MX | anglo secundario ocupado; IT/MX = solo ruido (no confirma hueco) |

Trampas nuevas: `just in case binder`, `in case of emergency binder`, `when someone dies checklist`, `end of life planner` US, `death planning`, `funeral planning`, `parents affairs`, `will template`, `will kit`, `living trust kit`, `digital legacy` (novelas, short-dramas, apps); `password organizer` e `important documents organizer` (libretas físicas de dropship); `quando non ci sarò` IT y `cuando yo falte` MX (dramas).

Nodos hijos: `legacy-binder`, `albacea-executor`, `funeral-ultimos-deseos`, `padres-mayores-cuidador`, `documentos-testamento`, `legado-digital-organizador`, todos `superficial`.

## Lo que no se pudo verificar
- No cargaron las landings de thejourney.ie, trylamorial.com ni myestatekit.co.uk (WebFetch sin permiso de origen). Tampoco se pudo leer ningún snapshot (403 desde la nube).
- Lamorial: el precio no aparece en número. El advertorial sí confirma que es físico.
- Trust Guard: no se encontró su landing; la lectura de lead-gen de seguros es por patrón.
- Legaciesbydesign, ICE Box Shop: no se sabe el formato.
- La API no trae el cuerpo del copy ni el link: la cara (Filtro A) se juzgó por el nombre de la página y los títulos.
