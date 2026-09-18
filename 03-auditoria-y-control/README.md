# 03 — Auditoría y Control

**Responsable: Adalberto**

Control interno del negocio: que el inventario cuadre, que las compras se hagan bien y que
la caja esté controlada. Es la contraparte de Operaciones: mientras allá se mira que la
operación se ejecute, aquí se verifica que los números detrás de esa operación cierren.

| Carpeta | Qué va aquí |
|---|---|
| [`inventarios/`](inventarios/) | Procedimientos de conteo, control de existencias, análisis de consumo teórico vs. real. |
| [`compras/`](compras/) | Proceso de compras, proveedores, órdenes, recepción y control de precios. |
| [`caja/`](caja/) | Arqueos, control de efectivo, cierres de caja, conciliación de ventas. |
| [`hallazgos/`](hallazgos/) | Hallazgos de auditoría con su evidencia y su seguimiento. |

---

## Foco del mes

**Compras.** Es el área en profundización actual. Ver [`compras/`](compras/).

## Por qué esto pesa en una cadena en expansión

Mientras hay pocas tiendas, el control se sostiene con presencia: el dueño ve, pregunta y
corrige. Cuando se multiplican las tiendas y las ciudades, esa presencia deja de alcanzar,
y lo que sostiene el control son los procedimientos y los registros.

Las fugas de margen en este negocio casi nunca aparecen como un evento grande: aparecen
como una diferencia pequeña que se repite todos los días en cada tienda. Por eso el control
tiene que ser periódico y medido, no por sospecha.

## Cómo se trabaja una auditoría

1. **Se define el alcance**: qué se audita, de qué período, en qué tiendas.
2. **Se levanta la evidencia**: conteos, documentos, registros, observación directa.
3. **Se compara** contra el procedimiento vigente y contra lo que dicen los números.
4. **Se documenta el hallazgo**: qué se encontró, con qué evidencia, qué impacto tiene.
5. **Se acuerda la corrección** con un responsable y una fecha.
6. **Se verifica** en la auditoría siguiente.

Usa [`99-plantillas/plantilla-informe-auditoria.md`](../99-plantillas/plantilla-informe-auditoria.md).

## Criterio

Un hallazgo se sostiene con **evidencia**, no con impresión. Y se redacta apuntando al
proceso que falló, no a la persona: si un procedimiento permite que algo salga mal, el
problema es el procedimiento, y cambiar a la persona no lo arregla.
