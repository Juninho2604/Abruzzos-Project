# Estructura inicial del repositorio

**Fecha:** 2026-09-18
**Decide:** Omar
**Estado:** vigente

## Contexto

El proyecto de Abruzzos lo llevan varias personas de Escala (Cristian, Omar y Adalberto),
cada una con un foco distinto, y hasta ahora la documentación — propuestas, planes,
procesos, PDF — no tenía un lugar único. Hacía falta un espacio común con historial, donde
se pueda trabajar en paralelo sin sobrescribir el trabajo del otro.

## Decisión

Usar este repositorio como repositorio **documental**, no de código, organizado en
carpetas numeradas por área, con:

- Un responsable declarado por documento.
- Una rama por trabajo, con nombre `<persona>/<tema>`.
- Revisión por Pull Request antes de unir a la rama principal.
- Documentos en Markdown como fuente, y PDF solo como formato de entrega.

## Por qué

Se descartó el esquema de una carpeta compartida en la nube (tipo Drive) como espacio
principal de trabajo porque no deja historial comparable, no permite ver quién cambió qué
línea y por qué, y no tiene un mecanismo de revisión antes de que un cambio quede firme.
Para documentos que van a convertirse en procedimientos aplicados en tienda, ese control
de versiones importa.

La división de carpetas sigue la división real de focos del equipo: Omar en operaciones,
Adalberto en auditoría y control. Cada uno manda en su carpeta, y lo compartido
(expansión, propuestas, reportes) se acuerda entre ambos.

Markdown como fuente en vez de Word: permite comparar cambios línea por línea, que es lo
que hace posible la revisión por Pull Request.

## Consecuencias

- Todo documento nuevo del proyecto nace aquí.
- Los documentos que hoy existan sueltos hay que migrarlos (ver
  [`pendientes-de-arranque.md`](../pendientes-de-arranque.md)).
- Hay que invitar a Adalberto y a Cristian como colaboradores.
- Quien quiera entregar algo al cliente en PDF, lo exporta desde el `.md` fuente.
