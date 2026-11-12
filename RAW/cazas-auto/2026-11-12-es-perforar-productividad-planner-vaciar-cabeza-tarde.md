# Caza ES · B perforar (tarde) · `productividad/planner-vaciar-cabeza` · 2026-11-12

Sesión ES, nube, corrida de la tarde (18:45 AR). Mercado: MX, CO, AR, PE, CL, BO, EC, GT, ES. Evidencia solo por API
(`ads_library_search`); snapshots y embudos no verificados desde la nube (ningún título trae URL de landing).

**Elección del nodo:** no hay `virgen` ES. Todos los `superficial` ES fueron tocados en los últimos 7 días; se tomó el
más viejo de los que solo nacieron por huella y nunca se perforaron (`productividad/planner-vaciar-cabeza`, 1 huella
del 10-11), igual que hizo EN hoy con `hogar/preparacion-emergencias`. Criterio anotado para que Marisol lo revise.

Barrido en paralelo con 3 subagentes de solo lectura (escrituras al repo en el hilo principal). Corte de cohorte:
`ad_delivery_start_time` ≤ 1793914893 (7 d); «reciente» = creado después de 1792927693 (30 d).

## Cobertura

| Subnicho | Keywords (estimated_total_count) | Lectura |
|---|---|---|
| digital-formato | `planner digital` 594 · `planner goodnotes` 13 · `agenda digital` 12.880 · `plantilla Notion` 52 · `planner hipervinculado` 0 (ALL: 1 viejo) | ruido de short-drama/novelas/VND; señal solo en `plantilla Notion` (Claridad y Acción) |
| finanzas-plantillas | `planner financiero` 65 · `control gastos` 6.694 · `plantilla presupuesto` 429 · `finanzas personales plantilla` 95 · `reto ahorro` 435 | Edwindigital (zombi), Mis Finanzas Pro 7/12, retos de ahorro nuevos |
| hogar-menu | `menú semanal` 923 · `planificador comidas` 245 · `planner mamá` 58 · `organizar hogar` 3.242 · `planner hogar` 47 | recetarios y viandas; señal: Planner Hoy Solo 3 y Mente Inquieta |
| estudiantes | `planner estudiante` 5 · `agenda universitaria` 1.042 · `planner estudio` 113 · `organizador estudios` 24 · `planner oposiciones` 0 (ALL: 48 academias) | cementerio para planners; Mente Ordenada 0/40 |
| emprendedoras-contenido | `planner emprendedora` 13 · `agenda emprendedora` 209 · `calendario contenido` 1.436 · `planner redes` 83 · `planner negocio` 148 | SaaS, agencias, marca personal (Eleni Fafutis); Pack Digital Emprendor |
| agenda-2027 | `agenda 2027` 12.708 · `planner 2027` 1.377 · `calendario 2027` 2.254 · `agenda imprimible` 199 | físico (imprentas, almanaques) y PLR; Eonline 50 ads del 11-11 |
| habitos-mente | `planner hábitos` 117 · `diario gratitud` 568 · `journal imprimible` 4 · `planner autocuidado` 15 · `vaciar mente` 132 · `brain dump` 1.879 | el molde «cabeza que va a mil» aparece en 5 páginas (Mente Inquieta, Mente Ordenada, Agenda sin Caos, Bajá el ruido, Descongestiona tu mente) |

35 keywords nativas, 7 subnichos, ALL en 2 ceros. ~25 páginas contadas con `page_ids` + países.

## Páginas contadas

