---
titulo: Guía de levantamiento de información en centro de producción
area: Operaciones
responsable: Omar
estado: borrador
version: 0.1
actualizado: 2026-09-18
aplica_a: CDP Caracas · CDP Oriente
---

# Guía de levantamiento de información en CDP

Instrumento de campo para la visita de diagnóstico a un centro de producción. Sirve para las
dos unidades: se aplica igual en CDP Caracas y en CDP Oriente, y así los resultados se pueden
comparar.

**Cómo usarla:** se recorre en el orden de los bloques. El bloque A se hace mientras se
acompaña el inventario de apertura; el resto, recorriendo la planta y preguntando.

**Regla de la visita:** se pregunta **"muéstrame cómo lo haces"**, no *"¿cómo lo hacen?"*. Lo
que la gente describe y lo que la gente hace se parecen menos de lo que uno cree, y la
diferencia entre ambas cosas es justamente donde está la oportunidad de optimización.

---

## Bloque A — El inventario de apertura

Doble objetivo: **hacer el conteo** y, de paso, **evaluar el instrumento** con el que se hace.

### A.1 Sobre la planilla de productos críticos

| # | Pregunta | Respuesta |
|---|---|---|
| A1 | ¿Cuántos ítems tiene la planilla de críticos? | |
| A2 | ¿Con qué criterio se definió que esos son los críticos? (valor, rotación, riesgo de desviación) | |
| A3 | ¿Quién la definió y cuándo se actualizó por última vez? | |
| A4 | ¿Hay algún insumo de alto valor o alta rotación que **no** esté en la planilla? | |
| A5 | ¿La unidad de medida de cada ítem es la misma en la planilla, en el sistema y en la cabeza de quien cuenta? (bollos / kg / bandejas / unidades) | |

> La pregunta A5 parece menor y no lo es. La mitad de las diferencias de inventario en una
> planta de producción no son faltantes: son conversiones de unidad hechas de memoria.

### A.2 Sobre cómo se ejecuta el conteo

| # | Pregunta | Respuesta |
|---|---|---|
| A6 | ¿Quién cuenta físicamente? ¿Es la misma persona que custodia el producto? | |
| A7 | ¿Cuenta solo o con un segundo que verifica? | |
| A8 | ¿Se cuenta **antes** de que entre la producción del día, o después? ¿Siempre a la misma hora? | |
| A9 | ¿Quien cuenta ve el saldo teórico del sistema antes de contar? | |
| A10 | ¿Cuánto tarda el conteo completo? | |

> **A9 es la pregunta de control más importante del bloque.** Si quien cuenta tiene delante lo
> que el sistema dice que debería haber, el conteo deja de ser un conteo: se vuelve una
> confirmación. Los conteos se hacen a ciegas y el contraste viene después.

### A.3 Sobre el producto en proceso

| # | Pregunta | Respuesta |
|---|---|---|
| A11 | Al momento del conteo, ¿hay masa en fermentación, en cava o a medio proceso? | |
| A12 | ¿Ese producto en proceso se cuenta? ¿En qué renglón? | |
| A13 | ¿Se cuenta la materia prima ya consumida en un batch que todavía no es producto terminado? | |

> En un CDP siempre hay producto en tránsito entre materia prima y producto terminado. Si no
> se cuenta, el inventario **nunca** va a cuadrar, y se va a estar buscando una fuga donde solo
> hay un bache de medición.

### A.4 Sobre qué pasa después del conteo

| # | Pregunta | Respuesta |
|---|---|---|
| A14 | ¿Contra qué se compara el conteo? | |
| A15 | Cuando hay diferencia, ¿se investiga o se ajusta el sistema y se sigue? | |
| A16 | ¿A partir de qué diferencia se considera que hay un problema? ¿Existe un umbral? | |
| A17 | ¿Quién recibe el resultado del conteo y qué hace con él? | |
| A18 | ¿Se guardan las planillas de los conteos anteriores? ¿Dónde? ¿Desde cuándo? | |

> **A18 vale oro.** Si existen las planillas de los últimos meses, ahí está el histórico de
> consumo del CDP — que es la materia prima para planificar la producción sin esperar ninguna
> API. Pídelas antes de irte.

---

## Bloque B — Mapa del proceso

Objetivo: dibujar cómo fluye el producto desde que entra la harina hasta que sale el despacho.

