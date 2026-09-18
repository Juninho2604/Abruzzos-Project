# Hallazgos

Registro de las desviaciones detectadas en auditoría y su seguimiento hasta el cierre.

## Qué va aquí

Un archivo por informe de auditoría:

```
AAAA-MM-DD-auditoria-<tema>-<tienda>.md
```

Ejemplos:

```
2026-10-05-auditoria-inventario-guatire.md
2026-10-18-auditoria-compras-centro-de-produccion.md
2026-10-22-arqueo-sorpresivo-charallave.md
```

Usa [`99-plantillas/plantilla-informe-auditoria.md`](../../99-plantillas/plantilla-informe-auditoria.md).

## Cómo se clasifica un hallazgo

| Nivel | Criterio | Plazo de corrección |
|---|---|---|
| **Crítico** | Pérdida de dinero en curso, riesgo sanitario o legal. | Inmediato |
| **Alto** | Control ausente o incumplido que expone al negocio. | 7 días |
| **Medio** | Proceso que se cumple parcialmente o sin registro. | 30 días |
| **Bajo** | Oportunidad de mejora, sin impacto inmediato. | Próxima revisión |

## Un hallazgo bien escrito tiene cinco partes

1. **Qué se encontró** — el hecho, concreto y verificable.
2. **Evidencia** — conteo, documento, foto, registro del sistema.
3. **Contra qué se compara** — el procedimiento o el estándar que se incumple.
4. **Impacto** — qué le cuesta al negocio, en dinero o en riesgo.
5. **Corrección acordada** — qué se hace, quién responde, para cuándo.

Sin el punto 5, no es un hallazgo: es una queja.

## Seguimiento

Un hallazgo se cierra cuando se **verifica** que la corrección se aplicó y sostuvo — no
cuando alguien avisa que ya lo arregló. Los hallazgos abiertos se revisan en cada
auditoría siguiente, y uno que reaparece dos veces deja de ser un problema de ejecución y
pasa a ser un problema de diseño del proceso.
