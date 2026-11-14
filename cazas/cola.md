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
| negocios/guias-management-pdf | negocios | EN | superficial | 1 operador contado (Your Consulting Management Guide 41/46 US, 34/38 GB) + 1 control AR/ES · 2026-11-11 | apareció por modo C el 2026-11-11 (tarjeta); perforar por tema (gobierno corporativo / resolución de problemas / procesos / RR. HH.) y contar el control hispano con 4-5 kw |
| educacion-profesional/contabilidad-workbooks | educacion-profesional | EN | superficial | 1 kw GB (£27 pdf) + 1 control AR/ES · 2026-11-09 | apareció por huella el 2026-11-09 (Practical Accounting Kit 21/31 GB); perforar por avatar (estudiante / pyme / liquidación de sueldos) |
| ciberseguridad/plantillas-nist | ciberseguridad | EN | profundo | 24 kw nativas US/GB + ALL en ceros + control AR/ES · 2026-11-09 | modo C: seguir a Dragon Fire Method; perforado el 2026-11-09 |
| ciberseguridad/plantillas-nist/nist | ciberseguridad/plantillas-nist | EN | profundo | 4 kw · 2026-11-09 | un whale (Dragon Fire Method); tarjeta 2026-11-09 |
| ciberseguridad/plantillas-nist/iso-27001 | ciberseguridad/plantillas-nist | EN | superficial | 4 kw · 2026-11-09 | cementerio: kits ISO solo con ads inactivos (ISO 27001 PRO LLC, Stratovik) |
| ciberseguridad/plantillas-nist/soc2-politicas | ciberseguridad/plantillas-nist | EN | superficial | 4 kw · 2026-11-09 | ruido SaaS; solo Dragon Fire |
| ciberseguridad/plantillas-nist/incident-response | ciberseguridad/plantillas-nist | EN | superficial | 4 kw · 2026-11-09 | DR/BC = hueco con ALL; IR solo Dragon Fire |
| ciberseguridad/plantillas-nist/hipaa | ciberseguridad/plantillas-nist | EN | superficial | 4 kw · 2026-11-09 | SaaS y MSP; Gamma Compliance Solutions 6/6 (ads de hasta 823 d) |
| ciberseguridad/plantillas-nist/estudio-examen | ciberseguridad/plantillas-nist | EN | superficial | 4 kw · 2026-11-09 | CISSP = cementerio; Security+ es una trampa |
| examenes-ilustrados | educacion-profesional | EN | virgen | — | apareció por huella el 2026-11-09 (Visual Guide Lab, In pictures books, Illustrated Manuals: volumen sin cohorte); re-medir desde 2026-11-16 |
| planners-imprimibles-2027 | hogar | EN | profundo | 7 kw US/GB + 1 control AR/ES, 5 subnichos · 2026-11-09 tarde | perforado el 2026-11-09 (tarde): 2 tarjetas (This & That, Planner Lovers); estacional, ventana hasta enero |
| planners-imprimibles-2027/digital-tablet | planners-imprimibles-2027 | EN | superficial | 4 kw · 2026-11-09 | This & That 10/50 US y Planner Lovers 28/28 US (tarjetas); EaseUp 140 est. con cohorte oculta: re-medir desde 2026-11-16 |
| planners-imprimibles-2027/presupuesto | planners-imprimibles-2027 | EN | superficial | 1 kw · 2026-11-09 | Winter Wren, Plan With Sage, Litepaper (GB): todo < 7 d; faltan `budget binder`, `money planner pdf` |
| planners-imprimibles-2027/navidad | planners-imprimibles-2027 | EN | superficial | 0 kw propias · 2026-11-09 | Simplify Her Life, Family Fun Printables: todo < 7 d; re-medir antes del 2026-11-30 |
| planners-imprimibles-2027/docente | planners-imprimibles-2027 | EN | superficial | 1 kw (ruido) · 2026-11-09 | Nova for Teachers 5/5 (66 d, EUR); usar `lesson planner pdf`, `teacher binder` |
| planners-imprimibles-2027/fe-oracion | planners-imprimibles-2027 | EN | superficial | 1 kw (ruido) · 2026-11-09 | My Digital Prayers 8/8 en una sola fecha (posible zombi); usar `christian planner`, `bible study planner` |
| pareja/reconquista-matrimonio | pareja | EN | profundo | 22 kw US/GB (5 subnichos) + ALL en 9 ceros/spam + control AR/ES · 2026-11-10 | perforado el 2026-11-10: tarjeta Heroic Husband + Linda Harrison (él); modo C sobre los operadores |
| pareja/reconquista-matrimonio/el-salvar-matrimonio | pareja/reconquista-matrimonio | EN | superficial | 4 kw · 2026-11-10 | Heroic Husband 47/53 US y 45/45 GB, Linda Harrison 43/55 US (tarjeta); `wife stopped` y `dead bedroom` = short-drama |
| pareja/reconquista-matrimonio/ella-reconectar | pareja/reconquista-matrimonio | EN | superficial | 4 kw · 2026-11-10 | Kinley's Lane 10/10 de una sola fecha (posible zombi); Fierce Marriage 15/15 es pareja-marca con libros impresos |
| pareja/reconquista-matrimonio/infidelidad-confianza | pareja/reconquista-matrimonio | EN | superficial | 4 kw + ALL · 2026-11-10 | Sarah Couples Therapist 6/10 ($9.97, persona); Michelle Mays 17/17 es autora; LanternGo workbook 2/3 |
| pareja/reconquista-matrimonio/ruptura-ex | pareja/reconquista-matrimonio | EN | superficial | 4 kw + ALL · 2026-11-10 | con ALL es spam; lo real es INR (Calm sphere 16/16 de agosto, posible zombi) |
| pareja/reconquista-matrimonio/workbooks-conexion | pareja/reconquista-matrimonio | EN | superficial | 6 kw · 2026-11-10 | fábricas «90% off» que rotan cada semana (Printable WITH Lisa 0/31, Heal & Focus 0/46); Donna Whitfield 553 est. con cohorte oculta: re-medir 2026-11-17 |
| musica/teoria-workbooks | musica | EN | virgen | 2 kw US/GB · 2026-11-09 | apareció por huella el 2026-11-09 (Acordes en Claro est. 586, Music Solved, Daniel Brooks): volumen sin cohorte visible por API; re-medir desde 2026-11-16 |
| manualidades/patrones-costura-pdf | manualidades | EN | profundo | 25 kw US/GB (7 subnichos) + ~20 páginas contadas; sin control AR/ES · 2026-11-10 tarde | perforado el 2026-11-10 (tarde): 2 tarjetas (Knitting Art Studio, The Crochet Nook); modo C sobre los operadores |
| manualidades/patrones-costura-pdf/mascotas | manualidades/patrones-costura-pdf | EN | superficial | 2 kw · 2026-11-10 | Knitting Art Studio 40/50 US (10 en la oferta de $27), tarjeta; Wag & Stitch 0/15 ($21, cruza 7 d el 11-11), PawPattern nuevo; `dog clothes pattern` = short-drama |
| manualidades/patrones-costura-pdf/tejido-crochet | manualidades/patrones-costura-pdf | EN | superficial | 4 kw · 2026-11-10 | Crochet Nook 44/50 GB (tarjeta); Knitting Memories 23/27 (92 d, SKU sueltos); Sarah Mitchell 14/44 GB; Patterns Zone 12; All Knittings y Knitter's Treasure Chest con cohorte oculta: re-medir 2026-11-17 |
| manualidades/patrones-costura-pdf/ropa-mujer | manualidades/patrones-costura-pdf | EN | superficial | 5 kw · 2026-11-10 | todo < 2 d por keyword; Stitch Well 409 est. (cohorte oculta, 21 ads de 7+ d por keyword) y su espejo Elsie Brooks; marcas (Style Arc, McClure, Love Notions) |
| manualidades/patrones-costura-pdf/infantil-munecas | manualidades/patrones-costura-pdf | EN | superficial | 4 kw · 2026-11-10 | Stitch Well «doll wardrobe» 15/15 (69 d); Vive Digital 15/23 multinicho (costura 5); Emma Clarke / Online Skills = persona |
| manualidades/patrones-costura-pdf/bolsos | manualidades/patrones-costura-pdf | EN | superficial | 3 kw + control AR/ES (`patrones bolsos`) · 2026-11-11 | Sewing Lovers 19/50 US (tarjeta 2026-11-11); Motif Studio sin cohorte; `tote bag pattern` = físicos; en AR/ES ya hay moldes (Dulce Irene, El Arsenal Del Marroquinero) |
| manualidades/patrones-costura-pdf/fieltro-peluches | manualidades/patrones-costura-pdf | EN | superficial | 3 kw · 2026-11-10 | Mariana Williams (fieltro católico) todo < 7 d: re-medir 2026-11-17; Sweet Pea, SewBloom chicos |
| manualidades/patrones-costura-pdf/quilting | manualidades/patrones-costura-pdf | EN | superficial | 2 kw · 2026-11-10 | Wildbloom Quilts 5/10 ($27/$47, RON); el resto, kits físicos |
| religion/biblia-visual | religion | EN | profundo | 6 subnichos × 5 kw US/GB (30) + 1 de arranque + 2 controles AR/ES; ~20 páginas contadas · 2026-11-11 tarde | perforado el 2026-11-11 (tarde): tarjeta RootedinFaith; modo C sobre los hijos |
| religion/biblia-visual/visual-ilustrada | religion/biblia-visual | EN | superficial | 6 kw · 2026-11-11 | Revelation Unsealed 3D 8/23 US (re-medir 2026-11-14, ¿PDF o libro?); Stories of the Bible y chart Adams = físicos; Christian Knowledge 275 est. con cohorte oculta |
| religion/biblia-visual/estudio-biblico-guias | religion/biblia-visual | EN | superficial | 5 kw + control AR/ES (`entender Biblia`) · 2026-11-11 | RootedinFaith 30/45 GB y 28/≥50 US (tarjeta); en español ya corren operadores BR «la Biblia libro por libro» (sin contar) |
| religion/biblia-visual/devocional-planner | religion/biblia-visual | EN | superficial | 5 kw · 2026-11-11 | nada con 10+; Coffee and Bible Time 0/7 (nuevo); Christian Craft Paper es membresía |
| religion/biblia-visual/ninos-escuela-dominical | religion/biblia-visual | EN | superficial | 5 kw · 2026-11-11 | Growing in Faith 18/27 US (advertorial, producto no visible, 9 d); Faith Times 7/36 hermana; FaithSprout 2/8 |
| religion/biblia-visual/tarjetas-cheat-sheets | religion/biblia-visual | EN | superficial | 5 kw · 2026-11-11 | Shining Light Printables 12/12 sin ads nuevos en 30 d (posible zombi); el resto ruido |
| religion/biblia-visual/historia-apologetica | religion/biblia-visual | EN | superficial | 5 kw · 2026-11-11 | Catholic Roots 25/25 US sin ads en 31 d (posible zombi); Adams & Century físico; ruido de iglesias |
| religion/papeleria-cristiana-reventa | religion | EN · ES | superficial | 1 kw EN + control AR/ES (`papelería cristiana`) · 2026-11-11 | Valentina Ríos 17/26 US (BRL, español) pero ya corre en AR/ES con Elixir de Vida y Papelería Cristiana: destino ocupado |
| hogar/preparacion-emergencias | hogar | EN | profundo | 6 subnichos × 4-5 kw US/GB (25) + ALL en 1 + 2 controles AR/ES; ~25 páginas contadas · 2026-11-12 tarde | perforado el 2026-11-12 (tarde): 2 tarjetas (The Lost Skills of Independence, Fallback Book); modo C sobre los hijos |
| hogar/preparacion-emergencias/planes-apagon-72h | hogar/preparacion-emergencias | EN | superficial | 3 kw (`emergency plan printable`, `blackout binder`, `prepper pdf`) · 2026-11-12 | ola de esta semana con cohorte 0 (Smart Library 0/12, Handled Simply 0/7, Grid Down Plan, Gridfall «$9 Blackout Binder», READY GB): re-medir 2026-11-19 |
| hogar/preparacion-emergencias/plan-familiar-personalizado | hogar/preparacion-emergencias | EN | superficial | 2 kw + Fallback Book contado · 2026-11-12 | Fallback Book 18/18 GB (tarjeta); `family emergency plan` = ruido; control ES `kit 72 horas`: Apagón Total y Charlotte Whitmore de 1-2 d |
| hogar/preparacion-emergencias/habilidades-perdidas | hogar/preparacion-emergencias | EN · ES | superficial | 2 kw + control AR/ES (`habilidades perdidas`) · 2026-11-12 | Lost Skills of Independence ≥50/604 US (físico USD 39, tarjeta); ola hispana de clones de 0-2 d (Maestro del Oficio, Mauricio Rios, Jime Bauer, Lucas Rossi): re-medir 2026-11-19 |
| hogar/preparacion-emergencias/despensa-almacenamiento | hogar/preparacion-emergencias | EN | superficial | 5 kw + ALL en 1 · 2026-11-12 | Food Storage Tips ≥17/273 US (advertorial, producto no visto) y 8/8 GB (394 d); canning = cementerio |
| hogar/preparacion-emergencias/primeros-auxilios-remedios | hogar/preparacion-emergencias | EN | superficial | 5 kw · 2026-11-12 | `first aid printable` es la única limpia (todo < 7 d); Forgotten Home Apothecary ≥8/170 (libro, cohorte oculta) |
| hogar/preparacion-emergencias/checklists-mochila | hogar/preparacion-emergencias | EN | superficial | 5 kw · 2026-11-12 | familia American Ready / Prepared American / Homefront Ready = físico; Bug in Guide ≥18/635 (¿libro?); Survival Starter 2/2 (PDF 97 p) |
| escrita-criativa/estruturas-narrativas | escrita-criativa | BR | superficial | 1 huella BR + 1 control ES/AR/MX/CO (ALL) · 2026-11-09 | apareció por huella el 2026-11-09 (Creartool 23/48 BR, tarjeta); perforar por avatar (novelista / guionista / fanfic) y formato (manual / plantillas de escaleta) |
| produtividade/planner-rotina-estudos | produtividade | BR | superficial | 1 huella BR + 1 control AR/ES · 2026-11-09 | apareció por huella el 2026-11-09 (Daily Routine Club 14/22 BR, tarjeta); perforar por avatar (vestibular / concurso / universitario) |
| educacao/atividades-prontas-professores | educacao | BR | profundo | 30 kw nativas BR (6 subnichos × 5) + 2 controles AR/ES/MX · 2026-11-09 tarde | perforado el 2026-11-09 (tarde): tarjeta Prof. Mariana Oliveira 19/48; modo C sobre los operadores |
| educacao/atividades-prontas-professores/alfabetizacao | educacao/atividades-prontas-professores | BR | superficial | 5 kw · 2026-11-09 | rotadores con cohorte oculta (Atividades Educacionais 66, Mariane Assis Dias 120 + 2 hermanas a R$10, Atividades infantil 128); re-medir |
| educacao/atividades-prontas-professores/educacao-infantil | educacao/atividades-prontas-professores | BR | superficial | 5 kw · 2026-11-09 | mayormente escuelas; Criador de Apostila Visual 12/19 es herramienta, no PDF |
| educacao/atividades-prontas-professores/portugues-fund2 | educacao/atividades-prontas-professores | BR | superficial | 5 kw · 2026-11-09 | Pequenos Leitores se apaga (8/17); Loja das Profs/Jaque Mendes con cohorte detrás del tope |
| educacao/atividades-prontas-professores/matematica | educacao/atividades-prontas-professores | BR | superficial | 5 kw · 2026-11-09 | Regina Alves 19/19 sin ads nuevos en 30 d (posible zombi); nadie vivo con 10+ |
| educacao/atividades-prontas-professores/planos-de-aula | educacao/atividades-prontas-professores | BR | superficial | 5 kw · 2026-11-09 | Prof. Luana Rodrigues 38/50 pero persona y R$197; Patrícia Oliveira 0/9 |
| educacao/atividades-prontas-professores/datas-e-escola-dominical | educacao/atividades-prontas-professores | BR | superficial | 5 kw · 2026-11-09 | oferta joven y repartida (Fé de Pertinho, Biblibrinca, EducaKids); Roberta Perez ≥11/121 es persona y apunta a padres |
| concursos/material-estudo | concursos | BR | profundo | 30 kw nativas BR (6 subnichos × 5) + 1 huella + 7 controles ES/AR · 2026-11-10 tarde | perforado el 2026-11-10 (tarde): 2 tarjetas (Mapa Concursos, 123passei); modo C sobre los operadores |
| concursos/material-estudo/apostilas-por-cargo | concursos/material-estudo | BR | superficial | 5 kw + huella · 2026-11-10 | saturado (7+ anunciantes): Aprovaconcursobb ≥21/50, ConcursoPM 26/33 (se apaga), Felipe Resumão ≥15/50; cada SKU vence con su edital |
| concursos/material-estudo/resumos-mapas-mentais | concursos/material-estudo | BR | superficial | 5 kw · 2026-11-10 | Mapa Concursos 39/50 (mapas de enfermagem, tarjeta); en AR/ES ya hay 3 testers de enfermería |
| concursos/material-estudo/questoes-simulados | concursos/material-estudo | BR | superficial | 5 kw · 2026-11-10 | 123passei 18/34 («Protocolo» R$27,90, 162 d, tarjeta); Gabaritei 14/37 mismo molde |
| concursos/material-estudo/planejamento-cronograma | concursos/material-estudo | BR | superficial | 5 kw · 2026-11-10 | `planner concurso` = 26 ads: el cronograma vive dentro del kit, no solo |
| concursos/material-estudo/legislacao-lei-seca | concursos/material-estudo | BR | superficial | 5 kw · 2026-11-10 | nadie con 10+ (Rota TJ 6/18); ruido de ley de tránsito |
| concursos/material-estudo/por-avatar-professor-saude | concursos/material-estudo | BR | superficial | 5 kw · 2026-11-10 | Trilha do Estudo ≥40/50 (¿app?), Concurseiros da Educação ≥13 (aulões), Enfermagem Resumida ≥14 (webinar) |
| psicologia/materiais-psicanalise | psicologia | BR | profundo | 30 kw nativas BR (6 subnichos × 5) + 1 de arranque + ALL en 1 + 2 controles AR/ES; ~25 páginas contadas · 2026-11-11 tarde | perforado el 2026-11-11 (tarde): 2 tarjetas (NeuroKit Clínico + Terapia Cognitiva Online, Nova Era Recursos Terapêuticos); modo C sobre los operadores |
| psicologia/materiais-psicanalise/psicanalise | psicologia/materiais-psicanalise | BR | superficial | 6 kw · 2026-11-11 | Estante 6/25 (re-medir 2026-11-18); Mariana Costa 11/14 (USD, persona); Terapia de Verdade mapas R$14,90 todo < 7 d |
| psicologia/materiais-psicanalise/estudantes-psicologia | psicologia/materiais-psicanalise | BR | superficial | 5 kw · 2026-11-11 | Mundo Conhecimento 7/17 (242 transtornos, USD); Mariana oliveira 4/9 (900 mapas R$12,90); Psicoterapeutas no Poder 0/6 |
| psicologia/materiais-psicanalise/ferramentas-clinicas-tcc | psicologia/materiais-psicanalise | BR | superficial | 5 kw + control AR/ES (`fichas terapia`) · 2026-11-11 | NeuroKit 34/50 + Terapia Cognitiva Online 19/33 (tarjeta); 5+ anunciantes = subnicho; en AR/ES ya hay testers BR en español < 7 d |
| psicologia/materiais-psicanalise/documentos-psicologo | psicologia/materiais-psicanalise | BR | superficial | 5 kw · 2026-11-11 | Psiflow.clin ≥18/81, Valesca Romão 17/21 (persona); mucho SaaS |
| psicologia/materiais-psicanalise/psicoterapia-infantil | psicologia/materiais-psicanalise | BR | superficial | 5 kw + ALL en 1 + control AR/ES (`recursos terapêuticos`) · 2026-11-11 | Nova Era 25/42 (tarjeta); ola de clones «recursos prontos R$9,99» < 7 d; excluido todo lo neurodivergente |
| psicologia/materiais-psicanalise/autoconhecimento-cadernos | psicologia/materiais-psicanalise | BR | superficial | 5 kw · 2026-11-11 | ebooks de ansiedad con cara; nadie fantasma con cohorte |
| mapas-visuais-r10 | educacao | BR | profundo | 6 subnichos × 5-6 kw BR (32) + 1 de arranque + 2 controles AR/ES/MX/CO; ~45 páginas contadas · 2026-11-12 | perforado el 2026-11-12: 2 tarjetas (TI em Mapas, Farmácia Mapeada); modo C sobre los hijos |
| mapas-visuais-r10/saude | mapas-visuais-r10 | BR | superficial | 5 kw + 3 controles AR/ES (`farmacología mapas`, `kinesiología mapas`, `educación física mapas`) · 2026-11-13 | Farmácia Mapeada ≥32/≥50 (farmacología 15/20, 78 d, tarjeta); Edufisicavisual 26/29 (cinesiología, 12,7 d, tarjeta 2026-11-13); en el hispano, kinesiología ya tiene ~7 testers BR (0-4 d), educación física pocos; muchas páginas-persona (Mariana Oliveira, Daniela Santos) |
| mapas-visuais-r10/lab-vet-agro | mapas-visuais-r10 | BR | superficial | 6 kw · 2026-11-12 | oferta chica a R$10: Bovino Ilustrado 6/16, Universo Laboratorial 4/10, Suelem Dias 9/9 sin ads nuevos; parasitologia y agronomia = huecos finos |
| mapas-visuais-r10/tecnologia-exatas | mapas-visuais-r10 | BR | superficial | 6 kw + control AR/ES (`mapas mentales informática`) · 2026-11-12 | TI em Mapas 41/49 (77,7 d, tarjeta; ya en español desde el 10-11); red «Clube do X» rota a diario sin cohorte; Bellion 5/31 |
| mapas-visuais-r10/direito | mapas-visuais-r10 | BR | superficial | 6 kw · 2026-11-12 | Marcelomapas ≥22/143 est. (79,5 d, ¿persona?); Direito do Trabalho 10X 7/≥50; OAB = suscripciones y apps |
| mapas-visuais-r10/escola-enem | mapas-visuais-r10 | BR | superficial | 5 kw · 2026-11-12 | nadie con 10+; O Pai do ENEM 0/22 estacional; Português Primata 4/5 (WA) |
| mapas-visuais-r10/formato-ilustrado | mapas-visuais-r10 | BR | superficial | 5 kw · 2026-11-12 | Mapas Visuais & ilustrados ≥22/50 (producto no visible); Luana Ferreira 0/9 (persona, USD) |
| design-digital/packs-stories-templates | design-digital | BR | superficial | 2 huellas BR (`templates canva`, `pack de artes`) + 1 control AR/ES · 2026-11-11 | apareció por huella el 2026-11-11 (Templates - Pack de artes: figurinhas 27/27, 217-293 d, tarjeta); perforar por formato (stickers / feeds / mini site / sublimación) y avatar (emprendedora / profesión) |
| oficios/moldes-marcenaria-pdf | oficios | BR | superficial | 2 huellas BR (`moldes pdf`, `download imediato`) + 2 controles AR/ES · 2026-11-11 | apareció por huella el 2026-11-11 (Mestre da Madeira 11/50, tarjeta); en AR/ES ya hay testers (Carpinteria que Vende, Tablero Studio); perforar por avatar (juguetes / palet / muebles) |
| receitas/ebooks-fit | receitas | BR | profundo | 6 subnichos × 5 kw BR (30) + 1 de arranque + 1 control AR/ES (`recetas airfryer`); sin ceros, ALL no hizo falta; ~45 páginas contadas · 2026-11-12 tarde | perforado el 2026-11-12 (tarde): 2 tarjetas (Hadassa Fit, Cozinhanoprato); FitFlow y Comida Saudável siguen sin ads nuevos (posible zombi) |
| receitas/ebooks-fit/airfryer-fit | receitas/ebooks-fit | BR | superficial | 5 kw + control AR/ES (`recetas airfryer`) · 2026-11-12 | SUBNICHO: Hadassa Fit 14/26 (104 d, tarjeta), Chef Mari ≥18, Chef Pierre 17/24, Fernanda Rocha ≥15 (personas-chef); AR/ES con ~12 testers < 2 d |
| receitas/ebooks-fit/colecoes-packs | receitas/ebooks-fit | BR | superficial | 5 kw · 2026-11-12 | Cozinhanoprato 14/14 (32 d, tarjeta, re-medir 2026-11-19); el resto es renda extra y personas |
| receitas/ebooks-fit/low-carb-emagrecimento | receitas/ebooks-fit | BR | superficial | 5 kw · 2026-11-12 | embudos WA sin oferta visible: Receitas Emagrecedoras ≥42/≥50, Saúde em Forma ≥29/≥50; verificar en la PC |
| receitas/ebooks-fit/doces-sobremesas-fit | receitas/ebooks-fit | BR | superficial | 5 kw · 2026-11-12 | nadie fantasma con 10+; red «200 Sobremesas Zero Açúcar» en 5 páginas, cohorte 0-1; Doces Fit Receitas 5/5 sin ads nuevos |
| receitas/ebooks-fit/marmitas-congeladas | receitas/ebooks-fit | BR | superficial | 5 kw · 2026-11-12 | marmitarias físicas; Luana Oliveira ~750 ads sin cohorte visible; `marmita saudável ebook` = hueco (4 ads) |
| receitas/ebooks-fit/restricoes | receitas/ebooks-fit | BR | superficial | 5 kw (sem glúten / sem lactose / diabéticos / zero açúcar) · 2026-11-12 | top 50 entero nuevo y ruido físico; Ajudai 0/14 (diabéticos, USD, de hoy); re-medir con `page_ids` |
| costura/moldes-pdf-br | costura | BR | profundo | 30 kw BR (6 subnichos × 5) + 3 controles AR/ES/MX/CO; ~30 páginas contadas · 2026-11-13 tarde | perforado el 2026-11-13 (tarde): 2 tarjetas (Ponto Certo App, Mamãe que fez); modo C sobre los operadores |
| costura/moldes-pdf-br/roupas-femininas | costura/moldes-pdf-br | BR | superficial | 5 kw · 2026-11-13 | Avila Moldes 8/12 (PDF por pieza, 52 d), Jéssica Modelista 6/11 (252 d, persona), Mavi Moldes 6/10; escuelas y personas (Maísa Rasche, Hellena Cometti) |
| costura/moldes-pdf-br/infantil-bebe-bonecas | costura/moldes-pdf-br | BR | superficial | 5 kw · 2026-11-13 | Mamãe que fez 11/17 (naninha R$17, 12 d, tarjeta); Ana Beatriz ≥30/≥50 (USD, ¿persona?); Ursinho da Memória en 4 páginas sin contar |
| costura/moldes-pdf-br/pet | costura/moldes-pdf-br | BR | superficial | 5 kw · 2026-11-13 | oferta chica: Gabi Moldes 3/7, Pixelverso 9/10 («4,8/5», producto sin ver); `roupa pet molde` y `caminha pet molde` = huecos (1-2 ads) |
| costura/moldes-pdf-br/bolsas-necessaires | costura/moldes-pdf-br | BR | superficial | 5 kw · 2026-11-13 | Costura com Jéssica Lais 9/10 (persona); Raquel Atellier R$14,90 1/2; mucho WA y «recebe antes de pagar» sin cohorte |
| costura/moldes-pdf-br/casa-avental-mesa-posta | costura/moldes-pdf-br | BR | superficial | 5 kw · 2026-11-13 | Ponto Certo App 10/24 (avental japonês, 114 d, tarjeta); Silvia Mello ≥30/164 (producto sin ver); hispano `molde delantal` = 8 ads |
| costura/moldes-pdf-br/apostilas-cursos | costura/moldes-pdf-br | BR | superficial | 5 kw · 2026-11-13 | escuelas, lanzamientos y gratis (Conserto de roupas na Prática); `apostila modelagem` y `moldes prontos` = ruido |
| salud-mental/sistemas-de-sesiones | salud-mental | ES | profundo | 6 subnichos × 4-6 kw (27) sin ceros + ~45 páginas contadas (Sector Digital por país) · 2026-11-11 tarde | perforado el 2026-11-11 (tarde): 1 tarjeta (Biblioteca Digital, eje entrenadores); modo C sobre los hijos |
| salud-mental/sistemas-de-sesiones/psicologia-clinica | salud-mental/sistemas-de-sesiones | ES | superficial | 7 kw · 2026-11-11 | nadie con 10+: Psico Express 7/21 (77 d), Cer Solutions 7 de psicología (20/28 multi-oficio), Psique y Ciencia mezcla cursos |
| salud-mental/sistemas-de-sesiones/deportiva | salud-mental/sistemas-de-sesiones | ES | superficial | 2 kw · 2026-11-11 | solo Sector Digital (≥31 únicos, AR/ES/MX, ya en bandeja); el resto universidades y lanzamientos con live |
| salud-mental/sistemas-de-sesiones/adicciones | salud-mental/sistemas-de-sesiones | ES | superficial | 3 kw · 2026-11-11 | clínicas y red de títulos ⭐; Sector Digital adicciones cohorte 0 (≤2 d): re-medir 2026-11-18 |
| salud-mental/sistemas-de-sesiones/pareja-sistemica | salud-mental/sistemas-de-sesiones | ES | superficial | 2 kw · 2026-11-11 | ola nueva: Clínica del vínculo 0/12, Kit Graduación Listo 0/36, Psicologia & Recursos 2025 6/16: re-medir 2026-11-18 |
| salud-mental/sistemas-de-sesiones/nutricionistas | salud-mental/sistemas-de-sesiones | ES | superficial | 5 kw · 2026-11-11 | Consultorio Nutri Listo 6/40 (8 d, re-medir 2026-11-18); Soy Nutri Digital 22/22 posible zombi; Nutrispace 7/7 |
| salud-mental/sistemas-de-sesiones/coaching-trabajo-social | salud-mental/sistemas-de-sesiones | ES | superficial | 5 kw · 2026-11-11 | certificaciones y coaches-persona; packs de coaching todos < 2 d |
| deportes/planificacion-entrenadores | deportes | ES | superficial | 1 kw (`plantillas entrenadores`) + Biblioteca Digital por país · 2026-11-11 | apareció al perforar salud-mental el 2026-11-11 (Biblioteca Digital 25/33 AR, tarjeta; ES 0); perforar por deporte (fútbol / vóley / básquet / handball) y avatar (profe de educación física / club) |
| manualidades/patrones-pdf | manualidades | ES | profundo | 8 subnichos × 4-5 kw (37) + ALL en 2 + ~30 páginas contadas · 2026-11-09 | perforado el 2026-11-09 (tarde): 2 tarjetas (Crea y Emprende, Cursos Online); modo C sobre los hijos |
| manualidades/patrones-pdf/crochet-amigurumi | manualidades/patrones-pdf | ES | superficial | 6 kw · 2026-11-09 | Crea y Emprende 19/30 (AR 17/20), tarjeta; la ola navideña de amigurumi tiene < 7 d: re-medir 2026-11-16 |
| manualidades/patrones-pdf/tejido-dos-agujas | manualidades/patrones-pdf | ES | superficial | 4 kw + ALL tricot · 2026-11-09 | La Biblioteca Definitiva De Tejido 23/23 pero sin ads nuevos en ~49 d (posible zombi) |
| manualidades/patrones-pdf/bordado | manualidades/patrones-pdf | ES | superficial | 4 kw + ALL bordado mexicano · 2026-11-09 | todo < 7 d; bordado mexicano = cementerio |
| manualidades/patrones-pdf/costura-moldes | manualidades/patrones-pdf | ES | superficial | 5 kw · 2026-11-09 | Educa Online 9/43 ($4), Emprendedores 6/6; re-medir 2026-11-16 |
| manualidades/patrones-pdf/macrame-bisuteria | manualidades/patrones-pdf | ES | superficial | 4 kw · 2026-11-09 | solo emprender con manualidades (≥6/≥50, piso); bisutería = cursos presenciales |
| manualidades/patrones-pdf/goma-eva-fieltro | manualidades/patrones-pdf | ES | superficial | 5 kw · 2026-11-09 | Recursos creativos 8/≥50 (piso); Hecho por vos 0/48 de esta semana |
| manualidades/patrones-pdf/navideno-pesebre | manualidades/patrones-pdf | ES | superficial | 5 kw · 2026-11-09 | ola de lanzamientos (Digital Shop, Santos En Punto, Puntada Maestra 4/23 ES); re-medir 2026-11-16 |
| manualidades/patrones-pdf/papercraft-fiesta | manualidades/patrones-pdf | ES | superficial | 5 kw · 2026-11-09 | Cursos Online 11/24 MX, tarjeta; Activa Academy kit de fiesta 4 en cohorte |
| oficios-digitales/guias-cricut | oficios-digitales | ES | profundo | 6 subnichos × 5 kw (30) + 4 de arranque + ALL en 1 + ~45 páginas contadas · 2026-11-10 tarde | perforado el 2026-11-10 (tarde): 2 tarjetas (Neutral Nature, Biblioteca Creativa); modo C sobre los hijos |
| oficios-digitales/guias-cricut/cricut-silhouette | oficios-digitales/guias-cricut | ES | superficial | 5 kw · 2026-11-10 | Biblioteca Creativa 10/25 (tarjeta); el resto son vendedores de máquinas |
| oficios-digitales/guias-cricut/archivos-svg-corte | oficios-digitales/guias-cricut | ES | superficial | 5 kw + ALL topper · 2026-11-10 | Pablo Ruiz 16/28 AR (persona, «método de venta»); Maestra de las Cajas 5/7; topper SVG = cementerio |
| oficios-digitales/guias-cricut/sublimacion-plantillas | oficios-digitales/guias-cricut | ES | superficial | 6 kw · 2026-11-10 | Pixelpack ≥29/62 (megapack de reventa); Smartsubli 25/25 posible zombi; Nivel Pro subset 12/12 (multiproducto) |
| oficios-digitales/guias-cricut/laser-cnc-archivos | oficios-digitales/guias-cricut | ES | superficial | 6 kw · 2026-11-10 | Vectores Laser 9/9 (78 d, Messenger); Planos & Proyectos 93 y The Leather Blueprint 92 con cohorte oculta: re-medir |
| oficios-digitales/guias-cricut/tarjetas-popup-papeleria | oficios-digitales/guias-cricut | ES | superficial | 5 kw · 2026-11-10 | Neutral Nature 47/47 CO (tarjeta), clon Pura Idea 0/43; Deco Mundo 11/23; Cajas Para Imprimir Creativas 6/8 |
| oficios-digitales/guias-cricut/negocio-con-maquina | oficios-digitales/guias-cricut | ES | superficial | 5 kw · 2026-11-10 | ruido de máquinas, insumos y talleres; nada con cohorte |
| productividad/planner-vaciar-cabeza | productividad | ES | profundo | 7 subnichos, 35 kw nativas + ALL en 2 ceros; ~25 páginas contadas · 2026-11-12 tarde | molde «cabeza que va a mil» con 2 operadores con cohorte (Planner Hoy Solo 3 30/41, Mente Inquieta 18/43, tarjeta) y ninguno en AR; Mente Ordenada 0/40 re-medir 2026-11-19 |
| productividad/planner-vaciar-cabeza/digital-formato | productividad/planner-vaciar-cabeza | ES | superficial | 5 kw + ALL · 2026-11-12 | ruido de short-drama/VND; `plantilla Notion` dio Claridad y Acción (tarjeta, nodo aparte) |
| productividad/planner-vaciar-cabeza/finanzas-plantillas | productividad/planner-vaciar-cabeza | ES | superficial | 5 kw · 2026-11-12 | Edwindigital 41/41 posible zombi; Mis Finanzas Pro 7/12; retos de ahorro nuevos (Ositos de Entrecasa 0/10): re-medir 2026-11-19 |
| productividad/planner-vaciar-cabeza/hogar-menu | productividad/planner-vaciar-cabeza | ES | superficial | 5 kw · 2026-11-12 | recetarios y viandas; menú semanal todo < 2 d |
| productividad/planner-vaciar-cabeza/estudiantes | productividad/planner-vaciar-cabeza | ES | superficial | 5 kw + ALL oposiciones · 2026-11-12 | cementerio para planners (academias, apuntes) |
| productividad/planner-vaciar-cabeza/emprendedoras-contenido | productividad/planner-vaciar-cabeza | ES | superficial | 5 kw · 2026-11-12 | SaaS, agencias, marca personal; Pack Digital Emprendor 18/18 AR sin producto visible |
| productividad/planner-vaciar-cabeza/agenda-2027 | productividad/planner-vaciar-cabeza | ES | superficial | 4 kw · 2026-11-12 | físico (imprentas) y PLR (Conocimiento y Salud 6/33, Eonline 50 del 11-11) |
| productividad/planner-vaciar-cabeza/habitos-mente | productividad/planner-vaciar-cabeza | ES | superficial | 6 kw · 2026-11-12 | Mente Inquieta (tarjeta), Mente Ordenada, Agenda sin Caos, Bajá el ruido, Descongestiona tu mente: el molde se está llenando |
| productividad/plantillas-notion-oficios | productividad | ES | superficial | 1 kw (`plantilla Notion`) + Claridad y Acción por país · 2026-11-12 | apareció al perforar planner-vaciar-cabeza (Claridad y Acción 30/40, 3 SKUs por oficio, tarjeta); perforar por oficio (salud / docentes / creativos) y formato (Notion / Excel) |
| manualidades/plantillas-ceramica | manualidades | ES | superficial | 1 huella ES (`plantillas imprimibles`) + conteo AR/ES · 2026-11-10 | apareció por huella el 2026-11-10 (Biblioteca maestra arcilla ≥16/≥50 AR, tarjeta; ES 0; clon Planos de Barro de hoy) |
| educacion-profesional/fichas-visuales-estudio | educacion-profesional | ES | profundo | 6 subnichos × 5 kw (30) + ALL en 1 + ~13 páginas contadas · 2026-11-11 | perforado el 2026-11-11: 2 tarjetas (Aprendia : Guias profesionales, Derecho en Mapas); modo C sobre los hijos |
| educacion-profesional/fichas-visuales-estudio/salud | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw · 2026-11-11 | red Aprendia con cohorte 0; IA Programas 16/22 (producto sin ver); testers BRL |
| educacion-profesional/fichas-visuales-estudio/oficios-tecnicos | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw · 2026-11-11 | casi solo la red Aprendia; Aprendia : Guias profesionales MX 38/50 (tarjeta) |
| educacion-profesional/fichas-visuales-estudio/mapas-esquemas | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw + ALL mapas conceptuales · 2026-11-11 | Derecho en Mapas CO 10/34 (tarjeta); mapas conceptuales imprimibles = cementerio |
| educacion-profesional/fichas-visuales-estudio/oposiciones-examenes | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw · 2026-11-11 | academias; Mapasyresumenes 4/50 (re-medir 2026-11-18); El Mapa del MIR 9/0 |
| educacion-profesional/fichas-visuales-estudio/derecho-contabilidad | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw · 2026-11-11 | Dra Mariana Legal 8/23; Studio Facile ES 43 nuevos (re-medir 2026-11-18); Virtual Derecho desde 9,90 € |
| educacion-profesional/fichas-visuales-estudio/formato-aprendia | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw · 2026-11-11 | ruido de 5.000+ en `guía visual PDF` y `fichas de estudio`; Bookbay Digital 9/0 |
| docentes/dinamicas-grupales | docentes | ES | superficial | Talleres Listos contado por país AR/ES/MX · 2026-11-10 | Talleres Listos pasa la vara (AR 20, ES 24, MX 21) pero ya corre en AR y ES; perforar por público (docentes / catequesis / RR. HH.) |
| hogar/kit-sucesion-familia | hogar | EN | superficial | 1 huella US/GB (`printable binder`) + My Estate Kit contado en GB · 2026-11-12 | apareció por huella el 2026-11-12 (My Estate Kit ≥50/50 GB, 115 d, tarjeta); hay cluster (Atlas Media «The Kept Folder», Just In Case Papers, LifeTrove, Afterpath, The Just in Case Binder): perforar por avatar (hijos / viuda / albacea) y por país (US, GB) |
| productividad/planillas-vida | productividad | EN | superficial | 2 huellas US/GB (`notion template`, `excel template`) · 2026-11-12 | apareció por huella el 2026-11-12 (Cosmo Studio 22/28 US, tarjeta; Notion planners de 2 fechas); perforar por formato (Sheets / Excel / Notion) y por tema (finanzas / hábitos / negocio) |
| deportes/planes-practica-entrenadores-en | deportes | EN | profundo | 6 subnichos, ~45 kw US/GB + ALL en 3 ceros + 2 controles AR/ES + 20 sondeos por SKU de The Ascent Club; ~30 páginas contadas · 2026-11-13 | perforado el 2026-11-13: tarjeta Basketball Coach Pro; modo C sobre los hijos |
| deportes/planes-practica-entrenadores-en/futbol-soccer | deportes/planes-practica-entrenadores-en | EN | superficial | 12 kw (5 US + 7 GB) · 2026-11-13 | Soccer Training Pro 22/22 US·GB (87 d, sin ads nuevos en 45 d: posible zombi), hermana de Basketball Coach Pro; The Coaching Playbook 1/5 (BRL) |
| deportes/planes-practica-entrenadores-en/basquet | deportes/planes-practica-entrenadores-en | EN | superficial | 10 kw + ALL en 1 + control AR/ES (`ejercicios baloncesto`) · 2026-11-13 | Basketball Coach Pro 27/27 US (39 d, tarjeta); EBasketballCoach 20/20 posible zombi; GB = cementerio; ES con testers < 7 d (Manuales Listos) |
| deportes/planes-practica-entrenadores-en/beisbol-softbol-cricket | deportes/planes-practica-entrenadores-en | EN | superficial | 9 kw · 2026-11-13 | nadie con 10+ en 3 fechas: Home Coach Cricket 21/21 GB en 2 fechas (padres); Softballpassion 5/5 (EUR) |
| deportes/planes-practica-entrenadores-en/voley-flag-hockey-rugby | deportes/planes-practica-entrenadores-en | EN | superficial | 11 kw + ALL en 2 · 2026-11-13 | HeroeDigitals ≥19 US (¿app?); American Football Academy 7/15; rugby y vóley en GB = cementerio |
| deportes/planes-practica-entrenadores-en/educacion-fisica-docentes | deportes/planes-practica-entrenadores-en | EN | superficial | 2 kw US/GB (`PE lesson plans`, `gymnastics lesson plans`) + control AR/ES (`juegos educación física`) · 2026-11-13 | Digital Academy PE 12/24 US y 11/20 GB (11 d): re-medir 2026-11-20; Orbis Atlas 10/31 ya en español; destino ocupado (EFácil, YTeducativo, Ideasjugadas) |
| deportes/planes-practica-entrenadores-en/fabricas-multisku | deportes/planes-practica-entrenadores-en | EN | superficial | 20 sondeos por SKU + `wrestling practice plans`, `PE lesson plans` · 2026-11-13 | The Ascent Club máx 8 por SKU; Download Studio cheer 7/8; Allsetvault/Zonaebook/DigitalCenter ≤ 8 |
| pareja/custodia-registros | pareja | EN | profundo | 23 kw US/GB + ALL en 2 + 2 controles AR/ES · 2026-11-13 | perforado el 2026-11-13 tarde: 5 hijos superficial; 2 tarjetas (CustodyLogs 47/47 US, Isabella Francis 31/31 US) |
| pareja/custodia-registros/registro-juicio | pareja/custodia-registros | EN | superficial | 5 kw US/GB + control AR/ES (`custodia registro`) · 2026-11-13 | CustodyLogs 47/47 US (274 d, tarjeta; ¿app o archivo?); clones < 7 d (Custody Keeper, Shielded, AntiAlienate): re-medir 2026-11-20; AR/ES = hueco |
| pareja/custodia-registros/organizador-divorcio | pareja/custodia-registros | EN | superficial | 5 kw · 2026-11-13 | `divorce` + binder/planner/checklist/organizer = short-dramas; `divorce workbook` = coaches con cara |
| pareja/custodia-registros/juicio-sin-abogado | pareja/custodia-registros | EN | superficial | 5 kw + ALL en 1 · 2026-11-13 | todo short-dramas; Dads Law School 4/5 (339 d); GB `pro se custody` = cementerio (Plainly Digital $17, Custody Binder) |
| pareja/custodia-registros/plan-parentalidad | pareja/custodia-registros | EN | superficial | 4 kw · 2026-11-13 | abogados, apps (OurFamilyWizard, TalkingParents) y quizzes de TDAH; nadie vende la plantilla |
| pareja/custodia-registros/ex-narcisista | pareja/custodia-registros | EN | superficial | 4 kw + ALL en 1 + control AR/ES (`ex narcisista hijos`) · 2026-11-13 | Isabella Francis 31/31 US (91 d, libro impreso, tarjeta; ¿persona?); Anthony Bompiani ≥47/51 = marca personal; AR/ES = hueco |
| educacion-emocional/actividades-imprimibles | educacion-emocional | ES | superficial | 2 huellas (`cuadernillo PDF`, `libro digital`) + Laura Educa contada por país · 2026-11-13 | apareció por huella el 2026-11-13 (Laura Educa 14/28 ES, 144 d, tarjeta; solo pauta en ES → destino AR); perforar por avatar (padres / docentes / psicólogos) y materia (autoestima / rechazo / navidad); OJO verificar que no roce neurokids |
| plantillas-canva/kits-por-oficio | plantillas-canva | ES | profundo | 6 subnichos, 32 kw + ALL en 1 · 2026-11-13 (tarde) | Mind Digital Studio AR 18/50 piso y Pack Insta de Impacto AR 19/44 (tarjetas); Taller Creativo 15/23 oferta invisible; LaOfi ES 12/50 piso; hijos abajo |
| plantillas-canva/kits-por-oficio/salud-terapeutas | plantillas-canva/kits-por-oficio | ES | superficial | 6 kw + ALL fisio · 2026-11-13 | Med Spa Documents Kit MX 0/48 por entrega (10 por creación, re-medir 2026-11-16); Odonto en Orden AR 0/26 (re-medir 2026-11-19); Cer Solutions 11/18 multi-oficio; `Canva fisioterapeutas` = cementerio |
| plantillas-canva/kits-por-oficio/belleza-estetica | plantillas-canva/kits-por-oficio | ES | superficial | 6 kw · 2026-11-13 | Lash Pro / Nail Pro Catálogo MX 0/14 · 0/13 (tanda del 12-11, re-medir 2026-11-19); Laura Martin ES 6/11; packs BRL genéricos |
| plantillas-canva/kits-por-oficio/profesionales-servicios | plantillas-canva/kits-por-oficio | ES | superficial | 6 kw · 2026-11-13 | Mind Digital Studio AR 18/50 piso (coach 17 + abogados 1, tarjeta; ES/MX/CO = 0); Matriz Digital AR 4/16 (anfitriones); inmobiliarias y contadores sin kits |
| plantillas-canva/kits-por-oficio/gastronomia-emprendedoras | plantillas-canva/kits-por-oficio | ES | superficial | 5 kw · 2026-11-13 | Universo Repostero MX 3/8; Cocina en Regla pausada (0 activos, 39 ALL); `Canva restaurantes` casi hueco |
| plantillas-canva/kits-por-oficio/docentes | plantillas-canva/kits-por-oficio | ES | superficial | 4 kw · 2026-11-13 | Material Educativo AR 5/15 (79 d); Mapasyresumenes MX 2/13 (US$7); `Canva educadoras` casi hueco |
| plantillas-canva/kits-por-oficio/formato-packs-genericos | plantillas-canva/kits-por-oficio | ES | superficial | 5 kw + 4 páginas de la huella · 2026-11-13 | Pack Insta de Impacto AR 19/44 · MX 21/47 (65 d, BRL, tarjeta); Taller Creativo 15/23 oferta invisible; LaOfi ES 12/50 piso; Neri Designer MX 8/50 piso (USD 4-6,90) |
| fe/material-cristiano-imprimible | fe | ES | virgen | 1 huella (`megapack PDF`) · 2026-11-13 | apareció por huella el 2026-11-13: Cristianas con Poder 31/71 bloque (16 CL, «recibe y luego pagas» sin oferta visible), Lumina Biblia, Calendarios de Fe, EducaTlon; perforar por formato (biblia para armar / calendarios / actividades) |
| esoterismo/grimorio-brujeria | esoterismo | ES | virgen | 1 huella (`libro digital`) · 2026-11-13 | apareció por huella el 2026-11-13: Grimorio Cósmico 6/26 (68 d, «El Gran Grimorio de las Brujas»), Universo Mistico; sin cohorte de 10 todavía, seguir |
| tecnologia/electronica-programacion-pdf | tecnologia | ES | virgen | 1 huella (`cuadernillo PDF`) · 2026-11-13 | apareció por huella el 2026-11-13: Macro Aula 5/20 (ESP32, Arduino, PLC, Scratch); El rincón educativo (ejercicios resueltos ingeniería); sin cohorte de 10, seguir |

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
| `LightBurn` / `diseños tazas` / `diseños mdf` / `productos láser` (ES) | short-dramas (8 mil) / tazas físicas / muebles MDF / estética y tóner | `vectores láser`, `plantillas sublimar`, `mockups sublimación` |
| `Cricut proyectos` / `Silhouette Cameo` / `negocio Cricut` / `cortadora vinil` (ES) | vendedores de máquinas e insumos | `Cricut Design`, `Cricut principiantes`, `Cricut guía` |
| `tarjetas imprimir` / `plantillas tarjetas` / `papelería creativa` / `precios sublimación` (ES) | imprimibles genéricos, tiendas físicas, talleres | `tarjetas pop-up`, `plantillas sublimar` |
| página que devuelve **0 con `ALL`** | no está pausada: ya no existe | anotarla como desaparecida |
| página con > 50 activos y los 50 visibles nuevos (BR, nube) | la cohorte queda detrás del tope | `page_ids` + `search_terms` con un par de palabras de un título viejo: destapa los ads viejos (Creartool 23/79, Atividades infantil ≥27); `search_terms: "R$"` se ignora |
| `search_terms` para destapar una página que re-crea todo a diario con un solo título (EN: Donna Whitfield, Stitch Well, Visual Guide Lab, In pictures books) | devuelve los mismos 50 nuevos: no hay ads viejos detrás | anotar «rota todo» y re-medir; solo destapa si hay títulos viejos distintos (Crochet Nook `Granny Square` 28/50) |
| un whale migra de página sin apagar el negocio | contar solo la página madre lo da por muerto | contar también las páginas hermanas de su ficha |
| barrido por keyword en EN (`printable`, `instant download`) | la API los ordena del más nuevo: casi todo tiene < 2 d y la cohorte no se ve | usar la huella para leer nombres de página y contar cada una con `page_ids` + `countries` |
| `protocol` / `blueprint` (EN) | suplementos, advertoriales con persona, granjas de juegos y dramas | entregable + tema |
| `printable` solo (GB) | quiz-funnels de dieta (Eat Smart, High.diet) | `printable planner`, `printable pages` |
| `Security+` (EN) | el «+» se pierde y trae «security guide» (guardias, ficción) | `CompTIA Security` |
| `divorce` + binder/planner/checklist/organizer, `custody journal`, `co-parenting log`, `parenting time log` (EN) | novelas «click to read» y short-dramas: cero señal | `custody binder`, `narcissist custody`, `high conflict co-parent`, `parallel parenting` |
| `custody court` / `family court` / `court ready` / `custody hearing` / `parenting plan` / `custody documentation` (EN) | short-dramas, pickleball, quizzes de TDAH, arbitraje «pro bono lawyers» | ídem arriba + `page_ids` de los clones |
| `in pictures` (EN) | el token «in» matchea todo (1,3 M en US) | `made visual`, `visual guide` |
| `mini course` (EN) | short-dramas | `video lessons` + tema |
| `guia completo` (BR) | short-dramas y novelas en USD | `guia prático pdf`, entregable + tema |
| `passo a passo pdf` (BR) | 375 mil resultados de ruido (clínicas, solar, B2B) | `atividades imprimir`, `planner digital` |
| `acesso vitalício` (BR) | eventos en vivo y marcas personales | `mapas mentais`, `kit digital` |
| `te lo envío` / `paso a paso PDF` (ES) | físicos con pago contra entrega, cremas, clínicas (220-470 mil resultados) | `plantillas editables`, `kit digital`, `descarga inmediata` |
| `diseños bordado` / `kit imprimible` / `plantillas cajas` / `bisutería PDF` (ES) | ropa bordada y DTF / kits de lectoescritura / plantillas de cerámica y Canva / cursos presenciales de resina | `patrones bordado`, `papercraft plantillas`, `toppers imprimibles`, `macramé patrones` |
| `agujas` (ES, tejido) | estética facial («sin agujas») | `patrones palillos`, `patrones ganchillo` |
| `patrones crochet` / `patrones navideños` (ES) | una página de WA (Sofía Ramírez, ~180 ads) se come el top 50 | `amigurumis venden`, `belén ganchillo`, pares de tema |
| página con un solo título ×50 y 100-300 estimados (ES: Talleres Listos, Atril Estudio) | el tope de 50 devuelve solo los nuevos: cohorte 0 que no es real | anotar como «cohorte oculta» y re-medir; nunca dar por muerta |
| `prayer planner` / `teacher planner` (EN) | short-dramas («2000 readers are reading now») | `christian planner`, `lesson planner pdf`, `digital planner goodnotes` |
| `planos de aula prontos` / `projeto datas comemorativas` (BR) | ruido de ShortMax y genérico | `plano de aula BNCC`, `sequência didática pdf` |
| `wife stopped` / `husband distant` / `get ex back` / `after affair` / `no contact` / `dead bedroom` / `save marriage guide` (EN) | short-drama («He cast aside the wife…») incluso con ALL | `couples workbook`, `marriage workbook pdf`, `rebuilding trust workbook`, `save marriage ebook` |
| `date night printable` (EN) | regalos físicos (mantas, cajas) | `couples workbook`, `relationship workbook pdf` |
| embudo WA con título vacío (BR, nube) | la API solo devuelve el título del link: sin oferta visible, el test del copy no se puede hacer desde la nube | señal + verificar en la PC |
| `dog clothes pattern` / `learn to sew` / `sewing for beginners` / `tote bag pattern` / `quilting patterns` / `stuffed animal pattern` (EN) | short-dramas, gimnasios, dropshipping de bolsos, kits físicos de quilt, advertoriales | `dog sewing patterns`, `sewing pattern bundle`, `purse pattern pdf`, `quilt pattern pdf`, `crochet pattern pdf` + conteo por página |
| `pago único` / `guía práctica` / `pack digital` (ES) | cosmética, marcas personales, novelas y short-dramas en inglés | `planner imprimible`, `fichas imprimibles`, `plantillas imprimibles` |
| consulta de 9 países con `page_ids` en una página grande (ES) | devuelve los 50 más nuevos y esconde la cohorte (Talleres Listos 0/50 en el bloque, 20-24 por país) | página con 50 devueltos → contar siempre por país |
| página-persona que cambia de nombre («Dra.» → «Prof.») | fachada, no marca de autoridad; igual hay que ver si hay cara en los creativos | juzgar por los creativos en la PC |
| `kit aprovação` / `método aprovação` / `ciclo estudos` / `banco questões` (BR) | autos, solar, crédito, tarot, short-dramas, residencia médica | `caderno questões`, `questões banca`, `mapas mentais concurso` |
| `lei seca` / `legislação grifada` / `questões comentadas` (BR) | ley de tránsito / una mentoría / marcas personales | `lei seca pdf`, `legislação esquematizada` |
| `guia de bolso` / `cardápio semanal` / `download imediato` (BR) | «cabe no bolso» / marmitarias físicas / una sola página (Mestre da Madeira ×20) se come el top 50 | `templates canva`, `pack de artes`, `receitas fit pdf` (la única que trae ads de 60+ d) |
| `ebook pdf` / `guia ilustrado` (BR, noviembre) | lanzamientos de Navidad de hoy y ebooks gratis con persona | entregable + tema; contar por `page_ids` |
| página que lanza 15-40 ads de golpe con «⭐4,8/5 avaliações» (BR) | parece fuerte y tiene cohorte 0 (Ateliê Próspero 0/37, Habilidades dos Avós 0/19) | re-medir a la semana |
| página-catálogo con varios SKU (BR) | la cohorte de la página mezcla ofertas | `page_ids` + `search_terms` del título del SKU (Templates: figurinhas 27/27) |
| `exercícios TCC` / `fichas TCC` / `baralho terapêutico` / `cartas terapêuticas` / `relatório psicológico` / `prontuário psicológico` / `workbook ansiedade` (BR) | TCC = tesis universitaria; tarot y constelación; abogados BPC y dramas; SaaS; palabra no nativa | `técnicas TCC prontas`, `caderno terapêutico`, `recursos terapêuticos`, `dinâmicas terapêuticas` |
| `books of the bible` / `Revelation explained` / `bible timeline` / `visual bible` (EN) | stopwords (849 mil) / short-dramas / chart Adams físico y ~10 clones | `bible study printable`, `scripture cards printable`, `sunday school printable` |
| `bible verse cards` / `bible memory verses` / `bible study course` / `sunday school curriculum` / `bible activity pages` (EN) | Biblia etíope con páginas-persona falsas, dropshippers generalistas, curricula genéricas, advertoriales de salud | entregable + tema; contar por `page_ids` |
| API con `search_terms` en páginas de >50 ads/semana (ES) | la API devuelve igual los 50 más nuevos: la cohorte no se destapa (Aprendia 2/3, Studio Facile, Neutral Nature ES/MX) | medir por país con menos ruido o re-medir cuando frene la página |
| `ejercicios terapia` / `terapia adicciones` / `prevención recaídas` / `psicología deportiva` / `herramientas coaching` / `kit coaching` / `rutinas editables` (ES) | fisio y kinesio, clínicas de rehabilitación, universidades, certificaciones, ruido en inglés, y una red de páginas con títulos de solo estrellas (ReDuca, EstDuc, ApreDuc, EduPro, AprenEdu) | `plantillas psicólogos`, `terapia pareja ejercicios`, `plantillas entrenadores`, `planes alimentación editables` |
| `lifetime access` / `swipe file` / `video lessons` / `$9.99 guide` (EN) | short-dramas (16-36 mil), coaches con cara, ruido | `printable binder`, `notion template`, `excel template`, `toolkit pdf` |
| `mapas` solo / `mapas visuais` / `mapas anatomia` / `mapas história` / `resumos visuais` (BR) | astrología y numerología, lash mapping y mapas capilares, estética, Biblia infantil y juegos, cábala en USD | `mapas` + materia de carrera (`mapas farmacologia`, `mapas cinesiologia`, `mapas devops`) y contar por `page_ids` |
| `marmitas fit` / `marmitas semana` / `cardápio marmitas` / `doces fit` / `doces sem açúcar` / `receitas sem glúten` / `pão sem glúten` / `receitas sem lactose` / `airfryer saudável` / `lanches airfryer` (BR) | marmitarias, docerías y panaderías físicas, tés y suplementos, Polishop y Carrefour | `receitas airfryer ebook`, `receitas airfryer fit`, `bolo fit receitas`, `sobremesas low carb` |
| `apostilas receitas` / `receitas zero açúcar` / `receitas saudáveis ebook` / `dieta receitas ebook` / `livro receitas saudáveis` (BR) | recetas para renda extra, médicos-persona con desafío de ayuno, libros físicos | entregable + tema angosto, contar por `page_ids` |
| `search_terms` = una palabra del nombre de la página (BR: `arquivos` en Arquivos que encantam) | matchea todos los ads de la página: no dice qué vende | la materia o el entregable (`cinesiologia` identificó 29/29 en Edufisicavisual, de títulos de solo estrellas) |
| `mapas OAB` / `mapas engenharia` / `mapas de revisão` / `Leg Educação` (BR) | suscripciones y apps / concursos (Transpetro) / concursos / no es legislación (audio, mega hair) | `mapas direito constitucional`, `direito esquematizado` |
| `first aid guide` / `medical emergency guide` / `food storage guide` / `long term food storage` / `survival manual` / `off grid guide` / `family emergency plan` / `bug out bag checklist` (EN) | short-dramas («Survival Live», «The Last Shelter»), suplementos, decenas de miles de ruido | `first aid printable`, `survival skills pdf`, `emergency plan printable`, `blackout binder`, `hurricane preparedness guide` |
| advertoriales «If you're a parent or grandparent, read this» (EN, prepper) | familia de páginas (American Ready, Prepared American, Homefront Ready, David Miller) que vende un kit físico: pasa el volumen sin ser infoproducto | ver el producto antes de contar |
| `agenda 2027` / `agenda digital` / `agenda emprendedora` / `agenda universitaria` (ES) | el verbo «agenda tu cita» (concesionarias, clínicas, inmobiliarias) y universidades | `vaciar mente`, `planner hábitos`, `planner autocuidado` |
| `planner hogar` / `planner negocio` / `planner redes` / `planner 2027` / `organizar hogar` (ES) | wedding/event planners, SaaS, constructoras, muebles | `plantilla Notion` + oficio, `planner` + par de dolor |
| `calendario 2027` / `brain dump` / `diario gratitud` / `control gastos` / `reto ahorro` (ES) | imprentas físicas / short-drama en inglés / novelas / short-drama doblado | `vaciar mente`, `finanzas personales plantilla` |
| `tee ball practice` / `hockey practice plans` / `practice plans` / `drill cards` / `season plan coach` / `basketball playbook` (EN) | golf / novelas románticas («Hockey Rival») / ruido amplio / cartas coleccionables | `basketball coaching plans`, `PE lesson plans`, `wrestling practice plans`; en GB `football` en vez de `soccer` |
| sondear a The Ascent Club por deporte (EN) | escribe el deporte con emoji (🏓 🏐 ⚽): el nombre del deporte da 0 | sustantivos de actividad (`troop`, `ice`, `wall`, `deck`, `mat`) + `page_ids` + país |
| `envío inmediato` / `S/ 15` y precios en soles sueltos (ES) | short-dramas, físicos contra entrega, cosmética (17 mil); soles sueltos → novelas EN/FR (1 M) | `megapack PDF`, `plantillas Canva`, `láminas imprimibles`, `soles PDF` + tema |
| `apostila modelagem` / `moldes prontos` / `moldes para vender` / `molde cesto` / `molde tamanho real` / `moldes infantil` (BR, costura) | biscuit, biscoitos, barbeiro / papelaria y topos de bolo / capelinhas de papel / Betano / actividades escolares | `molde` + prenda concreta (`molde avental`, `molde naninha`, `molde necessaire`); Maximus Tecidos aparece en todo: tienda de tela, no contar |
| `pet` en portugués (BR) | botella PET, SHEIN | `molde cachorro`, `moldes pet` + mirar página |
| `cuaderno de trabajo` (ES) | short-dramas y cuadernos físicos | `cuadernillo PDF`, `megapack PDF` |
| página «plantillas Canva» con título único «Haz clic en Más información» (ES: Taller Creativo, LaOfi, Mind Digital Studio) | la cohorte se mide pero la oferta no se ve por API: puede ser plantilla o mini-curso | contar igual, pero verificar en la PC qué vende antes de dar tarjeta |
| `megapack` + «OFERTA SOLO POR HOY» con título genérico (ES: Pro Academy, Impulso Creativo, Megapack Online) | producto invisible por API | re-medir y abrir snapshot en la PC |
| `plantillas uñas` / `plantillas consultorio` / `posts psicología` (ES) | plantillas para calzado, podología y ortopedia / psicólogas promocionando su propio IG | `Canva` + oficio |
| `Canva coaches` / `Canva Airbnb` / `Canva estética` / `plantillas contadores` / `plantillas inmobiliarias` (ES) | vendedores en inglés, packs BRL en español, cursos y CRM | leer moneda e idioma; `Canva abogados`, `Canva lashista` |
| nombre de página con «en» como `search_terms` (ES: «Cocina en Regla») | el token «en» trae 2 mil de basura | el nombre pegado (`cocinaenregla`) con ALL, después `page_ids` |
| `page_ids` + `search_terms` (ES, nube, 2026-11-13) | el término se ignora: devuelve los mismos 50 nuevos (LaOfi) | anotar la cohorte como piso y re-medir |

