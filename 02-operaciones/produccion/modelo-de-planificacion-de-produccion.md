---
titulo: Modelo de planificación de producción del CDP
area: Operaciones
responsable: Omar
estado: borrador
version: 0.1
actualizado: 2026-09-18
---

# Modelo de planificación de producción del CDP

Marco de trabajo para optimizar la producción de los centros de producción. Es el documento
que ordena el encargo de Cristian: cómo planificar mejor la producción del CDP contra lo que
las tiendas realmente necesitan.

---

## 1. El planteamiento

La optimización de un centro de producción se ataca en este orden, y no en otro:

| Orden | Pregunta | Si falla, qué pasa |
|---|---|---|
| **1. Planificación** | ¿Se produce lo que se va a vender? | Merma por un lado y quiebres por el otro, **al mismo tiempo** |
| **2. Proceso** | ¿Se produce bien? | Rendimiento bajo, calidad despareja |
| **3. Productividad** | ¿Se produce con los recursos justos? | Costo de mano de obra alto |

Casi siempre se empieza por el 3 —"pongamos a la gente a rendir más"— y es el que menos mueve
la aguja. Una planta que produce con enorme eficiencia lo que nadie va a vender sigue botando
plata; solo la bota más rápido.

**La señal para saber dónde está parado el CDP hoy:** si hay merma de masa vencida **y**
tiendas que se quedan sin producto en la misma semana, el problema es de planificación. Las
dos cosas juntas no son contradictorias: son el síntoma clásico de producir sin pronóstico.

---

## 2. La cadena de planificación

Así debería decidirse cuánto produce el CDP cada día:

```
   Histórico de venta por tienda, por producto, por día de semana
                            ↓
   Pronóstico de venta de la semana entrante (por tienda, por producto)
                            ↓
   Ficha técnica  →  traducción a insumos
                     (X pizzas medianas = Y bollos de masa + Z kg de salsa)
                            ↓
   − Inventario actual en tienda
                            ↓
   = Necesidad de despacho por tienda
                            ↓
   Suma de todas las tiendas del CDP
                            ↓
   − Inventario de producto terminado en CDP
                            ↓
   = PLAN DE PRODUCCIÓN DEL CDP
                            ↓
   ÷ Capacidad por batch  →  número de batches, secuencia y turnos
```

Cada flecha necesita un dato. Los que **hoy no existen** están marcados:

| Eslabón | Dato que necesita | ¿Existe? |
|---|---|---|
| Histórico de venta | Venta por tienda/producto/día | **No documentado** |
| Pronóstico | Modelo, aunque sea un promedio por día de semana | **No existe** |
| Traducción a insumos | Ficha técnica por producto | **Por confirmar en la visita** |
| Inventario en tienda | Conteo o sistema | Parcial |
| Inventario en CDP | Conteo de apertura | Sí |
| Capacidad | kg/batch, ciclo, cava | **Por levantar** |

> **Atajo válido:** mientras no haya venta por producto, el **histórico de despachos CDP →
> tienda de las últimas 8 semanas** sirve como sustituto. No es la venta real —incluye la
> merma y los errores de pedido— pero captura el patrón de demanda por tienda y por día de
> semana, que es el 80 % de lo que hace falta para empezar a planificar.

---

## 3. Sobre la API de Cetux

Cristian planteó pedirle a Cetux la API para descargar los inventarios de todas las tiendas y
que el CDP pueda verlos en tiempo real. Es la dirección correcta, con una precisión que
conviene hacer **antes** de formular la solicitud, porque cambia lo que hay que pedir.

### Son dos problemas distintos, con dos datos distintos

| | **Reposición** | **Planificación** |
|---|---|---|
| Pregunta que responde | ¿Qué le mando hoy a cada tienda? | ¿Cuánto produzco esta semana? |
| Dato que necesita | **Inventario en tiempo real** | **Histórico de venta / consumo** |
| Horizonte | Horas | Días o semanas |

El inventario en tiempo real resuelve el primero, y lo resuelve muy bien: elimina el pedido
hecho a ojo y los despachos de emergencia.

Pero **no resuelve el segundo**, y el segundo es el que Cristian está pidiendo atacar. El
motivo es el tiempo de proceso: la masa necesita amasado y fermentación. Para cuando el
sistema avisa que la tienda está baja de masa, ya no hay tiempo de amasar. Planificar
producción exige saber **qué se va a vender**, no **qué hay ahora**.

### Qué pedirle a Cetux

Que la API exponga **movimientos y ventas**, no solo saldos:

- [ ] **Ventas por tienda, por producto (SKU), por fecha y hora.** Es el dato que habilita el
      pronóstico. Sin esto, la integración sirve para reponer pero no para planificar.
