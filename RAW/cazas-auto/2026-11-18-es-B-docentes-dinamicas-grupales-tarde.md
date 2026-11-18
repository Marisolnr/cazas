# Caza automática — ES · B perforar (tarde) · docentes/dinamicas-grupales — 2026-11-18

Mercado: CO + ES (fuente). Corrida de la tarde (18:45 ART). Nodo elegido: el `superficial` ES más viejo con «perforar» pendiente (cobertura del 2026-11-10), sin toque de otra sesión en 7 días. No había nodos `virgen` ES.
Método: 3 subagentes de lectura (30 kw × CO/ES, conteo por `page_ids` + país) + re-conteo propio de Geriactiva CO, Isabel Navarro ES y HIJOS DEL REY ES + 4 sondas de destino (Isabel Navarro PT/FR, Geriactiva IT, `attività anziani` IT, `nervo vago` PT, `nerf vague exercices` FR).
Cohorte = ads activos con `ad_delivery_start_time` < 2026-11-11 00:00 UTC.
Límite de la API: devuelve solo `ad_creative_link_title`, moneda, fechas y snapshot. No trae el cuerpo del copy, la URL ni el precio.

## Shortlist

1. **Isabel Navarro** — page_id 110050558601097
   - Arsenal: ES 49/≥50 (53 est.) y CO 49/≥50, el mismo set de ads. El filtro de país es de alcance: la página aparece igual en PT (50 est.) y FR (47 est.).
   - Fechas: ~11 de creación entre el 21-07 y el 17-11. El ad más viejo tiene 120,9 d y el más nuevo 1,2 d.
   - SKUs: «+120 Actividades del Nervio Vago», «+90 Protocolos Somáticos», «+1.500 Metáforas Terapéuticas Ilustradas». También corre versiones en italiano (Protocolli Somatici, Attività del Nervo Vago).
   - Hooks: «75% OFF — Solo por 24 horas», «⭐(4,9/5)», «El secreto de Erickson estaba en el silencio», «Accede al material 👉».
   - Moneda: BRL.
   - Snapshots: 2090924911769804 (21-07), 1415492977312610, 1635621261609394, 1818571269362389 (17-11).
   - Tipo de página: nombre de persona. Por la moneda BRL y las versiones multiidioma parece un avatar de operador. Sin verificar.
   - Embudo: no verificado desde la nube.
   - Score: 2/4.
2. **Geriactiva** — page_id 1259324537268785
   - Arsenal: CO ≥36/50 mostrados (119 est.). Re-conteo propio: 7 ads del 17-11, 7 del 12-11, 7 del 09-11, 10 del 05-11, 10 del 01-11 y 9 del 30-10. ES igual (119 est.). En IT llega con 95 est., con creativos en español.
   - Fechas: el ad visible más viejo tiene 19,7 d. Los 69 ads ocultos son anteriores.
   - Título único: «👍 +3000 Profesionales lo recomiendan».
   - Moneda: USD.
   - Snapshots: 1735676718271244, 1098567629673914, 2216864269713775, 1429215670275003.
   - Embudo: no verificado desde la nube.
   - Score: 2/4.
3. **HIJOS DEL REY** — page_id 1124309607441637 (tercero: va como señal por el tope de 2 tarjetas)
   - Arsenal: ES 14/25 (re-conteo propio) y CO 14/28.
   - Fechas: 28-08, 29-10, 04-11, 09-11, 12-11 y 15-11. El ad más viejo tiene 82,7 d. En CO hay una variante en inglés del 18-11 («Print & Play!»).
   - Título: «¡Imprime y úsalo!» (material cristiano juvenil y de campamentos).
   - Moneda: BRL.
   - Snapshots: 2078478896392088, 2107564673216499.

## Veredicto provisorio

- **Isabel Navarro → ENTRAR → Portugal** (PT-PT), con **Francia** como segunda opción.
  - Con `nervo vago` PT solo aparecen suplementos, el «Lymphatic Reset» y un curso en vivo (Luis Fernando). Nadie vende recursos para terapeutas.
  - En FR apareció hoy Olivia Grant, con la misma plantilla «⭐(4.9/5)» y 0 días de antigüedad.
  - Italia ya la ocupa el mismo operador.
  - Solo se corrió 1 keyword por destino: hay que confirmar el hueco con ALL desde la PC.
