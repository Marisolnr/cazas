# Rutinas de caza en la nube

| Sesión | Id de la rutina | Cron | Hora local (Buenos Aires) | UTC | Modelo |
|---|---|---|---|---|---|
| EN | `trig_01HCg7HC9szLeKFJLfk46uVW` | `CRON_TZ=America/Argentina/Buenos_Aires 30 6,18 * * *` | 06:30 y 18:30 | 09:30 y 21:30 | claude-opus-5-5 |
| BR | `trig_012jazt2hcbESQrFJNwegmx9` | `CRON_TZ=America/Argentina/Buenos_Aires 35 6,18 * * *` | 06:35 y 18:35 | 09:35 y 21:35 | claude-opus-5-5 |
| ES | `trig_01EnskdvotwoCSw8Pb1MuB1S` | `CRON_TZ=America/Argentina/Buenos_Aires 40 6,18 * * *` | 06:40 y 18:40 | 09:40 y 21:40 | claude-opus-5-5 |
| EU | `trig_01K4RuQZdX6Aj1DD3G9pWbAw` | `CRON_TZ=America/Argentina/Buenos_Aires 45 6,18 * * *` | 06:45 y 18:45 | 09:45 y 21:45 | claude-opus-5-5 · **PAUSADA 2026-11-17**: Europa es destino, no fuente |

Creadas el 2026-11-08 (recreadas el mismo día para adjuntar el conector de Meta). Corren en modo automático (sin pedir aprobaciones). Pausar / reactivar: actualizar `enabled` en cada id.