| Página | page_id | Cohorte/activos 9 p | AR / ES / MX | Más viejo | Fechas | Reciente | Moneda | Qué vende | Veredicto |
|---|---|---|---|---|---|---|---|---|---|
| Claridad y Acción | 771123896085843 | **30/40** (recontado) | 30/40 · 20/30 · 30/40 | 37,6 d | 6 | sí (10-11) | USD | plantillas Notion por oficio: freelancer (10 en cohorte + 10 nuevos), estudios de arquitectura/obras (10), abogados/casos (10); «Instructivo paso a paso incluido»; cierre «Comenta FREELANCER» | **tarjeta** |
| Mente Inquieta | 1335956396276935 | 18/43 | 0/0 · **18/40** (recontado) · 18/40 | 14,3 d | 5 | sí (11-11) | EUR | «La agenda hecha para tu cerebro», «La agenda para cabezas que van a mil», «La agenda que no te juzga si la dejas», «Un plan también para los días malos» | **tarjeta** (riesgo: ¿física?) |
| Planner Hoy Solo 3 | 1280820831792286 | 30/41 | 0 · 29/40 · 29/40 | 21,7 d | ~11 | sí | USD | planner para vaciar la cabeza + 5 bonos | ya en bandeja (10-11) → señal |
| Planner Lovers | 128972030308501 | 20/20 | 19/19 · 0 · 20/20 | 14,8 d | 2 | sí (01-11) | USD | Planner Digital 2027 para tablet | ya en bandeja (EN 09-11); 2 fechas: no pasa el filtro de fechas |
| Pack Digital Emprendor | 104462436003652 | 18/18 | 18/18 · 0 · 0 | 108,6 d | 11 | sí | ARS | títulos «50%off» o vacíos: producto sin identificar | señal: no evaluable sin snapshot |
| Edwindigital | 630965730107298 | 41/41 | 13/13 · 0 · 13/13 | 36,1 d | 2 | **no** | PEN | plantillas Excel de finanzas a US$6 | posible zombi (sin ads en 35 d) |
| Habitos exitosos | 1060765213776917 | 13/13 | 13/13 · 0 · 0 | 233,7 d | 3 | **no** | ARS | catálogo «{{product.name}}» + WhatsApp | posible zombi, producto sin identificar |
| Mis Finanzas Pro | 930127610190546 | 7/12 | — | 205,7 d | 7 | sí | BRL/USD | pack Excel finanzas | debajo de la vara |
| Mente Ordenada | 1084424138077543 | 0/40 | — | 5,7 d | 4-5 | sí | USD | «Planner + 5 bonos · Descarga inmediata», «Vaciá tu cabeza en 10 minutos» | re-medir 2026-11-19 |
| Ositos de Entrecasa | 1376377502227263 | 0/10 | — | 0,6 d | 1 | sí | USD | Mega Kit Retos de Ahorro, Reto Aguinaldo | re-medir 2026-11-19 |
| Guias e Manuais para ajuda | 999834106555562 | 3/14 | — | 41,5 d | 3 | sí | BRL | Mega Kit Retos de Ahorro (español) | debajo de la vara |
| Conocimiento y Salud | 1419349107921669 | 6/33 | — | 18,9 d | 5 | sí | USD | PLR multinicho (+4.000 agendas 2027) | debajo de la vara |
| Binestar y Belleza | 811240618733828 | ≥14/50 | — | 14,3 d | muchas | sí | COP | kits escolares infantiles imprimibles | fuera del nodo |
| Otros (Transformación Saludable 0/9, Cocina Saludable Organizada 0/5, Biblioteca Digital 0/5, Kit imprimibles chile 0/3, TransformAccion 3/3, Best Venture Digital 0/1, Todo Digital 2/2, Agenda sin Caos TDAH 0/2, Bajá el ruido 0/2, Creative_SL 1/3) | | | | | | | | | sin cohorte |

IDs: Claridad y Acción más viejo 1779100009908413, freelancer reciente 1010407701336699, obras 3736736096474074, abogados
2380519166053337. Mente Inquieta más viejo 2269026110674995, «cabezas que van a mil» 4479179522300537.

## Lectura

- El molde del nodo («vaciar la cabeza / agenda para cabezas que van a mil / sin culpa») ya tiene **dos operadores con
  cohorte** (Planner Hoy Solo 3 30/41 y Mente Inquieta 18/43) y tres más testeando (Mente Ordenada 40 ads nuevos,
  Agenda sin Caos, Bajá el ruido). **Ninguno pauta en AR.** ES y MX ya están ocupados.
- Mente Inquieta usa el ángulo de TDAH adulto («hecha para tu cerebro»). No es el nicho excluido (neurokids = niños).
  Cobra en EUR y dice «agenda»: puede ser física; hay que verlo en la PC.
- Claridad y Acción sale del eje formato (`plantilla Notion`): no es planner personal sino plantilla de gestión por
  oficio, con 3 SKUs y lotes cada ~1-2 semanas. Nodo nuevo propuesto: `productividad/plantillas-notion-oficios` (ES).
- Planners anuales 2027 en hispano = físico/PLR; finanzas = zombis o BR.

## Decisiones tomadas sin preguntar

- Nodo elegido con el criterio de arriba (ningún ES libre de 7 días).
- Mente Inquieta va como tarjeta pese a la duda físico/digital: pasa la vara por API y el riesgo queda escrito.

## Pendiente (verificar en la PC)

- Embudo y precio de Claridad y Acción (DM por comentario) y de Mente Inquieta (¿PDF o agenda impresa?).
- Snapshot de Pack Digital Emprendor (qué es el pack).

## Trampas nuevas

`agenda` + año/rubro (verbo «agenda tu cita»), `planner` + negocio/redes/2027/hogar (wedding/event planners, SaaS,
constructoras), `calendario 2027` (imprentas), `brain dump` y `diario gratitud` (short-drama/novelas), `control gastos`
y `reto ahorro` (short-drama doblado), `organizar hogar` (muebles/inmobiliarias), `agenda universitaria`
(universidades). Rinden: `vaciar mente`, `planner hábitos`, `plantilla Notion`, `planner autocuidado`.
