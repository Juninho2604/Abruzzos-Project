---
titulo: Notas de entrevista al Jefe de CDP — 18 de septiembre de 2026
area: Operaciones
responsable: Omar
estado: borrador
version: 0.1
actualizado: 2026-09-18
---

# Notas de entrevista al Jefe de CDP

**Fecha:** 2026-09-18 · **Entrevista:** Omar · **Unidad:** CDP (confirmar si Caracas)
Levantado con el [guion de entrevista](guion-entrevista-jefe-cdp.md).

> Primera tanda de notas, tomadas durante la visita. Lo textual está separado de la
> interpretación, como corresponde: dentro de tres días ya no se distinguen.

---

## PARTE 1 — Lo que se levantó (sin interpretar)

### Personal y horarios

| Dato | Valor |
|---|---|
| Total de personas en el CDP | **11** |
| Trabajan de 9:00 a.m. a 9:00 p.m. | **10** |
| Trabajan de 2:00 p.m. a 9:00 p.m. | **1** |

**Carmelo** hace los despachos y, al regresar al CDP, se incorpora a producción.

### Estaciones

| Estación | Personas | Qué hace |
|---|---|---|
| Masas | **3** | |
| Jamón | 1 | Rebana y porciona |
| Tocineta | _(por confirmar)_ | Rebana y porciona |
| Pepperoni | _(por confirmar)_ | Porciona |
| Nutella | _(por confirmar)_ | Porciona |
| Maíz | _(por confirmar)_ | Porciona |
| Aceituna | _(por confirmar)_ | Porciona |
| Pecorino | _(por confirmar)_ | _(sin detalle)_ |
| Salsas especiales | _(por confirmar)_ | Romesco, ajo, mayo pesto, mayo bacon, piña, miel picante, mayo champiñones |
| Salsa para pizza | _(por confirmar)_ | |

Las 7 salsas especiales coinciden exactamente con los `XSUB` del catálogo de Xetux
([análisis de la planilla](analisis-planilla-inventario.md), sección 2).

### Cómo se decide qué producir — respuesta textual

> «Cuando yo llego en la mañana lo que hago es reviso las neveras, lo que queda de mercancía,
> las masas viejas, lo que queda de topping viejo y de ahí procedo a decirle por lo menos a los
> muchachos cada uno que haga el maíz, lo que se vaya a hacer, de acuerdo a lo que quedó, de
> igual manera con el pepperoni, pecorino, tocineta, Nutella, las salsas especiales, las salsas
> para pizza.
>
> Todo se hace un conteo antes de mandar hacerlo del día siguiente. De igual manera de que
> quede lo que quedó el día anterior, se cuenta todo y se saca el cálculo para saber lo que se
> va a hacer a diario.»

---

## PARTE 2 — Análisis

### A1 — El método planifica mirando hacia atrás. **Este es el hallazgo central.**

El cálculo que describe es:

```
Lo que quedó en nevera  →  decidir cuánto producir
```

Falta el otro término de la ecuación:

```
Lo que quedó en nevera  →  [ CUÁNTO SE VA A VENDER ]  →  decidir cuánto producir
```

Lo que hace hoy el CDP no es planificación de producción: es **reposición de inventario**.
Repone lo que se consumió, bajo el supuesto implícito de que mañana se va a consumir lo mismo
que ayer.

Ese supuesto funciona cuando la demanda es plana. **En una pizzería no lo es** — el propio Plan
Maestro fija viernes y sábado como los días de mayor demanda. Y cuando la demanda varía, el
método falla de forma predecible y en las dos direcciones:

| Día que se planifica | Se repone según el consumo de | Resultado esperable |
|---|---|---|
| Jueves para viernes | Miércoles (día bajo) | **Se produce corto** → quiebre o corrida de emergencia el viernes |
| Domingo para lunes | Sábado (día pico) | **Se produce de más** → merma a principios de semana |

Esto explica el patrón que buscábamos: **merma y quiebres conviviendo en la misma semana**. No
son contradictorios y no son descuido de nadie — son la consecuencia mecánica de reponer sin
pronóstico.

**Verificación pendiente:** contrastar si los quiebres se concentran en jueves–viernes y la
merma a principios de semana. Si el patrón se confirma, queda demostrado con data.

### A2 — El método no está mal ejecutado; le falta un dato

Hay que decirlo con precisión, porque determina la recomendación. El método actual tiene cuatro
cosas bien hechas:

- Se verifica **físicamente** antes de decidir. No se produce a ciegas.
- Se cuenta lo que quedó y se descuenta. La lógica de reposición es correcta.
- Se hace **todos los días**, con disciplina.
- Se toma en cuenta el estado del producto (distingue lo viejo de lo nuevo).

No le falta rigor. Le falta **un insumo**: cuánto se va a vender.

**De ahí sale la recomendación, y es más sencilla de lo que parece: no hay que cambiar el
método ni la persona. Hay que agregarle una columna.** Él ya cuenta lo que quedó; al lado de
ese número debe tener *lo que se despachó el mismo día de la semana pasada*. Con eso, su mismo
cálculo deja de ser reposición y pasa a ser planificación.

### A3 — Ya existe un conteo diario. Es la mejor noticia de la visita.

*«Todo se hace un conteo antes de mandar hacerlo del día siguiente... se cuenta todo y se saca
el cálculo.»*

El CDP **ya cuenta su inventario todos los días**. Eso es un hábito instalado, disciplinado y
gratuito, y es exactamente la materia prima del modelo de planificación.

**La pregunta que hay que hacer de inmediato: ¿dónde se anota ese conteo y se guarda?**

