# Caza automática — BR · B perforar (tarde) · produtividade/planner-rotina-estudos — 2026-11-17

Corrida de la tarde (18:40 ART). Nodo: el `superficial` BR más viejo (2026-11-09, una sola huella), sin toques de otra sesión en 7 días.
Seis subnichos × 5 kw BR = 30 keywords (3 subagentes de lectura) + re-conteo propio de Notion Estudos por tanda (`page_ids` + `search_terms` + `countries: ["BR"]`) + 2 controles hispanos con `ALL` + control de Notion Estudos en MX/CO/AR/PE/CL/ES/PT.
Evidencia: solo API (sin navegador). La API devuelve título del link, fechas, moneda y snapshot; **no trae cuerpo del copy ni URL de destino**: ningún embudo se pudo leer por WebFetch.

## Shortlist

### 1. Notion Estudos — «Caderno do acadêmico de <carrera>» (tarjeta)
- page_id `128822573650748` · BR · [Ads Library BR](https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=BR&view_all_page_id=128822573650748&search_type=page&media_type=all)
- **Cohorte 7+ / activos: ≥50 / ~247 estimados** (piso). La llamada por página solo trae los 50 más nuevos (todos del 16-11); la cohorte se contó **por tanda**, filtrando la página por carrera:
  | Tanda | Creada | Edad | Ads vivos |
  |---|---|---|---|
  | Terapia Ocupacional («ESSE CADERNO É PARA VOCÊ!») | 05-11 | 12,9 d | 10/10 |
  | Gastronomia | 06-11 | 11,1 d | 10/10 |
  | Física | 09-11 | 8,9 d | 10/10 |
  | Psicologia | 10-11 | 7,9 d | 10/10 |
  | Educação Física | 10-11 | 7,8 d | 10/10 |
  | Letras, Nutrição, Jornalismo, Música, Cinema (churn) | 16-11 | 1,3 d | 10 c/u |
  Enfermagem y Direito dan 0 dentro de la página (no las tiene).
