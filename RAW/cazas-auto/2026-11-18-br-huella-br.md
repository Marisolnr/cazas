# Caza automática — BR · huella (A) · — — 2026-11-18

Corrida de la mañana (miércoles → A huella, columna BR de «Rotación vigente»). 18 huellas BR nuevas (distintas de
las del 09-11, 11-11 y 14-11), 3 subagentes de lectura (6 huellas c/u + conteo por `page_ids` + `countries: ["BR"]`),
re-conteo propio de las dos páginas con tarjeta y 5 controles de destino (hispano, PT, IT) con `ALL`.
Corte de cohorte 7+: `ad_creation_time` ≤ 2026-11-11. La API no trae cuerpo del copy ni URL: ningún embudo verificado.

## Shortlist

### 1. Caeli - Editora Católica — capelinhas (mini-oratorios) de Nossa Senhora para imprimir
- page_id `1111029515430471` · BR · [Ads Library BR](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=BR&view_all_page_id=1111029515430471&search_type=page&media_type=all)
- **Cohorte 7+ / activos: 36/46** (46 estimados, los 46 vistos; re-conteo propio).
- Escalonamiento: 28-10 ×18 (20,7 d) · 01-11 ×5 · 09-11 ×12 · 12-11 ×6 · 17-11 ×4 → 5 fechas, operador vivo (ad de hoy).
- Títulos: «BAIXE AGORA AS CAPELINHAS DE NOSSA SENHORA DAS GRAÇAS» ×24 · «3 DEVOÇÕES MARIANAS» ×7 · «Capelinhas prontas
  para imprimir» ×7 · Santa Teresinha ×4 · Aparecida ×4. Una sola oferta con variantes por advocación.
- Tipo de página: marca («Editora Católica»), sin persona. BRL. Precio no visible.
- Más viejos: 2137708410471551 · 1588138586394312 · 1417963376640379 (28-10).
- Embudo: no verificado desde la nube («BAIXE AGORA» sugiere checkout directo de PDF).
- Score 3/4 (volumen, duplicación ×24, escalonamiento; falla hueco: testers en hispano e IT).

### 2. Na Sala da Prô — planillas Excel y plantillas Canva para coordinación escolar
- page_id `108550775468031` · BR · [Ads Library BR](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=BR&view_all_page_id=108550775468031&search_type=page&media_type=all)
- **Cohorte 7+ / activos: ≥43/50** (68 estimados → piso). El subagente destapó 17 más con `search_terms: Canva`
  sobre la página (≥60 en total, ad visible más viejo 18-10 según él; re-conteo propio: más viejo visible 26-10, 22 d).
- Por SKU (re-conteo propio): **«Grade de horários / Sua grade escolar com mais praticidade» 14/14** (02-03/11,
  14-15 d) · **«Calendário Escolar 2027 em Excel» 10/10** (26-27/10, 21-22 d) · Natal de gratidão (painel) ×6 ·
  «A turma muda» (transição) ×4 · Jornal da Equipe 2027 ×3 (08-11) · Consciência Negra ×3 · Aula da Saudade ×1 ·
  «Clube» Black Friday ×2 (09-11) · Agenda Digital da Coordenação 2027 ×6 (16-11, churn) · Recordação Escolar ×1 (hoy).
- 8 fechas de creación en la muestra; operador vivo. Marca, sin persona. BRL. Precio no visible.
- Riesgo Filtro C: hay un «Clube» (membresía) empujado en Black Friday → ¿los SKU sueltos son la puerta a una
  suscripción? Verificar en la PC.
- Score 3/4 (volumen, dos SKU con ≥10 cada uno, hueco hispano; falla longevidad < 30 d).