| # | Qué levantar | Respuesta |
|---|---|---|
| B1 | ¿Qué productos produce el CDP? (masa por tamaño, salsas, quesos rallados, vegetales cortados, otros) | |
| B2 | Para cada producto: secuencia de estaciones, de principio a fin | |
| B3 | ¿Cuánto tarda cada etapa? (amasado, división/boleado, fermentación, enfriado, empaque) | |
| B4 | ¿Cuántas personas hay en cada estación y qué hace cada una? | |
| B5 | ¿Hay ficha técnica escrita por producto, o la receta está en la cabeza del cocinero? | |
| B6 | ¿Se pesa la materia prima o se echa "a ojo"? ¿Hay balanza en cada estación? | |
| B7 | ¿Dónde se acumula producto esperando la siguiente etapa? | |

> **B7 señala el cuello de botella.** Donde se forma la cola, ahí está la restricción. No hace
> falta cronómetro para verlo: hace falta caminar la planta y mirar dónde hay producto parado.

**Croquis.** Dibuja a mano o toma fotos del recorrido físico: dónde entra la materia prima,
dónde está cada estación, dónde está la cava, por dónde sale el despacho. Guárdalas en
[`recursos/imagenes/`](../../recursos/imagenes/). Si el producto cruza la planta de ida y
vuelta, eso ya es un hallazgo.

---

## Bloque C — Capacidad y restricciones

Objetivo: saber cuánto puede producir esta planta realmente, que casi nunca es lo que la gente
cree.

| # | Qué levantar | Respuesta |
|---|---|---|
| C1 | Amasadoras: cuántas, capacidad en kg por batch, minutos por ciclo | |
| C2 | ¿Cuántos batches se hacen en un día normal? ¿Y en un viernes o sábado? | |
| C3 | Tiempo de fermentación/leudado por tipo de masa | |
| C4 | Cava de refrigeración: capacidad (bandejas o m³), temperatura de operación | |
| C5 | Cava de congelación, si existe: capacidad y uso | |
| C6 | ¿Qué tan llena está la cava en el momento de la visita? (foto) | |
| C7 | Horno, si el CDP hornea: capacidad y tiempo de ciclo | |
| C8 | ¿Cuál es, a juicio del Jefe de CDP, el paso que más limita la producción? | |
| C9 | ¿Qué pasa si una tienda pide un 30 % más de lo normal? ¿Se puede? | |

> **Ojo con C4 y C6.** En un CDP de masa, el cuello de botella real rara vez es amasar: suele
> ser **dónde guardar lo amasado**. La capacidad de refrigeración y el tiempo de fermentación
> son restricciones físicas que no se resuelven poniendo más gente.

---

## Bloque D — Cómo se decide hoy qué producir

**Este es el bloque central de la visita.** Todo lo demás es contexto; aquí está la
optimización.

| # | Pregunta | Respuesta |
|---|---|---|
| D1 | ¿Quién decide cuánto se produce de cada cosa cada día? | |
| D2 | ¿Con base en qué lo decide? (pedido de tienda, histórico, experiencia, corazonada) | |
| D3 | ¿Existe un plan de producción escrito, o se decide en la mañana? | |
| D4 | ¿Con cuánta anticipación se sabe lo que hay que producir? | |
| D5 | ¿Las tiendas mandan un pedido? ¿En qué formato y con qué anticipación? | |
| D6 | ¿El pedido de la tienda se produce tal cual, o el CDP lo ajusta? ¿Con qué criterio? | |
| D7 | ¿Se lleva registro de lo planificado vs. lo producido? | |
| D8 | ¿Se toma en cuenta el día de la semana? (viernes y sábado son los de mayor demanda) | |
| D9 | ¿Qué pasó la última vez que una tienda se quedó sin masa? ¿Cada cuánto pasa? | |
| D10 | ¿Qué pasa con la masa que sobra al final del día? | |

> **D2 y D9 juntas dan el diagnóstico.** Si la respuesta a D2 es "por experiencia" y la de D9
> es "pasa seguido", entonces la planta no tiene un problema de productividad: tiene un
> problema de planificación, y meterle más gente o más horas no lo va a resolver.

---

## Bloque E — Vida útil y merma

| # | Qué levantar | Respuesta |
|---|---|---|
| E1 | Vida útil real de cada producto, en días (masa, salsas, cada ítem) | |
| E2 | ¿Está rotulado con fecha? ¿Quién rotula? | |
| E3 | ¿Se aplica PEPS de verdad o se toma lo que está más a mano? | |
| E4 | ¿Cuánta merma hubo el mes pasado? ¿Está medida o es una estimación? | |
| E5 | ¿Se registra la merma por causa? (vencimiento, error de proceso, devolución de tienda) | |
| E6 | ¿Las tiendas devuelven producto al CDP? ¿Cuánto y por qué? | |
| E7 | ¿Cuánto rinde un saco de harina en bollos? ¿Coincide con lo teórico? | |

