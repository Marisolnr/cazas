# Cola de caza — el árbol de nichos

Fuente de trabajo del programa de caza automatizado ([[automatizar-la-caza-de-winners]]). Cada sesión
(EN · BR · ES) elige de acá **qué** cazar y en **qué modo**, y al terminar actualiza su nodo.

> ⛔ **Regla madre: el cero no descarta.** Un nodo pasa a `descartado-eje` solo después de (a) 4-5
> keywords nativas, (b) un nivel de subnichos perforado (modo B) y (c) `ad_active_status: ALL` mirado.
> Antes de eso vuelve como `superficial`. Los 🔴 los pone **Marisol**, nunca una sesión automática.

## Estados

| Estado | Significa | Qué hace la sesión con él |
|---|---|---|
| `virgen` | nunca se barrió | **prioridad 1** — modo A o B |
| `superficial` | se barrió con pocas keywords o un solo mercado | **prioridad 2** — modo B (perforar) |
| `profundo` | 4+ keywords nativas por mercado, subnichos mirados | solo modo C (operadores/agenda) |
| `ENTRAR` | hay molde y destino; el producto está en el catálogo o en camino | modo C: vigilar la ventana |
| `propio` | producto nuestro vivo en el nicho | modo C: vigilar competidores |
| `descartado-eje` | ese eje, en esos mercados, no da infoproducto modelable | no se toca; los hermanos sí |
| `🔴` | descarte permanente del dueño | no se toca |
| `🟡 <fecha>` | revisable en fecha | modo C cuando llega la fecha |

**Orden de elección:** `virgen` más viejo → `superficial` más viejo → `🟡` vencido. Dentro del mismo
estado, primero el nodo cuyo mercado coincide con la sesión. Una sesión no repite un nodo que otra
sesión tocó en los últimos 7 días.

---

## El árbol

Cargá acá tus nichos. Un nodo por nicho o subnicho (`nicho/subnicho`). Las keywords literales viven en
la página del nicho de tu wiki; acá va el conteo y la fecha. La columna Mercados dice a qué sesión
le toca (EN · BR · ES). Si el árbol está vacío, las sesiones arrancan en modo A (huella) y lo van llenando con
los nichos que emergen.

| Nodo | Padre | Mercados | Estado | Cobertura | Próxima acción |
|---|---|---|---|---|---|
| neurokids | — | todas | 🔴 | — | **EXCLUIDO por el dueño en la instalación: no se busca, no se perfora, no se agrega como hijo** |
| hogar/planner-limpieza | hogar | EN | superficial | 1 kw EN (printable planner) + 1 control AR/ES · 2026-11-09 | apareció por huella el 2026-11-09 (Honey Home 15/25 US); perforar por formato (sistema / por habitación / rutinas) |
| educacion-profesional/contabilidad-workbooks | educacion-profesional | EN | superficial | 1 kw GB (£27 pdf) + 1 control AR/ES · 2026-11-09 | apareció por huella el 2026-11-09 (Practical Accounting Kit 21/31 GB); perforar por avatar (estudiante / pyme / liquidación de sueldos) |
| ciberseguridad/plantillas-nist | ciberseguridad | EN | profundo | 24 kw nativas US/GB + ALL en ceros + control AR/ES · 2026-11-09 | modo C: seguir a Dragon Fire Method; perforado el 2026-11-09 |
| ciberseguridad/plantillas-nist/nist | ciberseguridad/plantillas-nist | EN | profundo | 4 kw · 2026-11-09 | un whale (Dragon Fire Method); tarjeta 2026-11-09 |
| ciberseguridad/plantillas-nist/iso-27001 | ciberseguridad/plantillas-nist | EN | superficial | 4 kw · 2026-11-09 | cementerio: kits ISO solo con ads inactivos (ISO 27001 PRO LLC, Stratovik) |
| ciberseguridad/plantillas-nist/soc2-politicas | ciberseguridad/plantillas-nist | EN | superficial | 4 kw · 2026-11-09 | ruido SaaS; solo Dragon Fire |
| ciberseguridad/plantillas-nist/incident-response | ciberseguridad/plantillas-nist | EN | superficial | 4 kw · 2026-11-09 | DR/BC = hueco con ALL; IR solo Dragon Fire |
| ciberseguridad/plantillas-nist/hipaa | ciberseguridad/plantillas-nist | EN | superficial | 4 kw · 2026-11-09 | SaaS y MSP; Gamma Compliance Solutions 6/6 (ads de hasta 823 d) |
| ciberseguridad/plantillas-nist/estudio-examen | ciberseguridad/plantillas-nist | EN | superficial | 4 kw · 2026-11-09 | CISSP = cementerio; Security+ es una trampa |
| examenes-ilustrados | educacion-profesional | EN | virgen | — | apareció por huella el 2026-11-09 (Visual Guide Lab, In pictures books, Illustrated Manuals: volumen sin cohorte); re-medir desde 2026-11-16 |
| planners-imprimibles-2027 | hogar | EN | virgen | — | apareció por huella el 2026-11-09 (Bindwell, Guías Vitales); estacional, ventana hasta enero |

---

## Trampas de keyword (no se repiten)

Cada sesión la lee antes de generar keywords y **agrega** las que descubre.