- **Geriactiva → ENTRAR → Italia**, con **Portugal** como segunda opción.
  - Con `attività anziani` IT salen 341 est., casi todos geriátricos y centros de día (servicio).
  - Los únicos infoproductos son Quaderni per Anziani («Il kit completo da stampare», USD, 3 ads de hoy) y Digitalfullkits («365 attività», ARS, de hoy): la ventana se está abriendo.
- **HIJOS DEL REY → observar.** Re-medir el 2026-11-25; su eje es el de `fe/material-cristiano-imprimible`.
- **Subnichos:**
  - Psicólogos y terapeutas, y adultos mayores: SUBNICHO con 1 whale cada uno.
  - Docentes y aula, y RR. HH. y empresa: molde joven, nadie con 10+.
  - Catequesis y jóvenes: HIJOS DEL REY pasa la vara; Pequeñitos en la Fe y Marcela Fernandez son posibles zombis.
  - Recreación y fiestas: servicios y estacional navideño de 0-9 d.

## Cobertura

Todas las keywords se corrieron en ACTIVE en CO y en ES. Ninguna dio 0 en los dos países, así que no hizo falta ALL.

| Subnicho | Keyword | CO | ES | Qué trajo |
|---|---|---|---|---|
| docentes-aula | dinámicas grupales | 241 | 214 | Talleres Listos domina; Geriactiva, Dinámicas Pro Pack, Trabajo en Equipo, Thomas Walker, PasoFirme |
| docentes-aula | juegos cooperativos | 12 | 15 | basura: regalos, consolas y juegos de mesa físicos (excluido) |
| docentes-aula | dinámicas docentes | 88 | 70 | universidades, másteres, academias; Marina Duarte, Miss Catalina |
| docentes-aula | actividades rompehielo | 5 | 0 | recreacionistas (servicio) |
| docentes-aula | dinámicas integración | 84 | 38 | turismo, retiros, constelaciones; HIJOS DEL REY |
| catequesis-jovenes | dinámicas catequesis | 22 | 17 | Pequeñitos en la Fe, Marcela Fernandez, Dinámicas con Laura, Ready Kits Club |
| catequesis-jovenes | dinámicas juveniles | 25 | 7 | Bendiciones creativas, Una Oración con Dios, HIJOS DEL REY |
| catequesis-jovenes | dinámicas cristianas | 35 | 29 | HIJOS DEL REY, Bendiciones creativas, Doxa Grace |
| catequesis-jovenes | juegos jóvenes iglesia | 75 | 49 | Bendiciones creativas en masa («RECIBELO GRATIS HOY»), Luz divina |
| catequesis-jovenes | dinámicas campamento | 3 | 8 | HIJOS DEL REY; en ES, escuelas de idiomas |
| rrhh-empresa | dinámicas empresariales | 42 | 1 | eventos, universidades, escape rooms |
| rrhh-empresa | team building dinámicas | 7 | 9 | servicios |
| rrhh-empresa | talleres RRHH | 1 | 5 | Dinámicas Pro Pack, abogados laborales |
| rrhh-empresa | dinámicas trabajo equipo | 109 | 48 | la mejor del eje: Trabajo en Equipo, Pro Pack, Marina Duarte, Kit Dinámicas Grupales Pro |
| rrhh-empresa | actividades clima laboral | 9 | 2 | hueco |
| psicologos-terapeutas | talleres psicoeducativos | 1 | 1 | psicóloga con servicio; neurodivergente (excluido) |
| psicologos-terapeutas | dinámicas terapéuticas | 50 | 26 | packs para terapeutas: **Isabel Navarro**, Sofía Rodrigues, Natália Soares, EstDuc, Terapeuta Constelador |
| psicologos-terapeutas | talleres listos | 189 | 109 | Talleres Listos, Thomas Walker; ruido de «listo» |
| psicologos-terapeutas | dinámicas autoestima | 64 | 42 | Bienestar Emocional, Sofía Rodrigues, CieloStore |
| adultos-mayores | actividades adultos mayores | 322 | 180 | **Geriactiva**, PasoFirme, Entrena Tu Mente, Mente Activa, Mente Sin Olvidos, GeriaVital; geriátricos |
| recreacion-fiestas | juegos fiestas PDF | 4 | 1 | Navidad para Niños, Mybibliotech |
| recreacion-fiestas | juegos baby shower | 113 | 3 | recreacionistas; NovaMente Digital 2/2 y «Dra. Evelyn Reed» 3/3 (kit baby shower, BRL) |
| recreacion-fiestas | juegos navideños imprimibles | 5 | 1 | Navidad Inolvidable US$4,90, Casita de aprendizaje |
| recreacion-fiestas | animación infantil juegos | 57 | 28 | 100 % servicio |
| recreacion-fiestas | recreación dinámicas | 73 | 3 | servicio; Aula Creativa |
| formato | dinámicas PDF | 186 | 138 | Talleres Listos, Mariana Lopes (+300), Cida Freire, Ready Kits Club, Activa Mayor Pro |
| formato | banco dinámicas | 17 | 13 | liderazgo (Breno Oliveira, banco de bono), fitness |
| formato | kit talleres | 245 | 139 | basura de taller mecánico; El Gran Fichero de Dinámicas de Grupo (ES) |
| formato | fichas dinámicas | 217 | 194 | Geriactiva, Avanza Digital, Universo Terapéutico (OJO neurokids) |
| formato | talleres imprimibles | 42 | 39 | Talleres Listos, Kit Dinámicas Grupales Pro, Jeimmy Castañeda 8/8 CO, Berteli Brothers |
| sonda destino | nervo vago (PT) | — | — | PT 54 est.: Lymphatic Reset, All The Way, Teravo, Luis Fernando (en vivo): hueco de recursos para terapeutas |
| sonda destino | nerf vague exercices (FR) | — | — | FR 31 est.: Teravo, **Olivia Grant ⭐(4.9/5) 0 d**, Dr Claire Moreau |
| sonda destino | attività anziani (IT) | — | — | IT 341 est.: centros de día y geriátricos; Quaderni per Anziani (USD, hoy), Digitalfullkits (ARS, hoy) |

