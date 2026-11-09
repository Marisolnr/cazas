# Modos del programa de caza y salida a bandeja

Referencia operativa de `/cazar` para las corridas del programa automatizado (método en la página
`automatizar-la-caza-de-winners` del cerebro: la carpeta de trabajo donde viven `cazas/` y `RAW/`).
Las reglas de evidencia (cohorte 7+, Filtros A/B/B-WA/C, links por país) son las de `SKILL.md` y
**no cambian por el modo**.

## 0. Arranque de una sesión automática

1. Leer `CLAUDE.md` del cerebro (§7.4), `cazas/cola.md`, `cazas/descartados.md`, `cazas/bandeja.md`.
2. Comprobar `ads_library_search` (cargar con ToolSearch si está diferida) y el navegador. **Si falta
   uno, escribir en `log.md`** `## [fecha] caza-auto | <sesión> — sin conector/navegador, no corrió`
   **y salir.** No se estima nada.
3. Determinar **sesión** (`en` / `br` / `es`) y **modo** por la tabla de rotación de la cola (o el
   argumento explícito).
4. Elegir el **nodo** por el orden de la cola: `virgen` más viejo → `superficial` más viejo → `🟡`
   vencido; primero los que tienen el mercado de la sesión; nunca uno tocado por otra sesión en los
   últimos 7 días (mirar la bitácora de la cola).
5. Escribir la línea en la **bitácora de la cola ANTES de cazar** (así otra sesión no lo agarra).

## 1. Modo `huella` (A) — descubrir por formato

No parte de un nicho: parte de la **huella del formato** y deja que el nicho emerja.

- Keywords de arranque por sesión (pares de palabras, el matcher es AND por token):
  - **br:** `hotmart`, `kiwify`, `pay hotmart`, `acesso imediato`, `e-book`, `passo a passo`, `R$ 19,90`, `R$ 27`, `R$ 37`, `R$ 47`, `R$ 97`, `método`, `segredo`, `desafio`.
  - **en:** `gumroad`, `payhip`, `etsy digital`, `instant download`, `printable`, `digital download`, `$7`, `$17`, `$27`, `$37`, `blueprint`, `protocol`, `cheat sheet`.
  - **es:** `hotmart`, `acceso inmediato`, `PDF`, `guía`, `plantillas`, `te lo envío`, `por WhatsApp`, `S/`, `COP`, `MXN`, `$9`, `$17`, `método`, `paso a paso`.
- Correr 8-12 huellas × los países de la sesión. Agrupar por anunciante; para los que asoman, contar
  el arsenal con `page_ids` + `countries`.
- **Clasificar cada anunciante que pasa el filtro madre en un nicho.** Si el nicho no existe en la
  cola, agregarlo como nodo `virgen` (o `superficial` si ya se midió algo) con la nota «apareció por
  huella el <fecha>».
- Anotar en la cola qué huellas rindieron y cuáles trajeron basura (short-dramas, ecommerce).

## 2. Modo `perforar` (B) — bajar un nicho un nivel

Toma un nodo `superficial` (o `virgen` con hijos ya propuestos) y lo abre:

1. Generar **4-6 subnichos concretos** por tres ejes: **avatar** (estudiante / profesional / padre /
   dueño), **materia o problema** (la parte del nicho que duele), **formato** (plantillas, examen,
   protocolo, calculadora, tarjetas). Si la cola ya lista hijos, usar esos.
2. Por subnicho, **4-5 keywords nativas y angostas** en el idioma de la sesión. Cruzar las trampas
   de la cola antes.
3. Correr; ante un cero, **repetir con `ad_active_status: ALL`** y anotar si es hueco o cementerio.
4. Cada subnicho queda en la cola como hijo con su estado; el padre pasa a `profundo`.
5. Veredicto por subnicho, nunca por el padre entero.

## 3. Modo `operadores` (C) — seguir fábricas y agenda

1. Tomar la tabla «Operadores a seguir» de la cola y la «Agenda de re-caza» del hub `cazas/cazas.md`
   con fecha vencida o dentro de la semana.
2. Por operador: `page_ids` + `countries` por cada país donde corre; comparar contra lo anotado en su
   página del cerebro: **¿SKU nuevo? ¿país nuevo? ¿cohorte creció o se apagó?**
3. Un SKU nuevo que pasa el gate va a la bandeja como candidato; un país nuevo se anota como
   «señal de cierre de ventana» en la página del nicho **y** en la bandeja (fila de tipo `señal`).
4. Un 🟡 vencido que sigue igual se re-fecha (+4 semanas) en el hub; si cambió, va a la bandeja.

## 4. El informe: `RAW/cazas-auto/YYYY-MM-DD-<sesión>-<modo>-<nodo>.md`

