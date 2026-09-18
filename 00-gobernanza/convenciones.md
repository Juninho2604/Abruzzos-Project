---
titulo: Convenciones de nombres y formato
area: Gobernanza
responsable: Compartido (Omar / Adalberto)
estado: vigente
version: 1.0
actualizado: 2026-09-18
---

# Convenciones

## Nombres de archivo

Regla general: **minúsculas, sin acentos, sin espacios, palabras separadas por guion.**

```
manual-apertura-de-tienda.md
procedimiento-conteo-de-inventario.md
checklist-supervision-de-tienda.md
```

Motivo: los espacios y los acentos rompen enlaces y dan problemas entre Windows, Mac y
Linux. El título con acentos va adentro del documento, no en el nombre del archivo.

### Documentos con fecha

Los documentos que corresponden a un momento puntual (informes, actas, reportes,
auditorías) llevan la fecha al principio, en formato `AAAA-MM-DD`:

```
2026-09-18-acta-reunion-arranque.md
2026-09-30-reporte-mensual-operaciones.md
2026-10-05-auditoria-inventario-guatire.md
```

Así se ordenan solos cronológicamente.

### Documentos por tienda

Cuando el documento aplica a una tienda específica, la tienda va al final:

```
2026-10-12-visita-de-tienda-guarenas.md
ficha-de-tienda-charallave.md
```

### Propuestas

```
2026-09-20-propuesta-reestructuracion-centro-de-produccion.md
```

---

## Encabezado de cada documento

Todo documento `.md` arranca con este bloque:

```yaml
---
titulo: Manual de apertura de tienda
area: Operaciones
responsable: Omar
estado: borrador
version: 0.1
actualizado: 2026-09-18
---
```

| Campo | Qué poner |
|---|---|
| `titulo` | El nombre completo y legible, con acentos. |
| `area` | Gobernanza, Abruzzos, Operaciones, Auditoría y Control, Expansión, Propuestas, Reportes. |
| `responsable` | Quién manda sobre este documento. |
| `estado` | `borrador`, `en revisión`, `aprobado`, `vigente` o `archivado`. |
| `version` | `0.x` mientras sea borrador. `1.0` cuando quede vigente. |
| `actualizado` | Fecha del último cambio de fondo, `AAAA-MM-DD`. |

## Versiones

- `0.1`, `0.2`, `0.3`... mientras el documento es borrador.
- `1.0` cuando queda aprobado y vigente por primera vez.
- `1.1`, `1.2`... ajustes menores sobre un documento vigente.
- `2.0` cuando el documento se rehace o cambia de fondo.

## Mensajes de commit

En español, en presente, diciendo qué se hizo:

```
Agrega manual de apertura de tienda
Corrige horarios en el checklist de cierre
Actualiza procedimiento de compras a versión vigente
```

No hace falta más ceremonia.

## Carpetas

- Las carpetas numeradas (`00-`, `01-`, ...) mantienen el orden de lectura en la pantalla
  de GitHub. Se respetan.
- Carpeta nueva → lleva su propio `README.md` explicando qué va adentro.
