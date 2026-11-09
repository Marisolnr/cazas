# Cerebro de caza de Marisol (repo de las cazas automáticas en la nube)

Este repo lo escriben **rutinas de Claude Code en la nube**, una por mercado, dos veces por día (06:30 y 18:30 America/Argentina/Buenos_Aires),
y lo lee Marisol desde una sesión local de Claude Code parada en este clon. Reglas de las rutinas:
`cazas/nube/NUBE.md`. Método: `wiki/estrategias/automatizar-la-caza-de-winners.md`. Skill: `skills/cazar/`
(donde dice «Franco», es Marisol; donde dice «el cerebro», es este repo).

```
cazas/
├── cazas.md        # hub: winners aprobados, agenda de re-caza, territorios descartados
├── cola.md         # árbol de nichos con estado por eje × mercado: de acá sale el trabajo de cada rutina
├── bandeja.md      # tarjetas que dejan las rutinas, sin revisar hasta que Marisol decida
├── descartados.md  # lista negra: se cruza antes de cada tarjeta
└── nube/           # NUBE.md (reglas), prompts/<xx>.md (uno por mercado), log-nube.md (fallas técnicas)
RAW/cazas-auto/     # informe completo de cada corrida
skills/cazar/       # la skill, dentro del repo porque la nube no tiene ~/.claude/skills
```

**Sesiones:** EN barre US y GB como mercado fuente; BR barre Brasil como mercado fuente; ES barre MX, CO, AR, PE, CL, BO, EC, GT y ES como destino y fuente. Máximo 2 tarjetas por sesión y por corrida. Vara: cohorte de **10 o más** ads con 7+ días activos de un solo page_id.
Se busca: infoproducto digital de bajo ticket (PDF, guías, plantillas, planners, mini-cursos grabados). No se trae nunca: marca personal (la cara del dueño vende), producto físico cuyo mecanismo es el objeto, servicios, mentorías y cursos en vivo; y los nichos excluidos por el dueño: neurokids.

**Reglas de la caza:** (1) un mercado marcado «fuente» se caza para llevar la oferta a otro lado, nunca como
destino: el veredicto dice a cuál de Argentina y España (AR, ES) se lleva. (2) El **embudo WhatsApp/Messenger es válido**: test
del copy, escalera «no evaluable», precio piso, **nunca se le escribe al vendedor**. (3) **El cero no descarta**:
un nicho se declara DESCARTAR solo con 4-5 keywords nativas, un nivel de subnichos mirado y `ALL`. (4) El descarte
se registra **por eje × mercado**, no por nicho entero.

**Lo que una rutina hace:** informe en `RAW/cazas-auto/`, tarjetas en la bandeja, nodo actualizado en la cola, una
línea en `log.md`, commit + push. **Lo que nunca hace:** crear fichas de producto, escribir 🔴, dar veredicto
DESCARTAR, contactar a un vendedor, `git push --force`.

## Cómo se usa desde la sesión local (la de Marisol)

- **Siempre primero `git pull --rebase origin main`**: la bandeja que ves en el disco puede tener horas.
- **«procesá la bandeja»** (o «revisé la bandeja»): Claude hace `git pull`, muestra las tarjetas pendientes en el
  chat y Marisol decide **con palabras**, nunca editando el archivo:
  - `Idea` → Claude crea la ficha `wiki/productos/<slug>/<slug>.md` (estado Idea) desde el informe de RAW, con
    oferta, ángulo, embudo, precio, par mercado fuente → destino y los `ad_snapshot_url` más duplicados; y la suma
    a «Winners cazados» del hub.
  - `tirar` → fila en `descartados.md` con el motivo y la permanencia que diga Marisol.
  - `re-cazar <fecha>` → agenda del hub. `profundizar` → el nodo vuelve a la cola en modo B.
  Las tarjetas decididas bajan al histórico de la bandeja y se anota la tasa de aprobación (`Idea` / revisadas):
  < 20 % sube la vara, > 70 % la baja. Al terminar: commit + push, para que las rutinas de mañana lo vean.
- **«excluí el nicho X»**: Claude lo escribe en los tres lugares (fila 🔴 en la cola, fila en `descartados.md`,
  párrafo en cada `cazas/nube/prompts/<xx>.md`) y hace push.
- **«pausá las cazas» / «reactivá las cazas»**: `RemoteTrigger update` con `{"enabled": false|true}` sobre cada
  rutina (sus ids están en `cazas/nube/rutinas.md`).
- **«qué pasó con la caza de hoy»**: `RemoteTrigger list_runs` + `get_run_log` sobre la rutina, o
  `cazas/nube/log-nube.md`.
- **Escritura segura:** nunca reescribir un archivo existente entero; inserciones chicas; `log.md` solo al final.