- Escalonamiento: una carrera nueva cada 1-3 días, 10 ads idénticos por carrera, y **ninguna tanda perdió un ad**. Ojo: eso también puede ser que no poda nada; la página parece haber arrancado el 05-11 (no se encontró nada anterior). Operador vivo: 6 fechas, la última hoy.
- Tipo de página: marca, sin persona. Producto: por el nombre, plantilla de Notion (o cuaderno digital) por carrera; **no confirmado**. Precio no visible. Moneda BRL.
- Embudo: no verificado desde la nube.
- Duplicación: 10× el mismo título por tanda.
- Snapshots: [TO 12,9 d](https://www.facebook.com/ads/library/?id=1851606812546576) · [Gastronomia 11 d](https://www.facebook.com/ads/library/?id=2210848403123692) · [Ed. Física](https://www.facebook.com/ads/library/?id=1140763092023383)
- Score: ① longevidad 45+ ✗ (12,9 d) · ② volumen 50+ en cohorte ✓ (piso) · ③ duplicación ✓ (×10 por tanda) · ④ hueco ✓ (`plantilla Notion estudiantes` ALL = 4 ads en el hispano, Notion Estudos 0 fuera de BR, PT incluido) → **3/4, con la salvedad de que el operador tiene 13 días**.

### Señales (pasan algo, no tarjeta)
- **Planner Lovers** (128972030308501): **44/44 BR**, 10 fechas, ad más viejo 93 d (15-08), cobra en USD con copy en portugués («Seu Semestre Organizado em 1 Clique» ×8). Ya tiene tarjeta EN del 09-11 (US) y corre AR/ES/MX: no es tarjeta nueva.
- **Daily Routine Club** (671948206009244), tarjeta del 09-11: **17/22**, 8 fechas, ad más viejo 42 d; «Sua rotina tá uma bagunça?» ×18. Estable y vivo.
- **Moldes & Artes Digitais** (125664903959736): 6/9, planner financiero/«Prosperar», renueva cada ~30 días desde el 19-09 (59 d).
- **Guia dos Desorganizados** (1468944306295036): 3/10, «Guia de Organização para Pessoas Extremamente Desorganizadas» ×8, 4 fechas en 9 días: re-medir 2026-11-24.
- **eleja.se** (2544666325578449): ~260 activos estimados, «Planner'27», cohorte invisible (50 de 1-2 d).
- Lanzamientos sin cohorte: Papeliê 0/10 («Casa em Harmonia», planner familiar), Planilhas Fáceis 0/9, Cursos Digitais Prontos 0/14 (catálogo de 14 PDFs), Rota ENEM 0/3, Caneta em Dia 6/6 de una sola fecha.

## Veredicto provisorio
Notion Estudos → observar como candidato B: **modelar «cuaderno del universitario por carrera»** (plantilla Notion + PDF imprimible por carrera) en **Portugal** (mismo idioma, validado) y **México** (validado). Par fuente BR → PT/MX. ENEM/vestibular y finanzas = sin jugador fantasma con 10+; rutina-casa = lanzamientos.

## Cobertura
| Subnicho | Keywords (BR, ACTIVE) | Qué trajo |
|---|---|---|
| estudos-enem-vestibular | `planner estudos` (50/494), `cronograma ENEM` (50/612), `planner vestibular` (7), `rotina de estudos` (50/15.988), `planner enem pdf` (39) | cursinhos y personas (Sabrina Oliveira), «Mega Acervo ENEM R$27,90» en 2 páginas (≤4 ads), Rota ENEM 0/3, tkestudos 4/4, Matemática Online ≥14/50 (curso); ruido Kumon/EAD |
| universitario | `planner universitário` (35), `planner faculdade` (50/322), `organização faculdade` (50/1.281), `planner acadêmico` (50/145), `agenda universitária` (50/114) | Notion Estudos domina; CDPI Faculdade; papelerías físicas; ruido de novelas USD y facultades |
| rotina-casa-maes | `planner rotina` (50/1.346), `rotina organizada` (50/7.851), `cronograma limpeza` (50/672), `planner mãe` (50/75), `organização casa planner` (50/92) | personas (Marcia Sousa, Melanie Eckschmidt, Organize com Ju), Papeliê 0/10, Guia dos Desorganizados 3/10, físicos (Loja Somos Filhas R$184) |
| financeiro-planilhas | `planilha financeira` (50/1.978), `planner financeiro` (50/354), `controle financeiro planilha` (50/1.398), `planilha gastos` (50/1.310), `orçamento doméstico planilha` (3) | apps/SaaS, celebridades (Felipe Titto), Moldes & Artes Digitais 6/9, Gestão Financeira 2/2 (41 d), Planilhas Fáceis 0/9 |
| habitos-autocuidado | `planner hábitos` (50/394), `rastreador hábitos` (50/53), `planner autocuidado` (50/150), `diário gratidão` (50/525), `planner metas 2027` (50/350) | Oráculo Houhou («Cósmica»), devocionales, físicos, personas; planners TDAH (descartados) |
| digital-formato | `planner digital` (50/884), `planner goodnotes` (20), `planner notion` (50/176), `planner 2027` (50/1.466), `planner imprimível` (18) | Planner Lovers 44/44, eleja.se ~260 sin cohorte visible, Notion Estudos, microdramas USD en `planner digital` |
| re-conteo propio | `Caderno acadêmico` (50/201), `acadêmico Gastronomia` (22), `acadêmico Educação Física` (50/116), + dentro de la página: `ESTUDANTES DE FÍSICA` (30), `ESSE CADERNO` (10), `PSICOLOGIA` (20), `ENFERMAGEM` (0), `DIREITO` (0) | ver tabla de tandas |
| controles hispanos | `plantilla Notion estudiantes` ALL × 9 países (4: juancaparelli USD, Lumen Digital Studio ARS/Etsy), `cuaderno digital estudiantes` ALL (4.491 de ruido: megapacks, WA, libros médicos); Notion Estudos en MX/CO/AR/PE/CL/ES/PT ALL = 0 | hueco para el molde «cuaderno por carrera» |

Ninguna keyword BR dio 0: `ALL` no hizo falta en BR.

Trampas nuevas: `rotina organizada` / `rotina de estudos` / `cronograma limpeza` (BR) = SaaS, gimnasios, Kumon, empleo y novelas; `planner digital` (BR) = microdramas en USD; `diário gratidão` = devocionales y libros USD. Usar `planner acadêmico`, `planner notion`, `organização casa planner`.
Nodos nuevos: los 6 subnichos como hijos `superficial`.

## Lo que no se pudo verificar
- Embudo y precio de Notion Estudos (la API no trae URL ni copy): ¿plantilla Notion, PDF o suscripción? ¿precio?
- Si Notion Estudos tiene ads anteriores al 05-11 que ya se apagaron (la API solo da los 50 más nuevos por consulta).
- Planner Lovers: precio y embudo (USD).
