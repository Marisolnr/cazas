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
| manualidades/patrones-costura-pdf/bolsos | manualidades/patrones-costura-pdf | EN | superficial | 3 kw · 2026-11-10 | Sewing Lovers 20/50 US ($9,99); Motif Studio sin cohorte; `tote bag pattern` = físicos |
| manualidades/patrones-costura-pdf/fieltro-peluches | manualidades/patrones-costura-pdf | EN | superficial | 3 kw · 2026-11-10 | Mariana Williams (fieltro católico) todo < 7 d: re-medir 2026-11-17; Sweet Pea, SewBloom chicos |
| manualidades/patrones-costura-pdf/quilting | manualidades/patrones-costura-pdf | EN | superficial | 2 kw · 2026-11-10 | Wildbloom Quilts 5/10 ($27/$47, RON); el resto, kits físicos |
| religion/biblia-visual | religion | EN | virgen | 1 kw US/GB · 2026-11-09 | apareció por huella el 2026-11-09 (Revelation Unsealed 3D 8/30, 13 fechas, ads de hasta 34 d) |
| hogar/preparacion-emergencias | hogar | EN | virgen | 1 kw GB · 2026-11-09 | apareció por huella el 2026-11-09 (Fallback Book GB 12/18, ¿personalizado o físico?; Lights Out) |
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
| psicologia/materiais-psicanalise | psicologia | BR | virgen | — | apareció por huella el 2026-11-09 (Estante da Psicologia 11/19) |
| mapas-visuais-r10 | educacao | BR | virgen | — | apareció por huella el 2026-11-09: red «Clube dos X» a R$10 (Mapas 8/25, Cálculo, Devops), Leg Educação, Universo Laboratorial, Bovino Ilustrado 6/16 |
| design-digital/packs-stories-templates | design-digital | BR | superficial | 2 huellas BR (`templates canva`, `pack de artes`) + 1 control AR/ES · 2026-11-11 | apareció por huella el 2026-11-11 (Templates - Pack de artes: figurinhas 27/27, 217-293 d, tarjeta); perforar por formato (stickers / feeds / mini site / sublimación) y avatar (emprendedora / profesión) |
| oficios/moldes-marcenaria-pdf | oficios | BR | superficial | 2 huellas BR (`moldes pdf`, `download imediato`) + 2 controles AR/ES · 2026-11-11 | apareció por huella el 2026-11-11 (Mestre da Madeira 11/50, tarjeta); en AR/ES ya hay testers (Carpinteria que Vende, Tablero Studio); perforar por avatar (juguetes / palet / muebles) |
| receitas/ebooks-fit | receitas | BR | virgen | 1 huella BR (`receitas fit pdf`) · 2026-11-11 | apareció por huella el 2026-11-11: FitFlow 17/17 y Comida Saudável 15/15 con ads de 61-119 d pero ninguno nuevo en 30 d (posible zombi) |
| costura/moldes-pdf-br | costura | BR | virgen | 1 huella BR (`moldes pdf`) · 2026-11-11 | apareció por huella el 2026-11-11: Ponto Certo App 9/22 (avental japonês, 111 d); el resto son olas de hoy (Pilar Digital, Keila moldes, Texto de Dentro) |
| salud-mental/sistemas-de-sesiones | salud-mental | ES | superficial | 1 operador contado (Sector Digital 25/≥50) + 8 huellas ES · 2026-11-09 | apareció por huella el 2026-11-09 (`kit digital`); perforar por profesión (psicología deportiva / adicciones / nutrición / entrenadores) |
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
| productividad/planner-vaciar-cabeza | productividad | ES | superficial | 1 huella ES (`planner imprimible`) + conteo por país ES/MX/AR · 2026-11-10 | apareció por huella el 2026-11-10 (Planner Hoy Solo 3 21/35 ES, tarjeta; AR 0); perforar por formato (PDF / digital) y avatar (madres / estudiantes / emprendedores) |
| manualidades/plantillas-ceramica | manualidades | ES | superficial | 1 huella ES (`plantillas imprimibles`) + conteo AR/ES · 2026-11-10 | apareció por huella el 2026-11-10 (Biblioteca maestra arcilla ≥16/≥50 AR, tarjeta; ES 0; clon Planos de Barro de hoy) |
| educacion-profesional/fichas-visuales-estudio | educacion-profesional | ES | profundo | 6 subnichos × 5 kw (30) + ALL en 1 + ~13 páginas contadas · 2026-11-11 | perforado el 2026-11-11: 2 tarjetas (Aprendia : Guias profesionales, Derecho en Mapas); modo C sobre los hijos |
| educacion-profesional/fichas-visuales-estudio/salud | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw · 2026-11-11 | red Aprendia con cohorte 0; IA Programas 16/22 (producto sin ver); testers BRL |
| educacion-profesional/fichas-visuales-estudio/oficios-tecnicos | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw · 2026-11-11 | casi solo la red Aprendia; Aprendia : Guias profesionales MX 38/50 (tarjeta) |
| educacion-profesional/fichas-visuales-estudio/mapas-esquemas | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw + ALL mapas conceptuales · 2026-11-11 | Derecho en Mapas CO 10/34 (tarjeta); mapas conceptuales imprimibles = cementerio |
| educacion-profesional/fichas-visuales-estudio/oposiciones-examenes | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw · 2026-11-11 | academias; Mapasyresumenes 4/50 (re-medir 2026-11-18); El Mapa del MIR 9/0 |
| educacion-profesional/fichas-visuales-estudio/derecho-contabilidad | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw · 2026-11-11 | Dra Mariana Legal 8/23; Studio Facile ES 43 nuevos (re-medir 2026-11-18); Virtual Derecho desde 9,90 € |
| educacion-profesional/fichas-visuales-estudio/formato-aprendia | educacion-profesional/fichas-visuales-estudio | ES | superficial | 5 kw · 2026-11-11 | ruido de 5.000+ en `guía visual PDF` y `fichas de estudio`; Bookbay Digital 9/0 |
| docentes/dinamicas-grupales | docentes | ES | superficial | Talleres Listos contado por país AR/ES/MX · 2026-11-10 | Talleres Listos pasa la vara (AR 20, ES 24, MX 21) pero ya corre en AR y ES; perforar por público (docentes / catequesis / RR. HH.) |

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
| un whale migra de página sin apagar el negocio | contar solo la página madre lo da por muerto | contar también las páginas hermanas de su ficha |
| barrido por keyword en EN (`printable`, `instant download`) | la API los ordena del más nuevo: casi todo tiene < 2 d y la cohorte no se ve | usar la huella para leer nombres de página y contar cada una con `page_ids` + `countries` |
| `protocol` / `blueprint` (EN) | suplementos, advertoriales con persona, granjas de juegos y dramas | entregable + tema |
| `printable` solo (GB) | quiz-funnels de dieta (Eat Smart, High.diet) | `printable planner`, `printable pages` |
| `Security+` (EN) | el «+» se pierde y trae «security guide» (guardias, ficción) | `CompTIA Security` |
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

