# Caza automática — ES · C operadores · — (operadores ES) — 2026-11-12

Corrida de la mañana (jueves → C operadores en la columna ES). Agenda de re-caza del hub: vacía; re-mediciones
con fecha de la tabla de operadores: ninguna vence hoy (Neutral Nature 17-11, Nutri Listo 18-11), se midieron igual.
Conteo por API con `page_ids` + un país + ACTIVE + limit 50 (3 subagentes de solo lectura; conteo manual sobre las
respuestas, sin JSON guardado). Cohorte = `ad_delivery_start_time` ≤ ahora − 7 d (ahora = 2026-11-12 09:41 UTC).
La API devuelve siempre los 50 más nuevos: con >50 estimados la cohorte es un piso y `search_terms` no la destapa.

## Shortlist

### 1. Talleres Listos — 1423115024221032 — «+150 dinámicas grupales listas para aplicar»
- ES ≥26/50 (115 est.) · MX ≥22/50 (122) · AR ≥12/50 (194; los lotes de 11-08 y 11-10 tapan a los viejos).
- Un solo SKU en los tres países. Ad más viejo 12 d (2000317804259636). 8 fechas de creación, la última 11-11 → vivo.
- Escalonamiento: lotes cada 1-3 días. Moneda USD. Página fantasma (nombre de marca, no persona).
- Embudo: no verificado desde la nube (la API no trae URL ni copy, solo título).
- Ya corre en los dos destinos (AR, ES): molde y competidor. Quedó fuera el 10-11 solo por el tope de 2 tarjetas.
- Score: ① longevidad no (12 d) · ② volumen no (<50) · ③ duplicación: título repetido 26 veces en la cohorte ES (creativo sin verificar) → 1 · ④ hueco no → **1/4**.

### 2. Consultorio Nutri Listo — 1431610173366748 — sistema de consultorio para nutricionistas
- AR 13/42 (42 est., completo). MX, ES, CO, PE, EC, CL: 0. Creció de 6/40 (11-11) a 13/42.
- Títulos: «Pago único · Acceso inmediato» (13 en cohorte, 22 en total), «4.7/5 +3400 Nutricionistas» (18, nuevos), «+1.500 materiales · 7 módulos» (2).
- Ad más viejo 8,0 d (1740005817558070): la cohorte es de ayer. 4 fechas de creación, la última hoy → vivo. Página de ~9 días.
- Moneda USD. Página fantasma. Embudo no verificado desde la nube.
- Score: ①0 ②0 ③ título repetido 13 → 1 · ④ hueco ES (no corre) → 1 → **2/4**. Riesgo: cohorte joven, puede apagarse.

## Veredicto provisorio
- Talleres Listos: SUBNICHO / modelar el molde (dinámicas para talleres, docentes, RR. HH., catequesis) en un ángulo propio; destino ES primero (ya corre, pero es donde más cohorte junta: el mercado compra).
- Consultorio Nutri Listo: ENTRAR → ES (hueco), después AR con ángulo distinto.

## Operadores contados (resto)

