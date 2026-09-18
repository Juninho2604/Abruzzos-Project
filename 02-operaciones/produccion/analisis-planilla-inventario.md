---
titulo: Análisis de la planilla de inventario del CDP
area: Operaciones
responsable: Omar
estado: borrador
version: 0.1
actualizado: 2026-09-18
---

# Análisis de la planilla de inventario del CDP

Revisión del formato de conteo que se está usando en el CDP, levantada durante el inventario
de apertura del 18 de septiembre de 2026.

**Evidencia:**
[página 1](../../recursos/imagenes/2026-09-18-planilla-inventario-apertura-cdp-p1.jpg) ·
[página 2](../../recursos/imagenes/2026-09-18-planilla-inventario-apertura-cdp-p2.jpg)

**Origen del formato:** reporte impreso desde **Xetux** (`xetux.com`) por Adalberto el
**27/07/2026 a las 2:01 p.m.** Dos páginas, alrededor de 100 ítems.

> Toda lectura de códigos y cantidades viene de una foto de la planilla. Antes de accionar
> sobre cualquiera de estos hallazgos, confirmarlos contra Xetux.

---

## 1. Hallazgos del instrumento

### H1 — La planilla no identifica el período. **Gravedad: alta**

El campo **"CORRESPONDIENTE AL:"** está en blanco. La planilla registra quién tomó el conteo
(Omar Moya) pero no a qué fecha ni a qué momento corresponde.

Un conteo sin fecha y hora no se puede conciliar contra el saldo del sistema, porque el saldo
de Xetux se mueve durante el día. Si el conteo se hizo a las 8:00 a.m. y se concilia contra el
saldo de las 6:00 p.m., toda la diferencia que aparezca es artificial.

**Corrección:** el campo se llena siempre, con **fecha y hora**, antes de empezar a contar.

### H2 — El formato tiene 53 días de antigüedad. **Gravedad: media**

Se imprimió el 27/07/2026 y se está usando el 18/09/2026. Cualquier producto dado de alta en
Xetux en ese lapso no aparece en la planilla y, por lo tanto, no se cuenta — y nadie se entera,
porque el que cuenta solo ve lo que está impreso.

**Corrección:** la planilla se reimprime desde Xetux el día del conteo.

### H3 — No es una planilla de productos críticos: es el catálogo completo. **Gravedad: alta**

El inventario de apertura debería contar solo productos críticos; el conteo completo es el
mensual. Pero este formato trae los ~100 ítems del catálogo, incluidos consumibles que no son
críticos por ningún criterio: papel higiénico, esponjas de alambre, coletos, gorros, guantes,
servilletas, vasos desechables, bolsas de basura.

Consecuencias de las dos posibles explicaciones:

- **Si se cuenta todo cada apertura:** el conteo se vuelve largo, cansa, y la calidad del
  conteo cae en los ítems del final — que en esta planilla son justamente la masa, las salsas y
  los quesos. Se cuenta con cuidado el aceite de oliva y con prisa el producto que de verdad
  importa.
- **Si solo se cuentan algunos:** no hay forma de distinguir **"no aplica a este conteo"** de
  **"se saltó"**, porque ambos casos se ven igual: la celda vacía.

**Corrección:** definir la lista de críticos con criterio explícito (valor, rotación, riesgo de
desviación) y sacar de Xetux un formato específico de apertura con solo esos ítems.

### H4 — Nueve productos distintos comparten un mismo código. **Gravedad: alta**

El código **`XPBOD26050001`** aparece asignado a nueve productos diferentes:

| Página | Producto |
|---|---|
| 1 | AGUA NEVADA 600 ML |
| 1 | AGUA SPARKLING |
| 1 | BOTELLON DE AGUA |
| 1 | LIPTON DE DURAZNO |
| 1 | LIPTON DE LIMON |
| 2 | REFRESCO 1 LT |
| 2 | REFRESCO 1.5 LT |
| 2 | REFRESCO 2 LT |
| 2 | REFRESCO DE LATA 350 ML |

Además, **AGUA NEVADA 355 ML** lleva `XPRO2605000125` — un prefijo distinto (`XPRO` en vez de
`XPBOD`) para un producto de la misma familia que AGUA NEVADA 600 ML.