> **E1 condiciona todo el modelo de planificación.** Si la masa dura 3 días y se despacha 2
> veces por semana, la tienda está obligada a almacenar producto que se le va a vencer. Esa
> tensión entre vida útil y frecuencia de despacho es donde se genera la merma, y no se
> resuelve en la tienda: se resuelve cambiando la frecuencia o la vida útil.

---

## Bloque F — Despacho a tiendas

| # | Qué levantar | Respuesta |
|---|---|---|
| F1 | ¿Qué tiendas abastece este CDP? | |
| F2 | ¿Con qué frecuencia despacha a cada una? ¿Días fijos? | |
| F3 | ¿En qué se transporta? ¿Hay cadena de frío en el traslado? | |
| F4 | ¿Cuánto tarda el recorrido a cada tienda? | |
| F5 | ¿Quién recibe en la tienda y qué verifica? | |
| F6 | ¿Se firma una guía de despacho? ¿Queda copia en ambos lados? | |
| F7 | ¿Con qué frecuencia lo despachado no coincide con lo recibido? | |
| F8 | ¿Cuántas veces al mes hay un despacho de emergencia fuera de ruta? | |

> **F8 es un buen termómetro.** Cada despacho de emergencia es una falla de planificación que
> además cuesta transporte. Si son frecuentes, hay un número que justifica el esfuerzo de
> montar el modelo de planificación.

---

## Bloque G — Personal y turnos

| # | Qué levantar | Respuesta |
|---|---|---|
| G1 | ¿Cuántas personas hay hoy realmente? (contrastar con las 14 del plan maestro) | |
| G2 | ¿Qué cargos y cuántos de cada uno? | |
| G3 | ¿Qué horario cumplen realmente? ¿Coincide con las mallas del plan? | |
| G4 | ¿A qué hora arranca la producción y a qué hora termina? | |
| G5 | ¿Hay picos de trabajo y horas muertas en el mismo turno? ¿Cuándo? | |
| G6 | ¿Quién cubre cuando falta alguien? | |
| G7 | ¿Cuánta gente entró y salió en los últimos 3 meses? | |

> **G5 importa para la optimización.** Si hay 4 horas muertas en la mañana y todo el mundo
> corriendo en la tarde, el problema no es la cantidad de gente: es el escalonamiento del
> turno contra la curva de producción.

---

## Bloque H — Qué llevarse antes de salir

Lo que no consigas hoy, difícilmente lo consigas por teléfono después.

- [ ] **Copia de la planilla de inventario de apertura** (el formato en blanco).
- [ ] **Copia de la planilla de inventario mensual** (el formato en blanco).
- [ ] **Planillas de conteo de los últimos 2–3 meses**, llenas. Son el histórico de consumo.
- [ ] **Registros de despacho CDP → tienda de las últimas 8 semanas.** Es el dato más valioso
      de la visita: con eso se puede construir el patrón de demanda por tienda y por día de
      semana sin depender de ningún sistema.
- [ ] **Fichas técnicas** de los productos, si existen.
- [ ] **Registro de mermas**, si existe.
- [ ] Fotos: recorrido de la planta, estaciones, cava (llena), rotulado de producto, pizarras
      o cuadernos donde se anota la producción.
- [ ] Nombre y contacto del Jefe de CDP y de quien lleva el inventario.

> El punto de los **registros de despacho de 8 semanas** es el que hay que pelear. Con eso se
> construye el modelo de planificación esta misma semana. Sin eso, hay que esperar a la API.

---

## Cierre de la visita

Antes de salir, cinco minutos con el Jefe de CDP:

1. **Qué le quita el sueño.** Pregunta abierta, sin guiarlo. Lo que sale primero suele ser el
   problema real.
2. **Qué cambiaría si pudiera cambiar una sola cosa.**
3. **Qué le pide a las tiendas que no le dan.**
4. Explicarle qué se va a hacer con lo levantado y cuándo vuelves. Una visita de diagnóstico
   que no vuelve con nada quema la confianza para la siguiente.

Los resultados se vacían en el diagnóstico de la unidad —
[`diagnostico-cdp-caracas.md`](diagnostico-cdp-caracas.md) — el mismo día, mientras está
fresco.
