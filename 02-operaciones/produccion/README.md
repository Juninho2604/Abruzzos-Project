# Producción

Producción de **tienda** y del **centro de producción**. El objetivo declarado del área:
que las producciones de ambos sean las más óptimas.

## Documentos

| Documento | Para qué sirve |
|---|---|
| [`modelo-de-planificacion-de-produccion.md`](modelo-de-planificacion-de-produccion.md) | El marco de optimización del CDP: la cadena de planificación, qué pedirle a la API de Cetux, la ruta por fases y los indicadores. |
| [`guia-levantamiento-cdp.md`](guia-levantamiento-cdp.md) | Instrumento de campo para la visita de diagnóstico a un CDP. Sirve para las dos unidades. |
| [`diagnostico-cdp-caracas.md`](diagnostico-cdp-caracas.md) | Resultado de la visita del 18/09/2026. |

## Qué va aquí

- Fichas técnicas de producto (receta, gramaje, rendimiento, tiempo, costo).
- Procedimientos de producción del centro de producción.
- Procedimientos de producción en tienda.
- Planificación de producción: cuánto producir, cuándo, con base en qué.
- Control de mermas y desperdicio.
- Estándares de tiempos de preparación y despacho.

## Qué significa "óptima"

Que se cumplan las cuatro cosas a la vez, no una a costa de otra:

| Dimensión | Qué se busca |
|---|---|
| **Cantidad** | Producir lo que se va a vender. Ni quedarse corto (venta perdida) ni pasarse (merma). |
| **Calidad** | Que el producto salga igual al estándar, siempre, en cualquier tienda. |
| **Costo** | Gramajes y rendimientos respetados. Merma controlada. |
| **Tiempo** | Que el producto esté listo cuando la operación lo necesita. |

## Frontera con auditoría

La **ficha técnica** (cuánto lleva cada producto) vive aquí, en Operaciones, porque define
cómo se produce.

El **consumo real contra el teórico** — es decir, si la tienda gastó lo que debía haber
gastado según la ficha — es control de inventario, y eso lo trabaja Adalberto en
[`03-auditoria-y-control/inventarios/`](../../03-auditoria-y-control/inventarios/).

Las dos cosas se miran juntas: una desviación de consumo casi siempre se explica por un
problema de producción (gramaje, merma, proceso) o por uno de control (mal conteo,
fuga). Por eso ninguno de los dos análisis sirve solo.
