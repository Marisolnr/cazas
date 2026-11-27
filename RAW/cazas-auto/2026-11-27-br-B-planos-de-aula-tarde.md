# Caza automática — BR · B perforar (tarde) · educacao/atividades-prontas-professores/planos-de-aula — 2026-11-27

Corrida desatendida de la tarde (18:36 ART). Nodo elegido: el `superficial` BR más viejo (planos-de-aula, 5 kw del 2026-11-09), no tocado por otra sesión en 7 días; no hay nodos BR `virgen`.
Decisiones tomadas sin preguntar: 6 subnichos por avatar/materia/formato (abajo); la API devolvió solo `ad_creative_link_title` + fechas (sin cuerpo del copy ni URL), así que precio, cierre y cara quedan n/d salvo lo que dice el título; WebFetch de alanaeduca.com.br bloqueado por permiso (no respondido) → embudo no verificado.

## Shortlist

### 1. Alana Educa — «Guia Anual – Sequências para o Ano Todo» + acceso vitalicio (tarjeta)
- page_id 531839286685764 · [Ads Library BR](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=BR&view_all_page_id=531839286685764&search_type=page&media_type=all)
- **Cohorte 7+/activos: 32/32 en BR** (re-conteo propio, completa, `estimated_total_count` 32). Escalonado en 5 fechas de creación: 30-10 (~14 ads, entrega desde 30/31-10 → 27-28 d), 02-11 (~12, 24 d), 10-11 (3, 17 d), 12-11 (1, 15 d), 13-11 (3, 14 d). Ad más nuevo 13-11 (operador vivo, pero sin tanda en los últimos 14 d). Longevidad máx 28 d.
- Títulos: «Acesso Vitalício | Atualizações Gratuitas» / «Acesso vitalício e pagamento único» ×9; «Guia Anual – Sequências para o Ano Todo» ×4; «Baixar Agora» ×6; «Recursos Lúdicos … atividades educativas … coordenação motora … pais e professores» ×4; «Coleção Inglês na Rotina – Cards Ilustrados» ×1; 8 sin título. Antes corrió «50% OFF | ACESSO VITALICIO».
- Tipo de página: marca (Alana Educa), sin cara por API. Dominio propio alanaeduca.com.br (aparece en título).
- Embudo: no verificado desde la nube (WebFetch bloqueado). «pagamento único + acesso vitalício» sugiere checkout de producto digital, no suscripción. Sin señales de inclusión/TEA en títulos.
- Snapshots duplicados: [«Acesso vitalício e pagamento único»](https://www.facebook.com/ads/library/?id=4588981154708818) · [«Guia Anual»](https://www.facebook.com/ads/library/?id=1828742291696030) · [«Guia Anual» 30-10](https://www.facebook.com/ads/library/?id=1863608648012711)
- Ya lo probó en Portugal: `sequências didáticas` PT con ALL trae ~14 ads de Alana («Guia Anual – PT», «50% OFF») de 30-10 a 12-11; con `page_ids` + PT ACTIVE = 0 → Portugal apagado (¿no rindió o pausa?).
- Score: ① longevidad 45+ no (28 d) · ② 50+ no (32) · ③ duplicación 10+ no (9 con el mismo título) · ④ hueco: no confirmado (ver destinos) → **0/4, observar**. Pasa la vara (32 ≥ 10, un solo page_id).

## Veredicto provisorio
SUBNICHO / observar. El molde «el año entero planificado para infantil, listo para usar» está validado en BR y ya lo clona una red de testers en varios destinos:
- IT (`programmazione annuale` ALL): Accademia Pronta, Cattedra Pronta, PsicoMotion Kids, EuroHacks — todos < 3 d.
- RO (`planificare grădiniță` ALL, 84): Mesa Ligera («36 de săptămâni planificate»), Edulabs Resources, Avenlo, Kinetika Group, Estimulación en casa - Kids («Planificarea anuală, gata făcută · 3–6 ani», desde 26-10) — oct-nov.
- FR (`programmation maternelle` ALL, 147): L'Année Prête Maternelle (desde 03-11, varios ads), Estimulación en casa - Kids (FR también), Grace Mitchell, Clarento, Orbis Atlas.
- MX (`planeación anual` / `secuencias didácticas`): Eonline (planeación + evaluación $100 por WA, ads de hoy), Asesoría Docente 2026, Planeaciones Secundaria 2.0; mercado local de planeaciones por WhatsApp.
- PT: el propio Alana lo probó y está apagado.
Par sugerido: BR → **Grecia o Hungría** (validados, sin sondear en esta corrida: sondear con ALL en la PC). En IT/RO/FR la ventana se está cerrando (testers de 0-30 d).

## Cobertura (BR, ACTIVE, limit 50; ningún cero → ALL no hizo falta en BR)
| Subnicho | Keyword | ACTIVE (est.) | Qué trajo |
|---|---|---|---|
| plano-aula-bncc-anos-iniciais | `plano de aula BNCC` | 184 | mezcla: Castelinho do Saber (WA), Prof. Renan Paro (vitalício R$59,90), Urânia Planetários; ruido SaaS IA (Teachy, Ensinei), Nova Escola, Futuremakers; PEI (excluido) |
| | `planejamento anual BNCC` | 60 | Ed. Física além da bola (~20), Alana Educa, Help Pedagógico (R$14,90), Prof. Lucas de Almeida; ruido Educamundo |
| | `planos de aula 1º ano` | 53 | Gleidson Nunes, Eber Gomes, Prof. Jaci, Ana Luiza Barbosa; ruido eventos/agencias |
| | `planejamento semanal professora` | 74 | Segredos da Carla, abcdaeducacaomais, Pensar Pedagógico, Tia Vera Galvão; ruido concursos/abogados |
| | `planejamento quinzenal` | 55 | ruido |
| sequencias-didaticas | `sequência didática pdf` | 18 | Mundo Miúdo, sala.interativa, suzanoadriana; ruido anatomía |
| | `sequências didáticas prontas` | 32 | Alana Educa, Pequenos com Ideias, Materiais Pedagógicos, EdHumanas; ruido IA (Skooly) |
| | `sequência didática BNCC` | 27 | Prof. Vilma Ribeiro, Alfakids, Pequenos Fluentes, profdanypogian |
| | `projeto didático pronto` | 15 | ruido |
| | `sequência didática editável` | 1 | artes.lucrativas_ |
| planner-diario-professor-2027 | `planner professor 2027` | 29 | Aprenda Brincando, abcdaeducacaomais, Salva Aula, Profe Camila, Theia, Castelinho do Saber |
| | `planejamento 2027` | 8585 | ruido total (empresas) |
| | `diário de classe` | 200 | microdramas, OAB; Prof em Dia |
| | `caderno de planejamento` | 493 | mixto, papelería física |
| | `planner docente` | 20 | Verônica Fragoso, Coração Lúdico (WA), Salva Aula, Theia |
| aulas-prontas-fund2-medio | `aulas prontas história` | 291 | ruido (fraudes, EBD) |
| | `aulas prontas geografia` | 49 | Mariane da Silva, Nuvem Kids, Na Sala da Prô, Materiais Pedagógicos, Marcia Almeida (WA, 317 d) |
| | `plano de aula ciências` | 62 | microdramas; Urânia, Ensina Educação |
| | `aulas prontas ensino médio` | 193 | Camila Rocha, Ed. Física além da bola, Prof. Vanderley, EducaFin, Mariane |
| | `aulas prontas química` | 50 | Prof. Vanderley, MateriaCiencia, Naturalmente Química |
| disciplinas-especiais | `aulas educação física` | 1374 | ruido (universidades, gimnasios); Ed. Física além da bola, Kit do Professor EF |
| | `aulas de arte prontas` | 57 | ARTE NA MENTE, 300 Dinâmicas de Arte, Acervo.Educa |
| | `ensino religioso aulas` | 60 | Ana Luiza Barbosa, Universo Educacional, Tudo Sala de Aula |
| | `aulas de inglês prontas` | 120 | Nuvem Kids, Inglês de Giz, Leticia Oliveira; ruido escuelas |
| | `plano de aula arte` | 136 | ruido (dramas, IA) |
| componentes-novo-ensino-medio | `projeto de vida aulas` | 1280 | ruido |
| | `eletiva pronta` | 6 | profdanypogian |
| | `educação financeira aulas` | 424 | EducaFin, Educoin; ruido finanzas personales |
| | `aulas socioemocionais` | 117 | colegios; inclusión (excluido) |
| | `itinerário formativo` | 15 | colegios |

Sondas de destino: `sequências didáticas` PT (ALL, 413 est.: Evolutiva Academy USD, Irmãos Mandarim, Alana Educa PT apagado) · `secuencias didácticas` MX (ACTIVE, 14: Planeaciones Secundaria 2.0, Aprendia, Maestra Miel de Maple) · `planeación anual` MX (ACTIVE, 127: Eonline WA, Asesoría Docente) · `unità didattiche` IT (ALL, 531: ruido + Orbis Atlas, Emito) · `programmazione annuale` IT (ALL, 1653: Accademia Pronta, Cattedra Pronta, PsicoMotion Kids) · `planificare grădiniță` RO (ALL, 84) · `programmation maternelle` FR (ALL, 147). Alana Educa `page_ids` + PT ACTIVE = 0.

## Páginas contadas (page_ids + BR, ACTIVE)
| Página | page_id | Cohorte/activos | Long. máx | Fechas | Ad más nuevo | Qué vende | Nota |
|---|---|---|---|---|---|---|---|
| Alana Educa | 531839286685764 | 32/32 | 28 d | 5 | 13-11 | Guia Anual sequências + vitalício | **tarjeta** |
| Materiais Pedagógicos | 759619130561032 | 20/21 | 410 d | ~18 | 27-11 | n/d (títulos vacíos / api.whatsapp / instagram) | WA sin oferta visible por API → señal |
| EdHumanas | 121666711034496 | 24/24 | 287 d | 20 | 18-11 | catálogo (LP 100% prontas ×4, maquetes) | ya tarjeta 26-11 → señal |
| Segredos da Carla | 778768491992375 | 12/37 | 8 d | 5 | 27-11 | berçário/pareceres (×6) + «Mãe, estimule seu bebê» (×9) + «app» | multi-SKU, nombre de persona; ninguna oferta llega a 10 |
| Mariane da Silva | 845386025334212 | 36/≥50 (96 est.) | ≥43 d | 5 | 24-11 | +1000 slides PPTX | tarjeta de esta mañana → señal |
| Na Sala da Prô | 108550775468031 | 41/45 | 31 d | 7 | 27-11 | multi-SKU coordinación (grade Excel 14, formatura 13) | operador ya seguido → señal |
| Theia Didáticos | 106477925437851 | 11/11 | 129 d | 4 | 12-10 | planner Ciências 2027, lapbooks | sin ads en 30 d → posible zombi |
| MateriaCiencia | 1280874838444389 | 10/10 | 80 d | 2 | 11-09 | «Por apenas R$10» | 2 fechas, nada en 30 d → posible zombi |
| Naturalmente Química | 980111551859343 | 15/15 | 240 d | 5 | 10-09 | n/d | marca personal (Prof Weverton) + sin ads en 30 d |
| Prof. Jaci Recursos Pedagógicos | 1129227410281432 | 9/10 | 49 d | 5 | 25-11 | n/d («🟢 ONLINE» ×10) | persona; a 1 de la vara |
| Ana Luiza Barbosa | 1222841337576063 | 9/9 | 9 d | 1 | 18-11 | 180 aulas de Ensino Religioso | una fecha |
| Pequenos com Ideias | 1368676116319540 | 7/11 | 37 d | 4 | 24-11 | n/d | |
| Universo Educacional | 134613913067365 | 2/10 | 22 d | 3 | 26-11 | catálogo por disciplina | |
| Nuvem Kids | 107330512133695 | 4/4 | 21 d | 2 | 08-11 | 500 actividades por materia | |
| Aprenda Brincando | 336720632853317 | 5/18 | 7 d | 5 | 27-11 | planner educadores 2027, kit mat | |
| Gleidson Nunes · Eber Gomes · Inglês de Giz · profdanypogian · 300 Dinâmicas de Arte | — | 4/5 · 2/3 · 3/3 · 3/3 · 1/1 | — | — | — | — | chicos |
| Educação Física além da bola | 110729704860273 | 0/20 | 2 d | 3 | 27-11 | aulas prontas EF | lanzamiento: re-medir 2026-12-04 |
| Profe Camila · Camila Rocha · Prof. Vanderley · EducaFin · Educoin · ARTE NA MENTE · Castelinho do Saber · Salva Aula | — | 0/28 · 0/9 · 1/10 · 0/4 · 0/9 · 0/4 · 0/4 · 0/3 | — | — | — | — | ola de planners 2027 / Black Friday, sin cohorte |

Trampas nuevas: `planejamento 2027` (8.585, empresas), `planejamento quinzenal`, `projeto didático pronto`, `projeto de vida aulas`, `plano de aula arte`, `aulas prontas história`, `diário de classe`, `caderno de planejamento`, `itinerário formativo`, `aulas socioemocionais` (inclusión). Útiles: `sequências didáticas prontas`, `planner professor 2027`, `aulas prontas ensino médio`, `aulas de inglês prontas`, `ensino religioso aulas`.

Nodos nuevos propuestos: ninguno fuera del nodo; 6 hijos superficial.

## Lo que no se pudo verificar
- Landing de Alana Educa (WebFetch: permiso no respondido); precio, checkout, formato exacto (PDF vs área de miembros), público (¿infantil? «coordenação motora»), y si hay contenido de inclusión dentro.
- Cuerpo del copy de todos los ads (la API solo devolvió el título del link).
- Materiais Pedagógicos: qué vende por WA (20/21, 410 d).
- Snapshots: 403 desde la nube; longevidad solo por API.