| Keyword / patrón | Por qué falla | Qué usar |
|---|---|---|
| `book` `novel` `read` (EN) | short-dramas (cientos de miles de resultados) | entregable + tema |
| `Google Sheets` / `sheets` | short-dramas | pares: `spreadsheet template`, `planilha controle` |
| keywords idénticas en ES/IT/PT (`farmacologia`, `peptide`, `dietoterapia`) | el mercado parece 3-8× más grande | la palabra que **no** se comparte; leer el idioma de cada creativo |
| siglas cortas (`EKG`) | spam de webnovelas | frase de 3+ palabras |
| préstamos del inglés (`barista`, `latte art`, `Meal Prep`) | traen anunciantes de otros países | la palabra nativa |
| keywords amplias en nichos de churn | solo devuelven las últimas 48 h | **angosto para ver la cola** |
| frases largas en `search_terms` | el matcher es **AND por token** | pares de palabras |
| huellas anchas en 🇧🇷 (`acesso imediato`, `apostila`, `kiwify`, precios) | decenas de miles de ads, los 50 primeros son de hoy: sirven para leer nombres de página, no para medir | barrer → anotar ~30 páginas → contar cada una con `page_ids` + `countries`; rinden `guia prático pdf`, `planilha pronta`, `ebook completo`, `material digital` |
| bloque `es` sin BO / EC / GT | subcuenta a los operadores andinos | `countries: ["MX","CO","AR","PE","CL","BO","EC","GT","ES"]` |
| `ad_creation_time` viejo sin impresiones | ads zombis | abrir el snapshot: «isn't in the Ad Library / no impressions» no cuenta |
| follow ads («Visit Instagram profile») | infl an la longevidad | la longevidad se lee **sobre el ad que vende** |
| `limit: 50` que devuelve 50 ads de hoy | cohorte truncada | reportar como piso, repetir con `page_ids` + `countries` |
| snapshot sin espera | `get_page_text` devuelve solo el encabezado | `wait` 4 s antes de leer |
| landing de operador 🇧🇷 | geo-redirige por idioma | el precio del mercado cazado se mira desde el checkout |
| página que devuelve **0 con `ALL`** | no está pausada: ya no existe | anotarla como desaparecida |
| un whale migra de página sin apagar el negocio | contar solo la página madre lo da por muerto | contar también las páginas hermanas de su ficha |
| barrido por keyword en EN (`printable`, `instant download`) | la API los ordena del más nuevo: casi todo tiene < 2 d y la cohorte no se ve | usar la huella para leer nombres de página y contar cada una con `page_ids` + `countries` |
| `protocol` / `blueprint` (EN) | suplementos, advertoriales con persona, granjas de juegos y dramas | entregable + tema |
| `printable` solo (GB) | quiz-funnels de dieta (Eat Smart, High.diet) | `printable planner`, `printable pages` |
| `Security+` (EN) | el «+» se pierde y trae «security guide» (guardias, ficción) | `CompTIA Security` |

## Operadores a seguir (modo C)

Fábricas multi-SKU y whales que muestran el próximo producto antes de que aparezca por keyword. Se
enumeran con `page_ids` + `countries`, siempre con el país. Cadencia: quincenal salvo que diga otra cosa.

| Operador | page_id | País | Por qué se lo sigue |
|---|---|---|---|
| Visual Guide Lab | 1467890346400480 | US | libros ilustrados para exámenes, mucho volumen sin cohorte (2026-11-09); mismo molde que In pictures books 1354208894450767, Illustrated Manuals 1459350803924436 y Avenlo 1434008009790850 (en español) |
| Honey Home | 1334135786448993 | US · GB | tarjeta del 2026-11-09: ver si la cohorte sigue creciendo |
| Dragon Fire Method | 163589696835008 | GB · US | whale de plantillas NIST/infosec, tarjeta del 2026-11-09 |
| Your Consulting Management Guide | 1097413493462052 | US · GB | 47/50 en cohorte (2026-11-09), no se sabe qué vende |
| | | | |

## Rotación vigente

| Día | EN | BR | ES |
|---|---|---|---|
| Lun | A huella | B perforar | C operadores |
| Mar | B perforar | C operadores | A huella |
| Mié | C operadores | A huella | B perforar |
| Jue | A huella | B perforar | C operadores |
| Vie | B perforar | C operadores | A huella |
| Sáb | C agenda | A huella | B perforar |
| Dom | lint de la cola | lint de la cola | lint de la cola |

La corrida de la tarde siempre es **B perforar** (`cazas/nube/NUBE.md` §5).

## Bitácora de la cola

Una línea por sesión, la más nueva arriba. La sesión la escribe **antes** de cazar (con «en curso») y
la completa al terminar.

| Fecha | Sesión | Modo | Nodo | Keywords corridas | Resultado | Nodo queda en |
|---|---|---|---|---|---|---|
| 2026-11-09 | BR | A huella (lunes toca B, pero no hay nodo BR en la cola → A) | — (huella, BR) | en curso | en curso | en curso |
| 2026-11-09 | EN | B perforar (2ª corrida, prueba manual) | ciberseguridad/plantillas-nist | 6 subnichos × 4 kw × US/GB (ALL en los ceros) + 2 controles AR/ES | 1 tarjeta (Dragon Fire Method), 3 señales | profundo, con 6 hijos |
| 2026-11-09 | EN | A huella | — (huella, US GB) | 13 huellas × US/GB + 2 controles AR/ES (24 keywords) | 2 tarjetas (Honey Home, Practical Accounting Kit), 4 señales | 5 nodos nuevos |
| | | | | | | |