Si en Xetux toda la línea de bebidas está bajo un solo SKU genérico, entonces:

- No hay control de inventario por bebida. No se puede saber si lo que falta son refrescos de
  2 litros o botellones.
- **No se va a poder sacar venta por SKU de bebidas**, que es exactamente el dato que hace
  falta para el modelo de planificación y para la solicitud de API a Xetux.

**Corrección:** verificar en Xetux si es un problema del maestro de productos o del reporte. Si
es del maestro, hay que abrir un SKU por presentación antes de pedir la API — si no, la API va
a entregar bebidas agregadas y el problema queda igual, pero automatizado.

### H5 — Ambigüedad en el separador decimal. **Gravedad: alta**

Varias cantidades anotadas a mano no son interpretables sin preguntar:

| Producto | Anotado | ¿Qué significa? |
|---|---|---|
| AZÚCAR KG | `4.730` | ¿4,73 kg o 4.730 kg? |
| BOLSAS 3KG PARA MASAS UND | `23.700` | ¿23,7 o 23.700 unidades? |
| BOLSAS PARA PORCIONAR UND | `26.100` | ¿26,1 o 26.100 unidades? |
| BOTELLÓN DE AGUA | `8850` | ¿8.850 botellones? Poco plausible |
| BOLSAS DE ASAS 5KG UND | `17400` o `7400` | Dígito inicial dudoso |

En Venezuela el punto es separador de miles y la coma es decimal, pero en la planilla se están
usando indistintamente y en ítems de unidad entera (bolsas, botellones) no debería haber
decimales en absoluto.

**Corrección inmediata:** definir la convención antes de seguir escribiendo, y en los ítems de
unidad entera no permitir decimales. Xetux debería imprimir la planilla con la cantidad de
decimales que corresponde a cada unidad de medida.

### H6 — Doble anotación de la misma cantidad. **Gravedad: media**

En ACEITUNAS NEGRAS el `7.8` está escrito dos veces: al lado del nombre del producto y en la
columna CANTIDAD. En ANCHOAS hay un `7` al lado del nombre pero la columna CANTIDAD está vacía.

Se está anotando primero al margen y después pasando a la columna. Ese paso intermedio es una
transcripción, y toda transcripción introduce error — como ya se ve en ANCHOAS, donde el valor
quedó a medio camino.

**Corrección:** se escribe directo en la columna CANTIDAD, una sola vez.

### H7 — Celda vacía sin significado definido. **Gravedad: media**

La mayoría de las celdas está en blanco. No hay forma de distinguir entre:

- contado y dio cero,
- no se contó,
- no aplica a este conteo.

**Corrección:** cero se escribe `0`. Lo que no se cuenta se raya. Nada queda en blanco.

### H8 — Un solo par de ojos. **Gravedad: media**

La planilla tiene **"TOMADO POR"** y nada más. No hay campo de verificación, ni de hora de
inicio y cierre, ni firma de quien custodia el producto.

**Corrección:** agregar al encabezado: fecha, hora de inicio, hora de cierre, quien cuenta,
quien verifica.

### H9 — Unidades de medida inconsistentes dentro de la misma familia. **Gravedad: media**

**ACEITE DE OLIVA LT** aparece con unidad `UNIDAD` (163), mientras que **ACEITE DE OLIVA PARA
TIENDA LT** aparece con unidad `LT` (14). El nombre del producto dice "LT" en ambos casos.

Si uno se cuenta en botellas y el otro en litros, el consumo teórico contra real nunca va a
cuadrar para ese insumo. Es el caso de libro del problema de conversión de unidades.

**Corrección:** revisar la unidad de medida de cada ítem en el maestro de Xetux, especialmente
donde el nombre del producto contradiga la unidad.

---

## 2. Lo que la planilla revela sobre el CDP

Más allá de los hallazgos, el catálogo responde varias preguntas del diagnóstico sin necesidad
de preguntarlas.

### Qué produce el CDP

Los ítems con prefijo **`XSUB`** son elaborados —lo que el CDP transforma, no lo que compra:

| Código | Producto |
|---|---|
| XSUB2403000002 | **MASA PARA PIZZA 380 G UND** |
| XSUB2407000030 | HARINA PARA ESTIRAR |
| XSUB2403000010 | CEBOLLA CARAMELIZADA |
| XSUB2405000015 | MANTEQUILLA DE AJO |
| XSUB2403000001 | SALSA PARA PIZZA TOMATE PELADO |
| XSUB2605000034 | SALSA PARA PIZZA PASSATA |
| XSUB2605000035 | SALSA MAYO AJO ROSTIZADOS |
| XSUB2605000036 | SALSA MAYO CHAMPIÑONES |
| XSUB2605000037 | SALSA DE PIÑA |
| XSUB2605000038 | SALSA MAYO BACON |
| XSUB2605000039 | SALSA MAYO PESTO |
| XSUB2605000040 | SALSA MIEL PICANTE |
| XSUB2605000041 | SALSA ROMESCO |

**El bollo de masa es de 380 g.** Dato clave para la ficha técnica y el rendimiento de harina.

### Elaborados que están codificados como materia prima

Hay productos que el CDP claramente transforma pero que llevan prefijo `XMAT` (materia prima)
en vez de `XSUB`:

- ALBAHACA PROCESADA KG · CEBOLLA BLANCA PROCESADA KG · CILANTRO PROCESADO KG ·
  PIMENTÓN PROCESADO KG · PIÑA PROCESADA KG
- Todas las **porciones**: aceitunas 60 g, jamón 60 g, jamón serrano 45 g, maíz 60 g,
  nutella 100 g, pepperoni 60 g, queso pecorino 30 g, salchicha italiana 80 g, tocineta 80 g

Esto importa para el modelo de planificación: si los elaborados no están identificados de forma
consistente, no se puede separar automáticamente **lo que se compra** de **lo que se produce**,
y esa separación es la base del plan de producción.

**Nota positiva:** el porcionado está normado al gramo (60 g, 45 g, 80 g, 30 g, 100 g). Eso es
una ficha técnica implícita y es una buena base de partida.

### Existe registro de desperdicio

Hay SKU para **DESPERDICIO DE JAMÓN KG**, **DESPERDICIO DE PEPERONI KG** y **DESPERDICIO DE
TOCINETA KG**. Es decir, el mecanismo para registrar merma de los embutidos ya existe en el
sistema.

Falta confirmar si se usa, con qué frecuencia se carga y si alguien lo revisa. Un SKU de
desperdicio que nadie alimenta es peor que no tenerlo, porque da la impresión de que la merma
está controlada.

### Productos marcados "para tienda"

**ACEITE DE OLIVA PARA TIENDA LT** sugiere que el CDP almacena y despacha insumos destinados a
las tiendas, además de producir. Conviene mapear cuántos ítems del catálogo son de tránsito
(compra → despacho sin transformación) y cuántos son de transformación: son dos flujos
distintos que hoy comparten el mismo almacén y la misma planilla.

---

## 3. Propuesta de planilla corregida

Cambios al formato, en orden de impacto:

**Encabezado**

| Campo | Estado actual |
|---|---|
| Unidad (CDP Caracas / CDP Oriente) | Falta |
| Tipo de conteo (apertura / mensual / sorpresivo) | Falta |
| Fecha | **En blanco** |
| Hora de inicio y de cierre | Falta |
| Tomado por | Existe |
| Verificado por | Falta |

**Cuerpo**

1. Formato de **apertura** limitado a la lista de críticos; formato **mensual** con el catálogo
   completo.
2. Reimprimir desde Xetux el día del conteo.
3. Columna de unidad de medida **al lado de la cantidad**, no al otro extremo de la hoja — hoy
   están separadas por media página en blanco, que es donde se genera el error de fila.
4. Decimales permitidos según la unidad: los ítems `UNIDAD` no admiten decimales.
5. Renglón para **producto en proceso** (masa en fermentación al momento del conteo).
6. Columna de observación por ítem, para anotar el motivo de una diferencia en el momento.

**Lo que NO hay que cambiar:** la planilla **no trae el saldo teórico**, y eso está bien. El
conteo se hace a ciegas y el contraste con Xetux viene después. Es el control mejor resuelto
del formato actual.