## Operadores a seguir (modo C)

Fábricas multi-SKU y whales que muestran el próximo producto antes de que aparezca por keyword. Se
enumeran con `page_ids` + `countries`, siempre con el país. Cadencia: quincenal salvo que diga otra cosa.

| Operador | page_id | País | Por qué se lo sigue |
|---|---|---|---|
| Visual Guide Lab | 1467890346400480 | US | libros ilustrados para exámenes, mucho volumen sin cohorte (2026-11-09); mismo molde que In pictures books 1354208894450767, Illustrated Manuals 1459350803924436 y Avenlo 1434008009790850 (en español) |
| Honey Home | 1334135786448993 | US · GB | tarjeta del 2026-11-09: ver si la cohorte sigue creciendo |
| Dragon Fire Method | 163589696835008 | GB · US | whale de plantillas NIST/infosec, tarjeta del 2026-11-09 |
| Your Consulting Management Guide | 1097413493462052 | US · GB | 47/50 en cohorte (2026-11-09), no se sabe qué vende |
| Linda Harrison | 778821148649074 | US · GB | 44/≥50 en cohorte (2026-11-09); 43/55 US y 17/20 GB en la tarjeta EN del 2026-11-10 (junto a Heroic Husband); formato y cara sin verificar |
| Creartool | 325627053956826 | BR | tarjeta del 2026-11-09 (manual de estructuras narrativas, 23/48); testea versión «30 estruturas» |
| Daily Routine Club | 671948206009244 | BR | tarjeta del 2026-11-09 (planner de rutina/estudios, 14/22) |
| Prof. Mariana Oliveira | 1080842931788422 | BR | tarjeta del 2026-11-09 tarde (Atividades Investigativas, 19/48); persona de fachada (Dra.→Prof.), paga en USD |
| Criativizando e Educando | 430307330169512 | BR | 14/32 con ad de 84 d, WhatsApp sin oferta visible por API; 16/32 el 2026-11-10: verificar en la PC |
| Loja das Profs / Prof Jaque Mendes | 1002633749601439 · 105209655117919 | BR | mismo operador, 187 activos est., cohorte detrás del tope |
| Pequenos Leitores | 1196621566868514 | BR | 12/35 el 2026-11-09 con hueco de 2 meses; el 2026-11-10 se apagó (4/4, ahora «Leitura Descomplicada», sin ads en 70 d): bajar a mensual |
| Atividades infantil | 265589206630616 | BR | ≥27/233 el 2026-11-10 (destapada con `search_terms`), ad de 42 d; cierra por mensajes sin oferta visible: verificar en la PC (y que no sea neurokids) |
| Lacuna Concursos | 1173569735845788 | BR | material para concursos «Baixe Agora», ≥4/89 el 2026-11-10 (ayer ≥15): ¿pago o lead magnet? |
| Sector Digital | 1122535934265327 | AR · ES · MX | tarjeta ES del 2026-11-09 (sistema de sesiones para psicólogos deportivos, 25/≥50); abrió línea «adicciones» el 08-11 |
| Digital Academy | 858372700683858 | MX · AR · BO | multipack con WA, 15/41 y ads de 88 d; ver qué SKU se queda con la cohorte |
| Talleres Listos | 1423115024221032 | hispano | 304 est. con un solo título; contado por país el 2026-11-10: AR 20, ES 24, MX 21 en cohorte (pasa la vara, ya en los dos destinos) |
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
| Sewing Lovers | 1341379315722832 | US · GB | patrones PDF de bolsos a $9,99, 20/50 US (2026-11-10) |
| Stitch Well / Elsie Brooks | 684792994717005 · 269275822943681 | US · GB | 409 y 269 est. con cohorte oculta (mismos creativos); re-medir 2026-11-17 |
| Templates - Pack de artes | 123045347437517 | BR | tarjeta BR del 2026-11-11 (figurinhas para stories R$3,99, 27/27, 217-293 d); catálogo de packs a R$1,49-3,99: ver qué SKU nuevo entra en cohorte |
| Mestre da Madeira | 1240001732528839 | BR | tarjeta BR del 2026-11-11 (+100 moldes de madeira PDF R$12,90, 11/50, escalando) |
| Clube do Devocional | 1333933036463024 | BR | ≥43/50 el 2026-11-11 con 40 ads de un solo día (7 d); WA sin oferta; re-medir 2026-11-18 |
| Arquivos que encantam | 216603914872916 | BR | 25/33 el 2026-11-11 («Apenas R$10», producto no visible): verificar en la PC |
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
| 2026-11-11 06:45 | ES | B perforar (mañana) | educacion-profesional/fichas-visuales-estudio | 6 subnichos × 5 kw (30) + ALL en 1; ~13 páginas contadas (por país en Aprendia y Derecho en Mapas) | 2 tarjetas (Aprendia : Guias profesionales, Derecho en Mapas), 5 señales | profundo, con 6 hijos superficial |
| 2026-11-11 06:40 | EN | C operadores (mañana) | — (operadores EN) | en curso | en curso | en curso |
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
