# Caza automática — EN · B perforar · ciberseguridad/plantillas-nist — 2026-11-09 (2ª corrida, -tarde)

Segunda corrida del día (disparo manual de prueba, 00:05 ART): según NUBE §5 la segunda corrida es **B perforar** sobre el
siguiente nodo `virgen` de EN; los tres vírgenes eran del mismo día y se tomó el primero de la cola. Barrido con 2
subagentes de solo lectura; now = 1794193530; cohorte 7+ = `ad_delivery_start_time` ≤ 1793588730.
Evidencia: API; snapshots y embudos **no verificados desde la nube**.

## Shortlist

### 1. Dragon Fire Method — megapaquetes de plantillas NIST / infosec
- page_id 163589696835008 · GB **30/≥50** (est. 58; los 8 que no devolvió la API son más viejos: piso) · US **≥9/≥50** en
  la primera pasada de 50 (est. 75; una segunda pasada con 3 llamadas juntó 73 ids distintos y contó 32 en cohorte, no
  reproducible con un solo link → se reporta el piso).
- Escalonamiento GB: 7.6 · 10.7 · 14.6 · 16.6 · 22.7 · 27.5 · 35.2 · 40.6 · 52.6 d (hasta ~60 d); 16-18 fechas de creación;
  tanda nueva «Becoming Unbreakable» (11 ads US de 0.6 d) → operador vivo y escalonado.
- Ofertas (títulos): «125 NIST templates + 500 more» (principal) · «500+ infosec templates» · «NIST 800-30 Risk Assessment
  Toolkit» · «The biggest Information Security Toolkit Bundle» · «30 incident response templates + 500 more» (GB, el grupo
  más viejo ~61 d) · «17 CISSP templates + 700 more» · «The Next-Gen Information Security Professional» (posible curso) ·
  «Buy direct from me, 30-day refund» (2 ads GB, ~41 d). Cobra en EUR. Precio no visible.
- Marca personal: nombre de página de marca, ningún nombre propio en los títulos; único indicio el «Buy direct from me».
  **Falta ver si hay cara en los creativos** (snapshot 403 desde la nube).
- Snapshots: https://www.facebook.com/ads/library/?id=1150905517887550 · https://www.facebook.com/ads/library/?id=1108803878273236 · https://www.facebook.com/ads/library/?id=1432024858543214 · https://www.facebook.com/ads/library/?id=2491747371339364
- Ads Library: https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=GB&view_all_page_id=163589696835008&search_type=page&media_type=all · https://www.facebook.com/ads/library/?active_status=active&ad_type=all&country=US&view_all_page_id=163589696835008&search_type=page&media_type=all
- Score 2/4: ① longevidad ✓ (cohorte a 52-60 d) · ② volumen ✗ (30 < 50) · ③ duplicación no medida dentro de la cohorte ✗ ·
  ④ hueco ✓ (AR+ES con `ALL`: «plantillas ciberseguridad» 82 / «plantillas ISO 27001» 65, casi todo ruido —Platzi, Lexroom,
  Digitaldocu—; el único par es Quality4U 1227252717141294 «Tu Centro de Mando de Ciberseguridad en Excel», ads de ~5 semanas).

## Veredicto provisorio
ENTRAR → **ES** (y AR después): versión en español del megapaquete, anclada en lo que pide el mercado (ENS en España,
ISO 27001, NIST CSF), con un competidor débil (Quality4U). Condición: confirmar en la PC que los creativos no dependen de
una cara y ver precio y landing.

## Cobertura (subnichos)
| Subnicho | Keywords (US y GB) | ALL en los ceros | Qué trajo | Queda en |
|---|---|---|---|---|
| A NIST | NIST templates · NIST 800-53 · NIST CSF · risk assessment template | — | casi solo Dragon Fire; SaaS (Complyance, EasyAudit, Netwrix); Your Consulting Management Guide | profundo (un whale) |
| B ISO 27001 | ISO 27001 templates · ISO 27001 toolkit · ISMS templates · ISO 27001 policies | ISMS templates: US 7 / GB 10 → cementerio (ISO 27001 PRO LLC 718298288032927, Stratovik OÜ 606431662546746 «ISO 27001 Full Documents Kit $99») | Vanta, Scytale, Aegora (lead magnet SaaS) | superficial: cementerio de vendedores de kits |
| C SOC 2 / políticas | SOC 2 templates · security policy templates · information security policies · cybersecurity policy template | — | ruido (Heidi, DocSpring), Dragon Fire, ITeam, LawMother | superficial |
| D incident response / continuidad | incident response template · incident response playbook · disaster recovery template · business continuity template | DR US 35 / GB 27 y BC GB 92: solo ruido → hueco | Dragon Fire, Jess Cotter (marca personal), Wiz/Sardine (SaaS) | superficial |
| E HIPAA | HIPAA templates · HIPAA policies · HIPAA compliance kit · HIPAA checklist | compliance kit GB: 6 inactivos (Bulletproof Practice Kit 1368727699658980) | SaaS y MSP; Gamma Compliance Solutions 210056055730299 (6/6, paquetes OSHA/HIPAA para consultorios, ads de 17 a 823 d) | superficial |
| F pyme / estudio de examen | cybersecurity checklist · CISSP study guide · Security+ study guide · CMMC templates | CISSP: US 8 / GB 29 → cementerio (Dragon Fire, Netwrix gratis) | LawMother (kit legal, fuera de nicho), Destination Certification (4/4, curso caro), Diego Ramírez (marca personal, 0/3) | superficial |
| control destino | plantillas ISO 27001 · plantillas ciberseguridad (AR+ES, ALL) | — | Quality4U (único par), ruido | — |

Trampas nuevas: `Security+` pierde el «+» → trae «security guide» (guardias, ficción); `SOC 2` trae ruido de SaaS.

## Señales fuera de nicho que salieron en el barrido
- **Your Consulting Management Guide** 1097413493462052: US **47/50** · GB **43/46**, cohorte de 10.5 a 141 d, 16-17 fechas,
  «Instant PDF Download» en 44 de 50 títulos, sin producto nombrado ni precio. Pasaría la vara con holgura pero no se sabe
  qué vende → verificar en la PC. Posible voz en primera persona («A founder once asked me…»).
- **LawMother** 101019127920427: US 25/45, kit de planificación sucesoria «60 % OFF» + webinar; posible estudio de abogados.
- **Stress Free Psych NP**: plantillas de notas de psiquiatría, «bundle for $29», 15+ ads de ~28 d (cohorte no contada).

## Lo que no se pudo verificar
- Cara en los creativos de Dragon Fire Method, precio y landing; qué producto vende el grupo «The future depends…» (44 ads US).
- Producto de Your Consulting Management Guide.
- Cohorte US de Dragon Fire más allá de los 50 más nuevos.