## Operadores a seguir (modo C)

Fábricas multi-SKU y whales que muestran el próximo producto antes de que aparezca por keyword. Se
enumeran con `page_ids` + `countries`, siempre con el país. Cadencia: quincenal salvo que diga otra cosa.

| Operador | page_id | País | Por qué se lo sigue |
|---|---|---|---|
| Mind Digital Studio | 100484571813019 | AR | kits de marca + gestión por oficio (coach 17, abogados 1), 18/50 piso (tarjeta 2026-11-13); ¿SKU u oficio nuevo? ¿salta a ES? re-medir 2026-11-20 |
| Pack Insta de Impacto | 802396849634003 | AR · MX · ES | pack de plantillas IG en BRL, 19/44 AR a 65 d (tarjeta 2026-11-13); página homónima 1194180837101878 sin contar |
| Med Spa Documents Kit | 1318045718067882 | MX · CO | documentos para estética, 48 activos con 10 en el borde de la cohorte; re-medir 2026-11-16 |
| LaOfi | 101087078492489 | ES · MX | kit para diseñadores, ES 12/50 piso con cohorte detrás del tope; re-medir 2026-11-20 |
| Hadassa Fit | 769240466269366 | BR | recetas fit para airfryer, 14/26, tandas cada 2-4 semanas desde el 01-08 (tarjeta 2026-11-12) |
| Cozinhanoprato | 1143346648872228 | BR | colección de 4 ebooks de recetas, 14/14 a 32 d (tarjeta 2026-11-12); re-medir 2026-11-19 |
| Receitas Emagrecedoras | 1036943289509621 | BR | embudo WA de recetas para adelgazar, ≥42/≥50; ver si aparece la oferta |
| Visual Guide Lab | 1467890346400480 | US | libros ilustrados para exámenes, mucho volumen sin cohorte (2026-11-09); mismo molde que In pictures books 1354208894450767, Illustrated Manuals 1459350803924436 y Avenlo 1434008009790850 (en español) |
| The Lost Skills of Independence | 984264748113661 | US · GB | libro físico de 200 habilidades, ≥50 en cohorte (2026-11-12); molde de la ola hispana de «habilidades de los abuelos» |
| Fallback Book | 1388539597681148 | GB | plan de emergencia personalizado por dirección, 18/18 (2026-11-12); ver si escala o abre US |
| Food Storage Tips | 724248187440810 | US · GB | advertorial de despensa con ads de 394 d en GB; producto sin ver |
| Honey Home | 1334135786448993 | US · GB | tarjeta del 2026-11-09: ver si la cohorte sigue creciendo |
| Dragon Fire Method | 163589696835008 | GB · US | whale de plantillas NIST/infosec, tarjeta del 2026-11-09 |
| Your Consulting Management Guide | 1097413493462052 | US · GB | tarjeta EN del 2026-11-11: guías PDF de management «Instant PDF Download», 41/46 US y 34/38 GB, ad de 144 d; Black Friday 40% OFF |
| Linda Harrison | 778821148649074 | US · GB | 44/≥50 en cohorte (2026-11-09); 43/55 US y 17/20 GB en la tarjeta EN del 2026-11-10 (junto a Heroic Husband); formato y cara sin verificar |
| Creartool | 325627053956826 | BR | tarjeta del 2026-11-09 (manual de estructuras narrativas, 23/48); testea versión «30 estruturas» |
| Daily Routine Club | 671948206009244 | BR | tarjeta del 2026-11-09 (planner de rutina/estudios, 14/22) |
| Prof. Mariana Oliveira | 1080842931788422 | BR | tarjeta del 2026-11-09 tarde (Atividades Investigativas, 19/48); persona de fachada (Dra.→Prof.), paga en USD |
| Criativizando e Educando | 430307330169512 | BR | 14/32 con ad de 84 d, WhatsApp sin oferta visible por API; 16/32 el 2026-11-10: verificar en la PC |
| Loja das Profs / Prof Jaque Mendes | 1002633749601439 · 105209655117919 | BR | mismo operador, 187 activos est., cohorte detrás del tope |
| Pequenos Leitores | 1196621566868514 | BR | 12/35 el 2026-11-09 con hueco de 2 meses; el 2026-11-10 se apagó (4/4, ahora «Leitura Descomplicada», sin ads en 70 d): bajar a mensual |
| Atividades infantil | 265589206630616 | BR | ≥27/233 el 2026-11-10 (destapada con `search_terms`), ad de 42 d; cierra por mensajes sin oferta visible: verificar en la PC (y que no sea neurokids) |
| Lacuna Concursos | 1173569735845788 | BR | material para concursos «Baixe Agora», ≥4/89 el 2026-11-10 (ayer ≥15): ¿pago o lead magnet? |
| Sector Digital | 1122535934265327 | AR · ES · MX | tarjeta ES del 2026-11-09 (sistema de sesiones para psicólogos deportivos, 25/≥50); abrió línea «adicciones» el 08-11; 2026-11-11: AR ≥15, ES ≥28, MX ≥14 (≥31 únicos, todo deportiva; adicciones 0) |
| Digital Academy | 858372700683858 | MX · AR · BO | multipack con WA, 15/41 y ads de 88 d; ver qué SKU se queda con la cohorte |
| Talleres Listos | 1423115024221032 | hispano | 304 est. con un solo título; contado por país el 2026-11-10: AR 20, ES 24, MX 21 en cohorte (pasa la vara, ya en los dos destinos); tarjeta ES del 2026-11-12: ES ≥26/50, MX ≥22/50, AR ≥12/50, sigue escalando |
| Biblioteca Creativa | 1244762302063129 | hispano | guías Cricut/Silhouette 8/26 (09-11) → 10/25 (10-11, tarjeta ES tarde); clon en inglés Creative Library 1362229870302077 |
| Neutral Nature | 919376131265589 | CO · ES · MX · AR | tarjeta ES del 2026-11-10 (tarde): 300 tarjetas pop-up, 47/47 CO; ES 130 y MX 128 con cohorte oculta: re-medir 2026-11-17; clon Pura Idea 1422137500990129 |
| Pixelpack | 116045223625247 | hispano | megapack DTF/sublimación US$9,99, ≥29/62 con ad de 108 d (2026-11-10) |
| Crea y Emprende | 1056023200924288 | AR · ES | tarjeta ES del 2026-11-09 tarde (Navidad Tejida / Florería Tejida, AR 17/20); ver qué tema sigue después de Navidad |
| Cursos Online | 512123288644096 | MX | tarjeta ES del 2026-11-09 tarde (papercraft / pueblito navideño, 11/24); ver si «120 casitas» entra en cohorte |
| La Biblioteca Definitiva De Tejido | 1151253608079340 | hispano | 23/23 sin ads nuevos en ~49 d: ¿zombi o escala vieja? |
| This & That Planners | 1007996855726476 | US · GB | tarjeta EN del 2026-11-09 (tarde): planner digital perpetuo 10/50; ver si la tanda de 22 del 09-11 sobrevive |
| Planner Lovers | 128972030308501 | US · GB · AR · ES · MX | tarjeta EN del 2026-11-09 (tarde): planner digital 2027 28/28 US; operador hispano, le toca seguirlo también a ES |
| Heroic Husband | 234796816378250 | US · GB | tarjeta EN del 2026-11-10 («$8 Book», salvar el matrimonio, 47/53 US, 45/45 GB); ver si el libro es digital y qué es la «7 Day Trial» |
| Donna Whitfield | 1180278161845468 | US | 553 est. con un solo título (cohorte oculta, 2026-11-10); re-medir 2026-11-17 |
| The EaseUp Planners | 1194131877121706 | US | 140 est. con cohorte oculta (relanzó todo el 06/07-11); re-medir 2026-11-16 |
| Planner Hoy Solo 3 | 1280820831792286 | ES · MX | tarjeta ES del 2026-11-10 (planner para vaciar la cabeza, 21/35 ES); ver si entra a AR |
| Biblioteca maestra: Planos de arcilla | 1435630566293933 | AR | tarjeta ES del 2026-11-10 (246-248 plantillas de cerámica, ≥16/≥50); seguir con su clon Planos de Barro 1463269926874211 (USD, de hoy) |
| Red Aprendia | 1380966491766673 · 1372902832576549 · 1288181344388955 | MX · PE · hispano | fichas visuales de estudio, 342-659 est. por página con cohorte oculta; contar por país |
| Aprendia : Guias profesionales | 1319574141233447 | MX | tarjeta ES del 2026-11-11: packs de 50 fichas por oficio, MX 38/50 (63 est.), AR/ES 0; la única de la red que deja correr ganadores |
| Derecho en Mapas | 1356269490904663 | CO | tarjeta ES del 2026-11-11: mapas de Derecho Penal/Administrativo, CO 10/34, operador BR; hermana Mapas del Derecho 1404914672699239 |
| IA Programas | 809461785581622 | MX | 16/22 el 2026-11-11 con títulos vacíos: ver qué vende |
| Mapa Concursos | 113788658419021 | BR | tarjeta BR del 2026-11-10 tarde (+120 mapas mentais de enfermagem, 39/50); ver si «Receba Agora» es otro pack |
| 123passei | 109322741722198 | BR | tarjeta BR del 2026-11-10 tarde («Protocolo» por concurso R$27,90, 18/34, 162 d) |
| Trilha do Estudo | 641390105728644 | BR | ≥40/50 el 2026-11-10; apostila + app de preguntas: ¿PDF o suscripción? |
| Knitting Art Studio | 852298534641160 | US | tarjeta EN del 2026-11-10 (tarde): 100+ patrones de costura para mascotas a $27 + lead magnet, 40/50 |
| The Crochet Nook | 534358449768435 | GB · US | tarjeta EN del 2026-11-10 (tarde): megapacks de crochet, 44/50 GB; US 189 est. con cohorte oculta |
| Sewing Lovers | 1341379315722832 | US · GB | tarjeta EN del 2026-11-11: patrones PDF de bolsos a $9,99, 19/50 US (piso) y 8/37 GB; joven (ad más viejo 30 d) |
| Stitch Well / Elsie Brooks | 684792994717005 · 269275822943681 | US · GB | 409 y 269 est. con cohorte oculta (mismos creativos); 2026-11-11: 433/395 y 318 est., 0/50, `search_terms` no destapa; re-medir 2026-11-17 |
| Templates - Pack de artes | 123045347437517 | BR | tarjeta BR del 2026-11-11 (figurinhas para stories R$3,99, 27/27, 217-293 d); catálogo de packs a R$1,49-3,99: ver qué SKU nuevo entra en cohorte |
| Mestre da Madeira | 1240001732528839 | BR | tarjeta BR del 2026-11-11 (+100 moldes de madeira PDF R$12,90, 11/50, escalando) |
| Ponto Certo App | 1037269729466043 | BR | tarjeta BR del 2026-11-13 tarde (molde avental japonês PDF + videoaula, 10/24, 114 d); probando Cesto Baleia y Chinelo de Tecido: ver qué SKU entra en cohorte |
| Mamãe que fez | 1104742249386376 | BR | tarjeta BR del 2026-11-13 tarde (naninha R$17, 11/17, 12 d); re-medir 2026-11-20 |
| Ana Beatriz (moldes) | 500613633701984 | BR | ≥30/≥50 el 2026-11-13 (moldes infantiles + curso, USD, 47-56 d); ¿persona? verificar en la PC |
| Clube do Devocional | 1333933036463024 | BR | ≥43/50 el 2026-11-11 con 40 ads de un solo día (7 d); WA sin oferta; re-medir 2026-11-18 |
| Arquivos que encantam | 216603914872916 | BR | 25/33 el 2026-11-11 («Apenas R$10», producto no visible): verificar en la PC |
| Biblioteca Digital (deportes) | 1270799516117158 | AR | tarjeta ES del 2026-11-11 tarde (planificación anual de vóley/newcom/básquet/handball a $19.990, 25/33 AR, 63,6 d); ver si entra a ES o a otro deporte |
| Consultorio Nutri Listo | 1431610173366748 | AR | sistema de consultorio para nutricionistas, 6/40 el 2026-11-11 (página de 8 d); tarjeta ES del 2026-11-12: AR 13/42, solo AR; re-medir 2026-11-18 |
| NeuroKit Clínico | 964287390098744 · 883009701566343 | BR · ES · FR · DE | tarjeta BR del 2026-11-11 tarde (fichas TCC para psicólogos, 34/50); la hermana ya corre en español/francés/alemán: ver si la versión en español entra en cohorte |
| Terapia Cognitiva Online | 836423469737678 | BR | tarjeta BR del 2026-11-11 tarde («88 técnicas de TCC prontas», 19/33, 45 d) |
| Nova Era Recursos Terapêuticos | 114755404813290 | BR | tarjeta BR del 2026-11-11 tarde (cadernos de bolso para terapeutas, 25/42, 53 d); lanzó Planner Psi y Metáforas: ver cuál entra en cohorte |
| RootedinFaith | 1339338722596915 | GB · US | tarjeta EN del 2026-11-11 (tarde): guía para entender la Biblia, 30/45 GB y 28/≥50 US, ad de 33 d; formato sin verificar |
| Revelation Unsealed 3D | 1345541285309886 | US | 8/23 el 2026-11-11 («Visual Guide to Revelation», 168 páginas); re-medir 2026-11-14 |
| Valentina Ríos | 1280761195116636 | US · AR · ES | papelería cristiana de reventa, 17/26 US (BRL, español); ya en AR/ES; le toca seguirla también a ES |
| Mapasyresumenes | 234866809700963 | ES · CO | guías «2027 en 150 páginas»: el 2026-11-12 lanzó oposiciones españolas a 12,90 € (20 ads en ES); re-medir 2026-11-19 |
| Growing in Faith / Faith Times | 1329678806897080 · 1241869225684857 | US | 18/27 y 7/36 el 2026-11-11, advertorial infantil-cristiano, producto no visible |
| My Estate Kit | 1091977304009213 | GB | tarjeta EN del 2026-11-12: kit digital de sucesión (~£29), ≥50/50 GB, 115 d; contar US y seguir al cluster (Atlas Media Group 1254679187727827, Afterpath 1016389298235387) |
| Cosmo Studio | 209343218938190 | US · GB | tarjeta EN del 2026-11-12: planilla de vida a $9, 22/28 US y 21/25 GB, 72 d; abrió SKU de invitaciones en Canva el 12-11; hermanas probables Her Notion Planner 1282088321645043 y Ultimate Notion Planner 425210960671076 |
| The Ascent Club | 102421131594782 | US · GB | ≥58 en cohorte US por sondeos (228 est., multi-SKU de planes de práctica para entrenadores); hermana Download Studio 1344017652136102 |
| CustodyLogs | 959544217247977 | US | 44/49 el 2026-11-12; 47/47 el 2026-11-13 tarde (274 d, EUR, tarjeta); ¿app o PDF? verificar en la PC |
| Isabella Francis | 201865639680760 | US | 31/31 el 2026-11-13 tarde (libro impreso de ex narcisista + Recovery Set, 91 d, tarjeta); ¿persona? |
| Clones de CustodyLogs: The Custody Keeper · Shielded Co-Parenting · AntiAlienate | 1366011646600864 · 1280648655122547 · 1066259219910194 | US · GB | 0/4, 0/5, 0/5 el 2026-11-13: re-medir 2026-11-20 |
| TI em Mapas | 1171375182736345 | BR · hispano | tarjeta BR del 2026-11-12 (+300 mapas mentales de TI, 41/49, 77,7 d); lanzó versión en español el 10-11: contarla por país AR/ES/MX |
| Farmácia Mapeada | 105693778467803 | BR | tarjeta BR del 2026-11-12 (farmacología ilustrada 15/20, página ≥32/≥50, 78 d); ¿PDF o impreso? |
| Marcelomapas | 100945228762390 | BR | direito ilustrado R$17 / OAB R$97, ≥22/143 est. (79,5 d) el 2026-11-12; verificar si hay cara |
| Mapas Visuais & ilustrados | 1316538911539485 | BR | ≥22/50 (117 est.) con títulos de solo estrellas el 2026-11-12: ver qué vende |
| Claridad y Acción | 771123896085843 | AR · ES · MX | plantillas Notion por oficio, 30/40 y un SKU nuevo cada 1-2 semanas (2026-11-12): muestra el próximo oficio |
| Mente Ordenada | 1084424138077543 | hispano | 0/40 en 6 días con el molde «vaciá tu cabeza» (2026-11-12): re-medir 2026-11-19 |
| Pack Digital Emprendor | 104462436003652 | AR | 18/18, 108 d, producto no visible por API (2026-11-12) |
| Edufisicavisual | 1293268003864355 | BR | tarjeta BR del 2026-11-13 (mapas de cinesiología para educación física, 26/29, 12,7 d); re-medir 2026-11-20; ¿Lucia Ortiz 760125220506555 es su versión en español? |
| Brinca e Aprende | 942354795618344 | BR | inglés infantil imprimible, 10/37 el 2026-11-13 (los 10 de un solo día) + 3 SKU nuevos; re-medir 2026-11-18 |
| Basketball Coach Pro | 1373186709203115 | US | tarjeta EN del 2026-11-13: pack de básquet «Today only: $14.90», 27/27, 39 d; hermanas Soccer Training Pro 1234094106455284 (22/22 US·GB, sin ads nuevos en 45 d) y 1543066612216569, Jonathan Ross 429439973597227 (BRL) |
| Digital Academy (EF) | 1340771395780798 | US · GB | «150 PE games», 12/24 US y 11/20 GB con 11 d (2026-11-13); re-medir 2026-11-20 |
| HeroeDigitals | 1258628903995580 | US | planes de práctica multi-deporte, ≥19/50 (84 est.), 21 d (2026-11-13); ¿app o PDF? |
| Laura Educa | 109425057952071 | ES | tarjeta ES del 2026-11-13: actividades emocionales imprimibles, 14/28 ES, 144 d; solo pauta en ES → ver si abre AR y confirmar que no es marca personal ni neurokids |
| Taller Creativo | 1156743057524645 | AR · MX | plantillas Canva, 15/22 AR y 15/23 MX (36 d, 12 fechas) con título único «Más información»: oferta invisible por API; verificar en la PC qué vende |
| Cristianas con Poder | 1306900159163457 | MX · AR · CL | ex «Pequeños Cristianos», 31/71 bloque (16 CL), «recibe y luego pagas» sin oferta visible (2026-11-13); re-medir 2026-11-20 |
| Axo y Yo | 1358953320636772 | MX | cuadernillos escolares por grado $149 MXN, 10/20 pero cohorte de una sola fecha (05-11); re-medir 2026-11-20 |
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
| 2026-11-14 06:36 | BR | A huella (mañana) | — (huella, BR) | en curso | en curso | en curso |
| 2026-11-13 18:42 | ES | B perforar (tarde) | plantillas-canva/kits-por-oficio | 6 subnichos, 32 kw nativas + ALL en 1; ~22 páginas contadas (3 subagentes de lectura) | 2 tarjetas (Mind Digital Studio, Pack Insta de Impacto), 8 señales | profundo, con 6 hijos superficial; 4 operadores a seguir |
| 2026-11-13 18:40 | EN | B perforar (tarde) | pareja/custodia-registros | 5 subnichos, 23 kw US/GB + ALL en 2 + 2 controles AR/ES; ~15 páginas contadas (2 subagentes de lectura) | 2 tarjetas (CustodyLogs, Isabella Francis), 5 señales | profundo, con 5 hijos superficial; 3 operadores a seguir |
| 2026-11-13 18:36 | BR | B perforar (tarde) | costura/moldes-pdf-br | 6 subnichos × 5 kw BR (30) + 3 controles AR/ES/MX/CO (sin ceros, ALL no hizo falta); ~30 páginas contadas (3 subagentes de lectura) | 2 tarjetas (Ponto Certo App, Mamãe que fez), 6 señales | profundo, con 6 hijos superficial; 3 operadores a seguir |
| 2026-11-13 06:45 | ES | A huella (mañana) | — (huella, hispano) | 12 huellas ES (3 subagentes de lectura) + ~40 páginas contadas por país | 1 tarjeta (Laura Educa), 7 señales | 5 nodos nuevos ES; 4 operadores a seguir; 5 trampas nuevas |
| 2026-11-13 06:40 | EN | B perforar (mañana) | deportes/planes-practica-entrenadores-en | 6 subnichos, ~45 kw US/GB + ALL en 3 + 2 controles AR/ES + 20 sondeos por SKU; ~30 páginas contadas (3 subagentes de lectura) | 1 tarjeta (Basketball Coach Pro), 6 señales | profundo, con 6 hijos superficial; 3 operadores a seguir |
| 2026-11-13 06:36 | BR | C operadores (mañana) | — (operadores BR) | 32 page_ids (36 consultas `page_ids` + país, BR y AR/ES/MX), 13 sondas `search_terms` sobre página, 3 controles hispanos; 3 subagentes de lectura | 1 tarjeta (Edufisicavisual), 10 señales | sin cambios de estado; 2 operadores nuevos a seguir (Edufisicavisual, Brinca e Aprende) |
| 2026-11-12 18:45 | ES | B perforar (tarde) | productividad/planner-vaciar-cabeza | 7 subnichos, 35 kw nativas + ALL en 2 ceros; ~25 páginas contadas (3 subagentes de lectura) | 2 tarjetas (Claridad y Acción, Mente Inquieta), 7 señales | profundo, con 7 hijos superficial + 1 nodo nuevo (productividad/plantillas-notion-oficios); 3 operadores a seguir |
| 2026-11-12 18:40 | EN | B perforar (tarde) | hogar/preparacion-emergencias | 6 subnichos × 4-5 kw US/GB (25) + ALL en 1 + 2 controles AR/ES; ~25 páginas contadas (2 subagentes de lectura) | 2 tarjetas (The Lost Skills of Independence, Fallback Book), 6 señales | profundo, con 6 hijos superficial; 3 operadores a seguir |
| 2026-11-12 18:36 | BR | B perforar (tarde) | receitas/ebooks-fit | 6 subnichos × 5 kw BR (30) + 1 de arranque + 1 control AR/ES (sin ceros, ALL no hizo falta); ~45 páginas contadas | 2 tarjetas (Hadassa Fit, Cozinhanoprato), 5 señales | profundo, con 6 hijos superficial; 3 operadores a seguir |
| 2026-11-12 06:41 | ES | C operadores (mañana) | — (operadores ES) | 24 operadores (27 page_ids), ~45 consultas `page_ids` + país, 3 sondeos `search_terms` | 2 tarjetas (Talleres Listos, Consultorio Nutri Listo), 8 señales | sin cambios de estado; 1 operador nuevo a seguir (Mapasyresumenes) |
| 2026-11-12 06:40 | EN | A huella (mañana) | — (huella, US GB) | 15 huellas × US/GB (30, distintas de las del 09-11); ~40 páginas contadas con `page_ids` + país | 2 tarjetas (My Estate Kit, Cosmo Studio), 6 señales | 4 nodos nuevos (2 superficial, 2 virgen); 4 operadores a seguir |
| 2026-11-12 06:36 | BR | B perforar (mañana) | mapas-visuais-r10 | 6 subnichos × 5-6 kw BR (32) + 1 de arranque + 2 controles AR/ES/MX/CO (sin ceros, ALL no hizo falta); ~45 páginas contadas | 2 tarjetas (TI em Mapas, Farmácia Mapeada), 5 señales | profundo, con 6 hijos superficial; 4 operadores a seguir |
| 2026-11-11 18:42 | ES | B perforar (tarde) | salud-mental/sistemas-de-sesiones | 6 subnichos, 27 kw nativas (sin ceros); ~45 páginas contadas (Sector Digital y Biblioteca Digital por país) | 1 tarjeta (Biblioteca Digital), 6 señales | profundo, con 6 hijos superficial + 1 nodo nuevo (deportes/planificacion-entrenadores) |
| 2026-11-11 18:38 | EN | B perforar (tarde) | religion/biblia-visual | 6 subnichos × 5 kw US/GB (30) + 1 de arranque + 2 controles AR/ES; ~20 páginas contadas (sin ceros, ALL no hizo falta) | 1 tarjeta (RootedinFaith), 6 señales | profundo, con 6 hijos superficial + 1 nodo nuevo (papeleria-cristiana-reventa) |
| 2026-11-11 18:36 | BR | B perforar (tarde) | psicologia/materiais-psicanalise | 6 subnichos × 5 kw BR (30) + 1 + ALL en 1 + 2 controles AR/ES; ~25 páginas contadas | 2 tarjetas (NeuroKit Clínico + Terapia Cognitiva Online, Nova Era Recursos Terapêuticos), 5 señales | profundo, con 6 hijos superficial |
| 2026-11-11 06:45 | ES | B perforar (mañana) | educacion-profesional/fichas-visuales-estudio | 6 subnichos × 5 kw (30) + ALL en 1; ~13 páginas contadas (por país en Aprendia y Derecho en Mapas) | 2 tarjetas (Aprendia : Guias profesionales, Derecho en Mapas), 5 señales | profundo, con 6 hijos superficial |
| 2026-11-11 06:40 | EN | C operadores (mañana) | — (operadores EN) | 17 operadores EN + 3 señales de ayer, 27 consultas `page_ids` + país, 7 sondeos `search_terms`, 2 controles AR/ES | 2 tarjetas (Your Consulting Management Guide, Sewing Lovers), 7 señales | 1 nodo nuevo (negocios/guias-management-pdf); bolsos con control AR/ES |
| 2026-11-11 06:35 | BR | A huella (mañana) | — (huella, BR) | 16 huellas BR (distintas de las del 09-11) + 3 controles AR/ES; ~42 páginas contadas con `page_ids` | 2 tarjetas (Templates - Pack de artes, Mestre da Madeira), 6 señales | 4 nodos nuevos BR; 4 operadores a seguir |
| 2026-11-10 18:41 | ES | B perforar (tarde) | oficios-digitales/guias-cricut | 6 subnichos × 5 kw + 4 de arranque (34) + ALL en 1; ~45 páginas contadas | 2 tarjetas (Neutral Nature, Biblioteca Creativa), 7 señales | profundo, con 6 hijos superficial |
| 2026-11-10 18:38 | EN | B perforar (tarde) | manualidades/patrones-costura-pdf | 7 subnichos, 25 kw US/GB (sin ceros, sin control AR/ES); ~20 páginas contadas | 2 tarjetas (Knitting Art Studio, The Crochet Nook), 6 señales | profundo, con 7 hijos superficial |
| 2026-11-10 18:36 | BR | B perforar (tarde) | concursos/material-estudo | 6 subnichos × 5 kw BR + 1 huella + 7 controles ES/AR; ~35 páginas contadas | 2 tarjetas (Mapa Concursos, 123passei), 7 señales | profundo, con 6 hijos superficial |
| 2026-11-10 06:44 | ES | A huella (mañana) | — (huella, hispano) | 13 huellas ES + ~45 páginas contadas (por país en las de 50) | 2 tarjetas (Planner Hoy Solo 3, Biblioteca maestra arcilla), 6 señales | 4 nodos nuevos; 3 operadores a seguir |
| 2026-11-10 06:42 | EN | B perforar (mañana) | pareja/reconquista-matrimonio | 5 subnichos, 22 kw US/GB + ALL en 9 + control AR/ES; 15 páginas contadas | 1 tarjeta (Heroic Husband + Linda Harrison), 5 señales | profundo, con 5 hijos superficial |
| 2026-11-10 06:40 | BR | C operadores (mañana) | — (operadores BR) | 7 operadores BR + 3 señales de ayer, 28 consultas con `page_ids` (+ `search_terms` para destapar cohortes) | 0 tarjetas, 8 señales (Atividades infantil ≥27 y Criativizando 16 pasan volumen pero WA sin oferta visible) | sin cambios de estado; 2 operadores nuevos a seguir |
| 2026-11-09 18:42 | ES | B perforar (tarde) | manualidades/patrones-pdf | 8 subnichos, 37 kw nativas + ALL en 2 ceros flojos, ~30 páginas contadas | 2 tarjetas (Crea y Emprende, Cursos Online), 6 señales | profundo, con 8 hijos superficial |
| 2026-11-09 18:37 | EN | B perforar (tarde) | planners-imprimibles-2027 | 5 subnichos × 7 kw US/GB + 1 control AR/ES; 15 páginas contadas | 2 tarjetas (This & That Planners, Planner Lovers), 4 señales | profundo, con 5 hijos superficiales |
| 2026-11-09 18:35 | BR | B perforar (tarde) | educacao/atividades-prontas-professores | 6 subnichos × 5 kw BR + 2 controles AR/ES/MX; ~35 páginas contadas | 1 tarjeta (Prof. Mariana Oliveira), 5 señales | profundo, con 6 hijos superficial |
| 2026-11-09 06:40 | ES | C operadores (no hay operadores ES ni agenda → testers hispanos anotados por EN + complemento A huella ES) | — (operadores + huella, hispano) | 3 operadores EN-hispanos + 3 kw de control + 8 huellas ES + 31 páginas contadas | 1 tarjeta (Sector Digital), 7 señales | 3 nodos nuevos; 4 operadores ES a seguir |
| 2026-11-09 | BR | A huella (lunes toca B, pero no hay nodo BR en la cola → A) | — (huella, BR) | 16 huellas BR + 2 controles en español; ~45 páginas contadas con `page_ids` | 2 tarjetas (Creartool, Daily Routine Club), 5 señales | 6 nodos nuevos BR |
| 2026-11-09 06:30 | EN | A huella (corrida programada de la mañana) | — (huella, US GB, huellas distintas de las de 00:05) | 13 huellas US + 13 GB (26), ~50 páginas contadas | 0 tarjetas, 5 señales (Linda Harrison 44/≥50 con gate abierto) | 5 nodos nuevos virgen |
| 2026-11-09 | EN | B perforar (2ª corrida, prueba manual) | ciberseguridad/plantillas-nist | 6 subnichos × 4 kw × US/GB (ALL en los ceros) + 2 controles AR/ES | 1 tarjeta (Dragon Fire Method), 3 señales | profundo, con 6 hijos |
| 2026-11-09 | EN | A huella | — (huella, US GB) | 13 huellas × US/GB + 2 controles AR/ES (24 keywords) | 2 tarjetas (Honey Home, Practical Accounting Kit), 4 señales | 5 nodos nuevos |
| | | | | | | |
