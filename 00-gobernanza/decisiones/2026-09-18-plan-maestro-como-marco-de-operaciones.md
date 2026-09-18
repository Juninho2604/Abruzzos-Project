# El Plan Maestro de Operaciones queda como marco de referencia

**Fecha:** 2026-09-18
**Decide:** Omar
**Estado:** vigente

## Contexto

Adalberto entregó el *Plan Maestro de Operaciones* (PDF de 17 páginas, 10 de septiembre de
2026), que define estructura organizacional, dotación por categoría de tienda, mallas de
horario, coordinaciones corporativas, estandarización de procesos, plan de aperturas, plan de
acción por fases y cuadro de KPI.

El documento llegó después de que se montara la estructura del repositorio, y es más completo
y más concreto que los esqueletos que había: corrige el número de tiendas, aporta el
organigrama, fija la clasificación por volumen y cierra el diagnóstico de brechas.

## Decisión

1. El plan se transcribe a Markdown en
   [`02-operaciones/plan-maestro-de-operaciones.md`](../../02-operaciones/plan-maestro-de-operaciones.md)
   y queda como **marco de referencia del área de Operaciones**. El PDF original se conserva
   en [`recursos/pdf/`](../../recursos/pdf/) tal como fue entregado.
2. Su responsable sigue siendo **Adalberto**, que es su autor, aunque viva en la carpeta de
   Operaciones.
3. Los documentos que se creen en Operaciones deben encajar en ese marco y citarlo. Si algo
   del plan no funciona en la práctica, se cambia el plan; no se trabaja en paralelo a él.
4. `04-expansion/plan-maestro.md` se renombra a
   [`plan-de-expansion.md`](../../04-expansion/plan-de-expansion.md) y se reescribe para no
   duplicar lo que el plan maestro ya resuelve: recoge solo lo que queda abierto —evaluación
   por plaza, secuencia de oleadas, capacidad de abastecimiento y costo de la expansión.

## Por qué

Se descartó dejar el PDF suelto en `recursos/` y trabajar aparte. Un PDF no se puede comparar
versión contra versión, no se puede enlazar por sección desde otros documentos y no se puede
revisar por Pull Request. Como el plan va a ser la base de casi todo lo que produzca el
proyecto en los próximos meses, necesita ser texto editable con historial.

Se descartó también ponerlo en `03-auditoria-y-control/` por ser de Adalberto. La carpeta la
decide el contenido, no el autor: el plan es de operaciones. Lo que se conserva es el
responsable.

El renombrado de `plan-maestro.md` evita tener dos documentos llamados "plan maestro" en el
mismo repositorio, que es una confusión garantizada en una conversación de trabajo.

## Consecuencias

- Las tiendas, el organigrama y el perfil del negocio en
  [`01-abruzzos/`](../../01-abruzzos/) se actualizaron con la data del plan.
- El plan queda en estado `en revisión`: lo revisan Omar y Cristian antes de pasar a
  `aprobado`.
- Las preguntas abiertas que dejó la revisión están en
  [`pendientes-de-arranque.md`](../pendientes-de-arranque.md), no dentro del plan, para no
  mezclar comentarios ajenos en un documento cuyo responsable es Adalberto.