Re-conteos por `page_ids` + país (≈ 45 consultas entre subagentes y propias): Talleres Listos CO 4/25 · ES 4/38; HIJOS DEL REY CO 14/28 · ES 14/25; Pequeñitos en la Fe 14/14 · 14/14 (2 fechas, la última del 15-10: posible zombi); Marcela Fernandez ES 10/10 · CO 8/8 (una sola fecha, 05-10: posible zombi, «Últimas unidades»); Marina Duarte 4/5; Dinámicas Pro Pack 3/4; Bienestar Emocional 9/17; Sofía Rodrigues 8/13; EstDuc CO 9/19; Bendiciones creativas CO 0/≥50 · ES 1/45; Jeimmy Castañeda CO 8/8 (persona); Natália Soares 0/16; El Gran Fichero ES 0/10; Kit Dinámicas Grupales Pro 0/4; Thomas Walker ES 0/5; Trabajo en Equipo 0/4.

Trampas nuevas:
- `kit talleres`: trae el taller mecánico (llantas, autos y soldadura, que es nicho excluido).
- `juegos cooperativos`: trae juegos de mesa físicos (excluido) y consolas.
- `animación infantil juegos`, `juegos baby shower` (CO), `recreación dinámicas`, `actividades rompehielo`, `dinámicas empresariales` y `team building dinámicas`: solo traen servicios.
- `talleres listos`: el AND por token atrapa cualquier «listo».
- `talleres psicoeducativos` y `fichas dinámicas`: rozan neurokids.

Nodos nuevos propuestos: los 6 hijos del nodo, que quedan como `superficial`.

## Lo que no se pudo verificar

- Isabel Navarro y Geriactiva:
  - precio, formato (PDF o plataforma) y landing;
  - si alguno muestra una cara (Isabel Navarro tiene nombre de persona).
- La edad de los 69 ads ocultos de Geriactiva (el tope de 50).
- HIJOS DEL REY: el producto exacto.
- El filtro `countries` de la API es de alcance, no de idioma: Isabel Navarro aparece en PT/FR y Geriactiva en IT con creativos en otro idioma, así que la presencia en destino se juzga por el idioma del creativo.