```
# Caza automática — <sesión> · <modo> · <nodo> — <fecha>

## Shortlist
(formato de SKILL.md: por candidato nombre + link Ads Library por país + cohorte/total +
escalonamiento + tipo de página + embudo verificado (o ficha WA) + hook + snapshots duplicados + score)

## Veredicto provisorio
ENTRAR → <destino> / SUBNICHO / WHALE / observar. Nunca DESCARTAR.
Par fuente → destino y por qué (con ALL si el destino dio cero).

## Cobertura
| Keyword | País | ACTIVE | ALL | Qué trajo |
...
Trampas nuevas: ...
Nodos nuevos propuestos para la cola: ...

## Lo que no se pudo verificar
(links caídos, geobloqueo, API ciega, WA sin precio en el copy)
```

**Ficha WA** (reemplaza «landing + precio» cuando el embudo es WhatsApp/Messenger):
`vende:` · `promesa:` · `dolor:` · `precio dicho (piso):` · `bonos nombrados:` · `teléfono/mensaje prellenado (para agrupar):` · `no se sabe:` (contenido exacto, escalera, garantía…) · `escalera: n/e`.

## 5. La tarjeta en `cazas/bandeja.md` (lo único que Franco ve)

**Máximo dos tarjetas por sesión y por día.** Regla de Franco (2026-09-07): «uno o dos infoproductos
ganadores por día y por mercado, por qué es ganador, qué se puede hacer con él, el link de su biblioteca
de anuncios. Nada de informes largos.» El informe de §4 es evidencia; **no se le muestra**.

**Vara para tener tarjeta (Franco, 2026-09-23):** pasa el gate **y** tiene, **UN SOLO anunciante, al
menos 10 ads con 7+ días corriendo** en el país cazado. Si nadie llega, **una sola línea** («ES 09-08:
nada que pase la vara; se barrió X, Y, Z»). Nunca rellenar.

> ⛔ **Los 10 se cuentan por `page_id`.** No se suma la cohorte de varias fanpages que corren el mismo
> molde, y **la longevidad sola no reemplaza el volumen**. El 22-09 la sesión ES dio tarjeta a una red
> mexicana de cinco fanpages sumando 26 en cohorte (ninguna pasaba de 6) y apoyándose en un ad de 161
> días; **al día siguiente esa fanpage había apagado sus 13 ads de golpe**, el de 161 días incluido.
> Un ad viejo rodeado de cinco hermanos no es un ganador: es un ad que nadie apagó.

**Una tarjeta = un producto/oferta**, no un anunciante: si dos operadores corren la misma oferta, van
juntos en la tarjeta (eso es justamente la prueba). Formato, diez líneas:

```
### 🎯 <Producto> — <anunciante(s)> <país> · `nodo` · <fecha> · sesión <EN/BR/ES>
- **Qué es:** qué vende, formato, precio (piso si es WA).
- **Por qué es ganador:** cohorte 7+/activos · longevidad · fantasma · embudo verificado · cuántos operadores.
- **Qué hacer:** modelar tal cual / si es FÍSICO: cómo pasarlo a digital / si es APP: cómo pasarlo a PDF o a app propia / si es WA: arbitraje de embudo (landing a 3-4× el precio) · destino sugerido · ángulo.
- **Ads Library:** link filtrado por país (uno por anunciante).
- **Landing:** link (o «WA: ficha reconstruida» + lo que no se sabe).
- Score n/4 (· escalera n/e) · Decisión: —
```

Debajo de las tarjetas, **«Señales del día»** en una línea por ítem: lanzamientos sin cohorte, re-mediciones
con fecha, cementerios. Sin tarjeta.

- Si el candidato ya está en `descartados.md`, **no va a la bandeja**: se menciona en el informe.
- Si ya tiene página de producto en el cerebro, va como señal (qué cambió), no como tarjeta nueva.
- La sesión escribe la tarjeta **también en su mensaje final del chat**, tal cual, para que Franco la
  lea sin abrir nada.

## 6. Cierre de la sesión

1. Actualizar el nodo en `cazas/cola.md`: estado nuevo, cobertura (conteo de keywords y fecha), hijos
   nuevos, trampas nuevas, y completar la línea de la bitácora.
2. `log.md`: `## [YYYY-MM-DD] caza-auto | <sesión> <modo> <nodo> → <n> candidatos a bandeja`.
3. **No** tocar `index.md`, **no** crear páginas en `wiki/productos/`, **no** escribir 🔴 en
   `descartados.md`, **no** contactar vendedores.

> Para escribir en el cerebro: nunca `open(p,'w')` sobre un archivo existente; para agregar al log se
> abre en modo `a` (los CRLF del archivo entero se pierden si se reescribe); si es Python, script en
> archivo y `PYTHONIOENCODING=utf-8`.
