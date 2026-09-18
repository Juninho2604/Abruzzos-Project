---
titulo: Diagnóstico del CDP — visita del 18 de septiembre de 2026
area: Operaciones
responsable: Omar
estado: borrador
version: 0.1
actualizado: 2026-09-18
---

# Diagnóstico del CDP

> **Confirmar la unidad.** Este documento se creó para CDP Caracas. Si la visita fue al CDP
> Oriente (Puerto La Cruz), se renombra el archivo y se ajusta el encabezado.

**Fecha de visita:** 2026-09-18 (viernes)
**Visita:** Omar
**Atiende:** _(Jefe de CDP — nombre)_
**Motivo:** inventario de apertura + diagnóstico de optimización de la producción, a solicitud
de Cristian.

**Nota sobre el día:** viernes es uno de los dos días de mayor demanda de la red según el
[Plan Maestro](../plan-maestro-de-operaciones.md). Lo observado hoy corresponde a un día de
pico, no a un día promedio. Conviene repetir una visita en día bajo (lunes o martes) para
tener las dos fotos.

Levantado con la [guía de levantamiento](guia-levantamiento-cdp.md).

---

## 1. Resumen

<!-- Cinco líneas, al final de la visita. El estado general y lo más urgente. Se escribe de
     último pero se lee de primero. -->

---

## 2. El inventario de apertura

### Cómo se ejecutó

Formato impreso desde **Xetux**, dos páginas, ~100 ítems. Tomado por Omar Moya.

Evidencia:
[página 1](../../recursos/imagenes/2026-09-18-planilla-inventario-apertura-cdp-p1.jpg) ·
[página 2](../../recursos/imagenes/2026-09-18-planilla-inventario-apertura-cdp-p2.jpg)

<!-- Completar: quién contó físicamente, cuánto tardó, a qué hora, si entró producción durante
     el conteo. -->

### Resultado del conteo

| Ítem | Teórico | Contado | Diferencia | % |
|---|---|---|---|---|
| | | | | |

### Evaluación del instrumento

Análisis completo en [`analisis-planilla-inventario.md`](analisis-planilla-inventario.md).
Resumen de los hallazgos:

| # | Hallazgo | Gravedad |
|---|---|---|
| H1 | El campo "CORRESPONDIENTE AL" está en blanco: el conteo no identifica fecha ni hora | Alta |
| H2 | El formato se imprimió el 27/07/26, 53 días antes del conteo | Media |
| H3 | No es planilla de críticos: trae el catálogo completo (~100 ítems, incluye consumibles) | Alta |
| H4 | Nueve bebidas distintas comparten el código `XPBOD26050001` | Alta |
| H5 | Separador decimal ambiguo en las cantidades escritas a mano | Alta |
| H6 | Doble anotación de la cantidad (al margen y en la columna) | Media |
| H7 | La celda vacía no distingue "cero" de "no contado" | Media |
| H8 | Solo hay "tomado por": sin verificador, sin hora de inicio ni cierre | Media |
| H9 | Unidad de medida inconsistente en productos de la misma familia (aceite de oliva) | Media |

**Lo que sí está bien resuelto:** la planilla **no trae el saldo teórico**. El conteo se hace a
ciegas y el contraste con Xetux viene después. Es el control más importante del formato y está
correcto.

---

## 3. El proceso de producción

### Qué produce el CDP

Identificado desde el catálogo de Xetux (ítems con prefijo `XSUB`), pendiente de confirmar en
planta:

| Producto | Estaciones del proceso | Tiempo total | Vida útil |
|---|---|---|---|
| Masa para pizza 380 g | | | |
| Harina para estirar | | | |
| Salsa para pizza passata | | | |
| Salsa para pizza tomate pelado | | | |
| Salsas mayo (ajo rostizado, bacon, champiñones, pesto) | | | |
| Salsa de piña · miel picante · romesco | | | |
| Cebolla caramelizada · mantequilla de ajo | | | |
| Procesados (albahaca, cebolla, cilantro, pimentón, piña) | | | |
| Porciones (jamón, pepperoni, tocineta, aceitunas, maíz, nutella, pecorino, salchicha) | | | |

