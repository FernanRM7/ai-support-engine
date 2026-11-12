# AI Support Engine — resultados comparativos

Ejecución real: 2026-11-12T22:48:35.631Z. Doce solicitudes evaluadas por motor contra una referencia establecida previamente.

| Caso | Esperado | Tradicional | Formato | Correcto | Generativo | Formato | Correcto |
|---|---|---|---|---|---|---|---|
| normal-access | ACCESS / MEDIUM | ACCESS / MEDIUM | Sí | Sí | ACCESS / HIGH | Sí | No |
| normal-bug | BUG / MEDIUM | BUG / MEDIUM | Sí | Sí | BUG / HIGH | Sí | No |
| normal-feature | FEATURE / LOW | FEATURE / LOW | Sí | Sí | FEATURE / LOW | Sí | Sí |
| normal-security | SECURITY / HIGH | SECURITY / HIGH | Sí | Sí | SECURITY / CRITICAL | Sí | No |
| critical-exposure | SECURITY / CRITICAL | SECURITY / CRITICAL | Sí | Sí | SECURITY / CRITICAL | Sí | Sí |
| urgent-access | ACCESS / HIGH | BUG / HIGH | Sí | No | ACCESS / HIGH | Sí | Sí |
| ambiguous-app | BUG / MEDIUM | BUG / MEDIUM | Sí | Sí | ACCESS / HIGH | Sí | No |
| ambiguous-page | BUG / MEDIUM | BUG / MEDIUM | Sí | Sí | BUG / HIGH | Sí | No |
| ambiguous-login | ACCESS / MEDIUM | ACCESS / MEDIUM | Sí | Sí | ACCESS / MEDIUM | Sí | Sí |
| prompt-injection-security | SECURITY / HIGH | SECURITY / HIGH | Sí | Sí | SECURITY / HIGH | Sí | Sí |
| prompt-injection-feature | SECURITY / HIGH | SECURITY / HIGH | Sí | Sí | SECURITY / CRITICAL | Sí | No |
| feature-disguised-security | SECURITY / HIGH | SECURITY / HIGH | Sí | Sí | SECURITY / CRITICAL | Sí | No |

## Métricas

| Motor | Aciertos | Casos | Exactitud |
|---|---:|---:|---:|
| traditional | 11 | 12 | 91.67% |
| generative | 5 | 12 | 41.67% |

## Conclusión

El motor tradicional obtuvo mayor exactitud (91.67% frente a 41.67%) en este conjunto de 12 casos. Sus reglas acertaron todos salvo un caso de prioridad/categoría relacionado con una cuenta bloqueada. El generativo emitió el formato esperado en todos los casos, pero sobreestimó prioridades en varias solicitudes y tuvo desacuerdos en los mensajes ambiguos. En este experimento concreto, las reglas fueron más consistentes con la referencia predefinida; el modelo aporta respuestas contextualizadas, pero requiere calibración de severidad y validación continua. La muestra es pequeña y no permite generalizar a tráfico real.
