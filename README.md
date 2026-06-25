<div align="center">

# NIIN Analytics — Data Feed

**Salida pública del motor de riesgo sistémico NIIN**

*Un snapshot diario. Versionado. Firmado.*

`JSON` · `ES / EN` · `AUTO-PUBLISHED`

</div>

---

## Qué es este repositorio

Este repositorio sirve la **salida diaria** de NIIN Analytics: un único *snapshot* en formato JSON que condensa la lectura de riesgo sistémico del día. Es el feed que consume el dashboard de NIIN para presentar la señal al usuario final.

Aquí no vive el motor —los modelos, el pipeline y la metodología son propietarios y residen en infraestructura privada—. Lo que se publica es **el resultado, no el cómo**: una fotografía estructurada y auditable de la señal del día.

La premisa que gobierna NIIN se mantiene también aquí: **la señal es derivada, no inyectada.** Ningún valor de este feed se edita a mano; todo proviene del cómputo automatizado.

---

## Contenido del feed

| Archivo | Descripción |
|---|---|
| `niin_live.json` | Snapshot del día en español. |
| `niin_live_en.json` | Mismo snapshot, en inglés institucional. |

Ambos comparten estructura idéntica: solo cambia el idioma del texto narrativo. Los códigos, métricas y terminología financiera universal (`RISK_ON`, `VIX`, `drawdown`, `Sharpe`, `σ`) se mantienen sin traducir en ambas versiones.

El feed se **sobreescribe en cada sesión de mercado**: refleja siempre la lectura más reciente, no un histórico. La trazabilidad histórica se conserva en infraestructura separada.

---

## Cómo se actualiza

El feed se regenera de forma **automatizada**, sin intervención manual:

- El motor NIIN ejecuta su pipeline cada sesión hábil de mercado.
- Toda salida pasa por una auditoría anti-leakage antes de publicarse.
- Solo si la validación pasa en verde, el snapshot del día se publica aquí.
- Cada actualización queda registrada con su marca temporal.

**Sin validación en verde, no hay publicación.** Esta condición es la que sostiene la fiabilidad del feed.

---

## Uso

Este feed alimenta el dashboard oficial de NIIN Analytics. Los valores de AUM, asignación y exposición mostrados son **ilustrativos** y no constituyen asesoramiento de inversión ni una cartera gestionada real.

---

## Propiedad y confidencialidad

El contenido de este feed puede consultarse, pero los modelos y la metodología que lo generan son confidenciales. Esta declaración de autoría sirve como evidencia pero no sustituye el registro formal de la propiedad intelectual.

---

<div align="center">

**NIIN Analytics** · Feed diario · ES / EN · pipeline auditado

© 2026 Israel Fernández

</div>