**El bollo de masa es de 380 g.** Detalle en
[`analisis-planilla-inventario.md`](analisis-planilla-inventario.md), sección 2.

### Croquis y recorrido

<!-- Enlazar las fotos de recursos/imagenes/. Señalar si el producto cruza la planta de ida y
     vuelta, y dónde se acumula producto esperando. -->

### Capacidad

| Recurso | Capacidad | Utilización observada |
|---|---|---|
| Amasadora | | |
| Fermentación | | |
| Cava de refrigeración | | |
| Personal en turno | | |

**Cuello de botella identificado:** _(cuál es el paso que limita realmente la producción)_

---

## 4. Cómo se planifica hoy

<!-- El bloque central. Quién decide qué producir, con base en qué, con cuánta anticipación.
     Si la respuesta es "por experiencia", decirlo tal cual: no es una crítica, es el punto de
     partida. -->

| Pregunta | Situación actual |
|---|---|
| Quién decide cuánto producir | |
| Con base en qué | |
| Anticipación con que se sabe | |
| Formato del pedido de tienda | |
| Registro de plan vs. producido | |

---

## 5. Merma y quiebres

| | Dato | Fuente |
|---|---|---|
| Merma del mes anterior | | |
| ¿Está medida o estimada? | | |
| Frecuencia de quiebres en tienda | | |
| Devoluciones de tienda al CDP | | |
| Despachos de emergencia al mes | | |

> **La pregunta que ordena el diagnóstico:** ¿hay merma **y** quiebres en la misma semana? Si
> la respuesta es sí, el problema es de planificación y ahí va el esfuerzo.

---

## 6. Despacho a tiendas

| Tienda | Frecuencia | Día(s) | Tiempo de traslado | Cadena de frío |
|---|---|---|---|---|
| | | | | |

**Tensión vida útil vs. frecuencia:** _(si la masa dura N días y se despacha cada M días,
anotar aquí el conflicto)_

---

## 7. Personal

| Cargo | Plan maestro | Real hoy | Diferencia |
|---|---|---|---|
| Jefe de CDP | 1 | | |
| Cocinero Experto | 3 | | |
| Ayudante de Cocina | 10 | | |
| **Total** | **14** | | |

<!-- Cifras del plan maestro para CDP Caracas. Para CDP Oriente son 1 / 3 / 6 = 10. -->

**Observaciones de turno:** _(picos, horas muertas, escalonamiento contra la curva de
producción)_

---

## 8. Hallazgos

| # | Hallazgo | Evidencia | Impacto | Gravedad |
|---|---|---|---|---|
| 1 | | | | |

---

## 9. Oportunidades de optimización

Ordenadas por impacto sobre esfuerzo, no por facilidad.

| # | Oportunidad | Qué resuelve | Esfuerzo | Impacto estimado |
|---|---|---|---|---|
| 1 | | | | |

---

## 10. Acciones acordadas

| # | Acción | Responsable | Fecha | Estado |
|---|---|---|---|---|
| 1 | | | | Pendiente |

---

## 11. Data levantada

Checklist del bloque H de la guía.

- [ ] Planilla de inventario de apertura (formato en blanco)
- [ ] Planilla de inventario mensual (formato en blanco)
- [ ] Conteos de los últimos 2–3 meses
- [ ] Registros de despacho de las últimas 8 semanas
- [ ] Fichas técnicas
- [ ] Registro de mermas
- [ ] Fotos del recorrido y de la cava
- [ ] Contactos

Los archivos se guardan en [`recursos/`](../../recursos/) y se enlazan desde aquí.

---

## 12. Lo que dijo el Jefe de CDP

<!-- Sus respuestas a las tres preguntas de cierre: qué le quita el sueño, qué cambiaría si
     pudiera cambiar una sola cosa, qué le pide a las tiendas que no le dan. Textual, sin
     interpretar. Suele ser la parte más útil del documento. -->

---

## 13. Próxima visita

**Fecha prevista:** _(conviene un día bajo — lunes o martes — para contrastar con este viernes)_
**Qué verificar:** _()_