- [ ] **Existencias por tienda y por insumo**, con marca de tiempo. Para la reposición.
- [ ] **Movimientos de inventario** (entradas, salidas, transferencias, ajustes, mermas), con
      su motivo. Para poder distinguir consumo real de ajuste contable.
- [ ] **Recepciones de despacho del CDP**, para conciliar lo despachado contra lo recibido.
- [ ] Histórico: **al menos 12 meses hacia atrás**, no solo desde la fecha de conexión. Esto
      hay que pedirlo explícitamente; muchos proveedores entregan la API "desde hoy" y se
      pierde un año de patrón de demanda.
- [ ] Documentación de la API, ambiente de prueba y límites de consulta.

> El punto del histórico de 12 meses es el que más suele costar conseguir después y el que más
> vale. Con un año de data se ve la estacionalidad; con dos semanas, solo se ve ruido.

### No hay que esperar la API para arrancar

Negociar, obtener y conectar una API toma meses. El modelo de planificación se puede montar
**esta semana** con los registros de despacho en papel o exportados a Excel. La API después
automatiza lo que ya se sabe hacer a mano.

Montar la automatización antes de entender el patrón de demanda es la forma más común de
gastar meses en una integración que termina alimentando un proceso que nadie definió.

---

## 4. Ruta de implementación

### Fase 0 — Diagnóstico (esta semana)

- Visita de levantamiento con la
  [guía de levantamiento](guia-levantamiento-cdp.md).
- Rescatar los registros de despacho de las últimas 8 semanas.
- Confirmar si existen fichas técnicas.
- Medir capacidad real: batch, ciclo, fermentación, cava.

### Fase 1 — Planificación manual (semanas 2 a 4)

- Construir el **patrón de demanda por tienda y día de semana** con el histórico de despachos.
- Levantar o corregir las **fichas técnicas** de los productos del CDP.
- Definir **vida útil real** por producto y contrastarla con la frecuencia de despacho.
- Armar un **plan de producción semanal** en hoja de cálculo, con revisión diaria.
- Empezar a medir: plan vs. producido, merma, quiebres en tienda.

El entregable de esta fase es una hoja de cálculo que diga, cada día, cuánto amasar. No es
elegante y funciona.

### Fase 2 — Reposición asistida (mes 2 en adelante, sujeto a la API)

- Integrar existencias por tienda para calcular el despacho sobre inventario real, no sobre
  pedido estimado.
- Alertas de punto de reorden por tienda e insumo.

### Fase 3 — Pronóstico (cuando haya histórico de ventas)

- Pronóstico por tienda y producto con estacionalidad de día de semana.
- Ajuste automático del plan de producción.

Cada fase deja valor por sí sola. Si el proyecto se detiene en la fase 1, el CDP ya planifica
mejor que hoy.

---

## 5. Cómo se mide si mejoró

Sin línea base no hay optimización, solo opinión. Estos son los indicadores del CDP; la
columna "hoy" se llena con lo que salga del diagnóstico.

| Indicador | Definición | Hoy | Meta |
|---|---|---|---|
| **Merma %** | Producto perdido / producto producido, por causa | | |
| **Quiebres en tienda** | Veces/semana que una tienda se queda sin un producto del CDP | | |
| **Nivel de servicio** | % de pedidos de tienda atendidos completos y a tiempo | | |
| **Cumplimiento del plan** | Producido / planificado | | |
| **Rendimiento** | Bollos obtenidos por saco de harina, vs. teórico de ficha | | |
| **Productividad** | Unidades producidas por hora-hombre | | |
| **Despachos de emergencia** | Despachos fuera de ruta al mes | | |
| **Utilización de cava** | % de ocupación en el pico | | |

Los dos primeros son la pareja que revela el problema de planificación: **merma y quiebres al
mismo tiempo**. Una operación bien planificada baja los dos a la vez; una mal planificada solo
puede cambiar uno por el otro.

---

## 6. Cómo encaja con el Plan Maestro de Operaciones

El [Plan Maestro](../plan-maestro-de-operaciones.md) de Adalberto ya crea las figuras que
tienen que sostener esto:

- La **Coordinación de Logística** planifica la distribución CDP → tienda *"según la proyección
  de ventas"*.
- La **Coordinación de Compras** consolida la planificación de compras *"a partir de la
  proyección de ventas de cada tienda y CDP"*.

Las dos definiciones dependen de una **proyección de ventas que hoy no existe** — es el mismo
vacío que quedó anotado al revisar el plan. Este trabajo es el que la construye. Sin él, los
dos coordinadores que el plan manda a contratar van a terminar planificando por experiencia,
que es exactamente lo que se hace hoy sin ellos.

Dicho de otro modo: **este no es un trabajo paralelo al plan de Adalberto, es el insumo que le
falta a dos de sus cargos nuevos para poder operar.**