| Operador | page_id | País | Cohorte/activos (est.) | Lectura |
|---|---|---|---|---|
| Sector Digital | 1122535934265327 | AR / ES / MX | ≥16/50 (73) · ≥29/50 (62) · ≥15/50 (76) | estable; adicciones/«primera consulta» 0 en cohorte; ya en bandeja |
| Biblioteca Creativa | 1244762302063129 | AR/ES/MX | 7/33 · 7/36 · 7/35 | bajó; moneda BRL; SKU nuevo «Kit Calendario 027» (4, 11-11) |
| Neutral Nature | 919376131265589 | CO / ES / MX / AR | 42/42 · 0/50 (125) · 0/50 (123) · 0/8 | CO sin creativos nuevos desde 11-03; ES/MX cohorte oculta; AR país nuevo (test de 8 del 11-09) |
| Crea y Emprende | 1056023200924288 | AR / ES | 14/22 · 6/7 | tema nuevo hoy: «Verano 2027» + «cuánto cobrar tus tejidos» (6 ads) |
| Cursos Online | 512123288644096 | MX | 10/17 | sin «120 casitas»; Mostacillas 3D (5) entra hoy → 15 |
| Planner Hoy Solo 3 | 1280820831792286 | ES / MX / AR | 28/40 · 28/40 · 0 | creció (21→28); no entra a AR |
| Planos de arcilla | 1435630566293933 | AR | ≥26/50 (61) | creció (≥16→≥26); variante «248 plantillas» |
| Planos de Barro | 1463269926874211 | bloque | 0/10 | clon nuevo del 11-10 («229 plantillas», USD, tú) |
| Biblioteca Digital | 1270799516117158 | AR / ES | 25/33 · 0 | igual; ad de 64 d |
| Aprendia : Guias profesionales | 1319574141233447 | MX / AR / ES | ≥40/50 (60) · 0 · 0 | multi-SKU, 21 sin título |
| Derecho en Mapas / Mapas del Derecho | 1356269490904663 / 1404914672699239 | CO | 5/41 · 6/45 | bajó de la vara; rota ~15 ads/día; hermana con Laboral nuevo |
| Digital Academy | 858372700683858 | MX / AR / BO | 6/18 · 9/21 · 8/8 | sin SKU dominante (Revit, Mecánica) |
| Pixelpack | 116045223625247 | MX | ≥42/50 (51) | creció (≥29→≥42), ad de 103 d; megapack de reventa con diseños de terceros (anime, etc.): riesgo de derechos |
| La Biblioteca Definitiva De Tejido | 1151253608079340 | MX | 23/23 | zombi: sin ads nuevos en 53 d |
| Planner Lovers | 128972030308501 | AR / MX / ES | 19/19 · 20/20 · 0 | frenado desde 11-01, 2 fechas; no corre en ES |
| Valentina Ríos | 1280761195116636 | AR / ES | 19/19 · 0/20 | AR con cohorte completa; ES lanzado 11-05 (20 ads, entran ~13-11); reventa, nombre de persona, BRL |
| Red Aprendia 1 | 1380966491766673 | MX / PE / BO | ≥44/50 (100) · ≥26/50 (103) · 27/34 | pasa volumen pero es catálogo multi-SKU (41 sin título en MX); BO país nuevo con temas bolivianos |
| Red Aprendia 2 / 3 | 1372902832576549 / 1288181344388955 | MX / PE | 0/50 (125-161) | cohorte no medible (crean ~50/día) |
| IA Programas | 809461785581622 | MX | 11/11 | se achica (16/22→11/11), sin ads nuevos en 8 d, títulos vacíos |
| NeuroKit Clínico | 883009701566343 / 964287390098744 | ES / bloque | 12/28 (cohorte = copy francés) · 4/4 | versión en español 0 en cohorte (6 ads, 08 y 11-11); la página PT parece zombi |
| Mapasyresumenes | 234866809700963 | ES / CO | 3/34 · 0/50 (57) | SKU nuevo ES hoy: oposiciones «2027 en 150 páginas» a 12,90 € (Guardia Civil, Policía Nacional, Justicia, Abogacía) |
| Studio Facile | 1272162682644374 | ES | 0/50 (77) | creció 43→77; cohorte no destapable |
| Bienestar Digital | 1319255167927860 | bloque | 4/39 | rota, no acumula |
| Todo Digital | 916814288184704 | MX | 10/24 | multi-SKU; SKU nuevo guías de topografía a $125 MXN (6 en cohorte) |

## Cobertura
24 operadores (27 page_ids), ~45 consultas `page_ids` + país, 3 sondeos `search_terms` (Talleres Listos ×3 países:
mismo set; Aprendia 2 «guía visual»: no destapa). Sin keywords nuevas, sin ceros que pidan ALL.
Trampas nuevas: la API ordena del más nuevo al más viejo también con `search_terms`; en páginas que crean >50 ads por
país y por semana la cohorte no se puede medir desde la nube (Aprendia 2/3, Studio Facile, Neutral Nature ES/MX).
Nodos nuevos propuestos: ninguno (Talleres Listos y Nutri Listo ya caen en nodos existentes o se anotan como operadores).

## Lo que no se pudo verificar
- Embudo y precio de Talleres Listos y Consultorio Nutri Listo (sin URL ni copy en la API).
- Que el producto de Talleres Listos sea PDF/descarga y no un curso en vivo.
- Qué vende IA Programas (títulos vacíos).