## Veredicto provisorio
- **Caeli → ENTRAR, observar ventana.** Llevar a **México** (validado), alternativa **Polonia**. La ventana se cierra:
  en el hispano ya corren *Capillas de Nuestra Señora* (1365797309960134, USD, «120 Capillitas de la Virgen María
  para Imprimir y Armar en Casa», ads de 0-2 d) y *Fabíola Verreti* (328451810347763, BRL, «capillitas de la Virgencita
  en PDF», 1 d); en IT/PT, *Little Big Scientist* (1321647621036448, USD, 7 d) y *What Would Jesus Do?*
  (1514214018442562, «3 pieghe e la cappellina è pronta», 3 d). Todos testers sin cohorte: nadie ganó todavía fuera
  de BR.
- **Na Sala da Prô → ENTRAR.** Llevar a **Argentina / Chile** (año escolar marzo-diciembre, igual que Brasil: el
  calendario 2027 se vende ahora) y **México** después (ciclo agosto-julio: vender en junio-julio). Hueco con `ALL`:
  `calendario escolar excel` (MX CO AR PE CL) = 1 ad (Saberly, SaaS); `horario escolar excel` = 9 de ruido
  (RR.HH., noticias, CECATI). Na Sala da Prô no corre fuera de BR (0 en PT MX AR CO ES).

## Señales (no tarjeta)
- Facilitaê Digital (1171932599334530): 28/≥50 (62 est.), 11 fechas, catálogo de PDFs a R$3,99-5,90 (geleias de
  banho ×6, Vila de Natal de papel ×5, velas ×5): ninguna oferta suelta llega a 10.
- Biblioteca do Corte (1273210592538710): 25/≥50 (72 est.), todo «⭐ 4.9/5.0»: nicho invisible por API
  (`moldes`/`costura`/`cortes` dan 0 sobre la página).
- Packs para Empreendedoras (108230422168514): 15/23 (el 11-11: 9/24), packs Canva por profesión (nutri, vet,
  contabilidad, advogados), 6 fechas: crece; re-medir 2026-11-25.
- Pack para Empreendedores (307180532467124): 12/26, kits imprimibles para terapeutas (masoterapia, chakras R$49,90)
  multi-SKU: ningún SKU con 10.
- Seu Clube do Agro (1216416161562086): 9/28, «Hidroponia Fácil Sem Bomba» ×22, 36 d: ¿PDF o kit físico?
- Cerca de la vara: Clube dos Mapas (1288006144400020, antes «Clube da AWS») 9/17 R$10; Amora Digital
  (1422045540990007) 8/10 sin títulos.
- Citius (1516912008579966): 22/47 en sondeo, pero es curso/membresía con «inscrições abertas até 22/11»: Filtro C.

## Cobertura
| Huella | País | ACTIVE (est.) | ALL | Qué trajo |
|---|---|---|---|---|
| pdf completo | BR | 9.392 | — | mezcla: personas (PCP do Zero), DDS de obra, Atlas Visual, Arquivos Pedagógicos 9,90 |
| receba no email | BR | 248.913 | — | basura: novelas y short-dramas en USD |
| produto digital | BR | 12.981 | — | **Na Sala da Prô**, Papelaria Digital R$9,90, artes sacras, Clube do Devocional |
| 100% digital | BR | 38.325 | — | personas sin título, Universo Musical R$17,90, Tia Juliana |
| modelos prontos | BR | 11.754 | — | herrería (excluida: ignorada), fiestas, crochê, Copilot |
| aulas gravadas | BR | 8.210 | — | cursos y posgrados; ruido |
| bônus exclusivos | BR | 17.592 | — | Packs para Empreendedoras, Rota da Medicina, Mapa Desenhado; muchas personas |
| garantia 7 dias | BR | 35.954 | — | ruido (constructora, autos, SaaS); Planilha na Prática, VILA KIDS |
| entrega imediata | BR | 11.468 | — | físico y retail; Biblioteca do Corte |
| resumos pdf | BR | 1.119 | — | la más limpia: concursos y enfermería, todo de 0-2 d |
| flashcards | BR | 2.892 | — | concursos/OAB/medicina, muchas «Dra./Prof.» |
| pacote digital | BR | 5.957 | — | VILA KIDS, 8020dosconcursos, retail |
| combo digital | BR | 4.302 | — | **Caeli**, Packs para Empreendedoras, Resumos de Enfermagem |
| manual prático | BR | 5.012 | — | mecánica, solar, contra entrega |
| guia definitivo | BR | 2.753 | — | Citius, Mega Acervo Enem, short-dramas |
| fichas prontas | BR | 871 | — | fichas para idosos/terapia (muchas personas, USD), Pack para Empreendedores |
| material imprimível | BR | 159 | — | chica y limpia: Clube dos Mapas, Terapia Ocupacional, Cursos Práticos |
| baixe agora | BR | 77.640 | — | short-dramas en USD |
| capillitas imprimir | MX CO AR PE CL | — | 30 | control: 2 testers de 0-2 d (USD y BRL) |
| capelinhas imprimir | PT | — | 3 | control: Little Big Scientist 3 ads (7 d) |
| Madonna stampare | IT | — | 176 | control: Little Big Scientist, What Would Jesus Do?, Segnalibri di Fede (testers) |
| horario escolar excel | MX CO AR PE CL | — | 9 | control: ruido |
| calendario escolar excel | MX CO AR PE CL | — | 1 | control: Saberly (SaaS) |