- **Si se guarda** (cuaderno, hoja, Xetux): ya existe el histórico de consumo diario del CDP y
  se puede reconstruir el patrón de demanda por día de semana **sin esperar la API**.
- **Si no se guarda:** hay que empezar a guardarlo hoy. Es costo cero —ya se hace el conteo,
  solo falta archivar la hoja— y en cuatro semanas habilita el modelo completo.

### A4 — El horizonte de producción es de un día

*«...antes de mandar hacerlo del día siguiente.»* Se cuenta hoy y se produce para mañana.

Es una buena noticia técnica: con un horizonte de un día, **no hace falta un pronóstico
sofisticado**. Basta el promedio del mismo día de la semana de las últimas cuatro semanas. Eso
se resuelve en una hoja de cálculo, no en un sistema.

### A5 — Jornada de 12 horas. **Gravedad: alta.**

Diez de las once personas cubren de 9:00 a.m. a 9:00 p.m.: **12 horas diarias**.

Dos implicaciones, y hay que tratarlas por separado:

1. **Cumplimiento laboral.** Una jornada diurna de 12 horas excede la jornada ordinaria y
   supone horas extra sistemáticas. No corresponde a este documento determinar el encuadre
   legal exacto — **hay que revisarlo con quien tenga la competencia**, y encaja en el área de
   control interno de Adalberto, no en la operativa.
2. **Productividad.** El rendimiento de las últimas horas de una jornada de 12 es
   sustancialmente menor que el de las primeras. Si además hay horas muertas —cosa probable en
   una planta con estaciones de porcionado— entonces se está pagando presencia, no producción.

**Contradice el Plan Maestro**, que dimensiona el CDP con turnos de *«3 días x 8 h, 2 libres, 2
días ambos turnos»*. La malla propuesta asume 8 horas; la realidad son 12.

### A6 — Once personas contra las catorce del Plan Maestro

| | Plan Maestro (CDP Caracas) | Real |
|---|---|---|
| Jefe de CDP | 1 | _¿incluido en los 11?_ |
| Cocinero Experto | 3 | |
| Ayudante de Cocina | 10 | |
| **Total** | **14** | **11** |

Faltan tres respecto al plan. Hay que determinar si el plan sobredimensionó o si la planta está
corta — y el dato de las 12 horas sugiere lo segundo: **puede que las 12 horas sean el parche
con el que se cubre la brecha de dotación.** Si es así, pasar a jornadas de 8 horas obliga a
contratar, y ese costo tiene que estar en el número.

### A7 — Carmelo despacha y produce. **Control interno.**

La misma persona que sale con el despacho regresa a producir. Dos observaciones:

- **Separación de funciones.** Quien despacha y quien produce siendo la misma persona elimina
  un control natural. Corresponde revisarlo con Adalberto.
- **Capacidad.** Mientras Carmelo está fuera despachando, su estación queda sin cubrir — o la
  cubre alguien más, restándola de la suya. En una planta de 11 personas eso no es menor.

Falta precisar si Carmelo es el colaborador del turno de 2:00 p.m. a 9:00 p.m. o uno de los
diez de 9 a 9.

### A8 — «Masas viejas» y «topping viejo» son vocabulario cotidiano

El encargado usa ambos términos con naturalidad al describir su rutina. Que existan como
categoría corriente indica que el producto próximo a vencer **es parte del día a día**, no una
excepción.

La pregunta que se abre es importante para el cálculo: al contar lo viejo como existencia
disponible y descontarlo de lo que hay que producir, **se está asumiendo que se va a consumir**.
Si en realidad vence antes, el cálculo de reposición queda inflado y la merma llega igual, solo
que más tarde y sin que nadie la atribuya a esta decisión.

**Por precisar:** ¿«viejo» significa «de ayer» (apto) o «cerca de vencer» (en riesgo)? ¿Cuál es
la vida útil de la masa?

### A9 — Estaciones sin respaldo y con carga muy desigual

Tres personas en masas y una por estación en el resto. De ahí salen dos preguntas de
optimización:

- **¿Hay respaldo?** Si el de masas falta, ¿quién amasa? Una estación crítica con una sola
  persona formada es un riesgo de continuidad.
- **¿Cuánto trabajo real tiene cada estación?** Porcionar maíz o aceitunas difícilmente ocupa
  una jornada completa. Si hay estaciones de una hora de trabajo real dentro de un turno de 12,
  ahí hay capacidad ociosa que se puede reasignar sin contratar a nadie.

Falta confirmar si las personas están fijas por estación o rotan.

---

## PARTE 3 — Preguntas de seguimiento

Por orden de urgencia. Las cuatro primeras, de ser posible, en la misma conversación.

1. **¿Dónde se anota el conteo diario? ¿Se guardan esas hojas? ¿Desde cuándo?**
   *(La más importante de todas. Define si el modelo arranca esta semana o en cuatro.)*
2. ¿«Masa vieja» es de ayer o próxima a vencer? ¿Cuántos días dura la masa?
3. ¿Produce distinto un jueves que un domingo? ¿Toma en cuenta el día de la semana?
4. ¿Cuánto se despacha a cada tienda y qué días?
5. ¿Carmelo es el del turno de 2 a 9? ¿Quién cubre su estación mientras despacha?
6. ¿Las personas están fijas por estación o rotan?
7. ¿Los 11 incluyen al Jefe de CDP?
8. ¿Se trabaja 12 horas todos los días? ¿Cuántos días a la semana? ¿Cómo son las libranzas?
9. ¿Cuántas personas hay realmente en cada estación además de masas y jamón?
