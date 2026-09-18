# 99 — Plantillas

Para no arrancar nunca de cero, y para que dos documentos del mismo tipo se vean y se lean
igual aunque los haya escrito gente distinta.

| Plantilla | Cuándo se usa |
|---|---|
| [`plantilla-propuesta.md`](plantilla-propuesta.md) | Propuesta formal al cliente. |
| [`plantilla-procedimiento.md`](plantilla-procedimiento.md) | Estándar o procedimiento operativo (SOP/POE). |
| [`plantilla-visita-de-tienda.md`](plantilla-visita-de-tienda.md) | Visita de supervisión a una tienda. |
| [`plantilla-informe-auditoria.md`](plantilla-informe-auditoria.md) | Auditoría de inventario, compras o caja. |
| [`plantilla-plan-de-accion.md`](plantilla-plan-de-accion.md) | Plan de trabajo para resolver algo concreto. |
| [`plantilla-minuta-reunion.md`](plantilla-minuta-reunion.md) | Acta de reunión con acuerdos y responsables. |
| [`plantilla-reporte.md`](plantilla-reporte.md) | Reporte periódico de avance. |
| [`plantilla-expediente-de-plaza.md`](plantilla-expediente-de-plaza.md) | Expediente de una plaza de expansión. |

## Cómo se usa

```bash
cp 99-plantillas/plantilla-procedimiento.md 02-operaciones/estandares/procedimiento-conteo-de-producto.md
```

Después se edita el encabezado (`titulo`, `responsable`, `estado`, `actualizado`) y se
borra todo lo que esté entre `<!-- -->` o marcado como ejemplo.

Las secciones que no apliquen se eliminan. Una plantilla es un punto de partida, no un
formulario obligatorio: mejor un documento corto y completo que uno largo con la mitad de
las secciones vacías.

## Si la plantilla se queda corta

Se mejora la plantilla, no solo el documento. Así el siguiente que la use ya la encuentra
arreglada.