Páginas contadas (cohorte/activos, BR): Na Sala da Prô ≥43/50 · Caeli 36/46 · Facilitaê Digital 28/≥50 · Biblioteca do
Corte 25/≥50 · Citius 22/47 (sondeo) · Packs para Empreendedoras 15/23 · Pack para Empreendedores 12/26 · Clube dos
Mapas 9/17 · Seu Clube do Agro 9/28 · Amora Digital 8/10 · Descubra e Aprenda 6/20 · Produtos Inteligentes 4/10 ·
Jornada dos Pequenos 3/4 · Arquivos Pedagogicos PDF 3/33 · Rota da Medicina 2/9 · Universo Musical 2/7 ·
facamelhor.arte 2/20 · Mundo da Costura 1/10 · Dinâmicas Prontas 1/3 · cohorte 0: Ursinho da Memória 0/16, Concurso
Certo 0/8, Papelaria Digital 0/8, Akrecer 0/8, Resumos de Enfermagem 1 0/8, Universo dos Materiais 0/10, Ideia Fácil
0/7, Melodias e Riffs Baixo 0/7, Cursos Práticos 0/7, Mecânica Automotiva na Prática 0/6, Terapia Ocupacional 0/5,
Corpo em Movimento Atlas Visual 0/4, Mapa Desenhado 0/3, Mega Acervo Enem 0/3, Biblioteca Sénior 0/3, Pronto Para
Usar 0/3, Materiais & Artesanatos 0/3, Mundo dos Mapas Mentais 0/2, Renda com balões 0/2, Além da Aula 0/2,
Soluções Digitais Criativas 0/2, BRT Segurança 0/1.

Trampas nuevas: `receba no email` / `baixe agora` (BR) = novelas y short-dramas en USD; `garantia 7 dias` /
`entrega imediata` / `manual prático` (BR) = retail, autos, constructoras. Rinden: `combo digital`,
`produto digital`, `material imprimível` (chica y limpia), `resumos pdf` (limpia pero todo nuevo).

Nodos nuevos propuestos para la cola: `fe/capelinhas-imprimir` (superficial; Caeli) ·
`educacao/gestao-escolar-planilhas` (superficial; Na Sala da Prô).

Nicho excluido: aparecieron «+1000 projetos para serralheiros» (herrería) y un posgrado en autismo/TDAH: ignorados.

## Lo que no se pudo verificar
- Ningún embudo ni precio: la API no trae cuerpo del copy ni URL, y los snapshots dan 403 desde la nube.
- Caeli: confirmar que el entregable es un PDF para imprimir y armar (no un kit impreso enviado por correo).
- Na Sala da Prô: precio de cada planilla y si el «Clube» es la oferta principal (membresía) o un extra.
- Conteos de las páginas de señales: de los subagentes, sin re-conteo propio.
