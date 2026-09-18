# Proyecto Abruzzos — Escala Consultores

Repositorio de trabajo del equipo de **Escala Consultores** para el acompañamiento,
control operativo y plan de expansión de **Abruzzos** (pizzería, Venezuela).

Este repositorio **no es de código**. Es el espacio común donde vive la documentación
del proyecto: propuestas, planes, procesos, manuales, auditorías, reportes y los PDF
asociados. La idea es que todo lo que produzcamos quede en un solo lugar, con historial,
y que podamos trabajar en paralelo sin pisarnos.

---

## Quién es quién

| Persona | Rol en el proyecto | Área principal |
|---|---|---|
| **Cristian** | Dueño de Escala Consultores. Lidera la relación con el cliente y la dirección del proyecto de expansión. | Dirección |
| **Omar** | Project manager. Control operativo — actúa como gerente de operaciones externo. | [Operaciones](02-operaciones/) |
| **Adalberto** | Project manager. Auditoría y control interno. | [Auditoría y Control](03-auditoria-y-control/) |

El detalle de funciones está en
[`00-gobernanza/roles-y-responsabilidades.md`](00-gobernanza/roles-y-responsabilidades.md).

---

## Cómo está organizado

| Carpeta | Qué va aquí | Responsable |
|---|---|---|
| [`00-gobernanza/`](00-gobernanza/) | Reglas del repositorio: roles, forma de trabajo, convenciones, decisiones tomadas. | Compartido |
| [`01-abruzzos/`](01-abruzzos/) | Información del cliente: perfil del negocio, tiendas, organigrama. | Compartido |
| [`02-operaciones/`](02-operaciones/) | Estándares operativos, aperturas y cierres, producción, capacitación, supervisión, personal. | Omar |
| [`03-auditoria-y-control/`](03-auditoria-y-control/) | Inventarios, compras, caja, hallazgos de auditoría. | Adalberto |
| [`04-expansion/`](04-expansion/) | Plan maestro de expansión y expedientes por plaza. | Compartido |
| [`05-propuestas/`](05-propuestas/) | Propuestas formales al cliente y documentos comerciales. | Compartido |
| [`06-reportes/`](06-reportes/) | Reportes periódicos de avance (semanales y mensuales). | Compartido |
| [`99-plantillas/`](99-plantillas/) | Plantillas para no arrancar nunca de cero. | Compartido |
| [`recursos/`](recursos/) | Archivos binarios: PDF, imágenes, fotos de tienda. | Compartido |

---

## Documento de referencia del proyecto

El [**Plan Maestro de Operaciones**](02-operaciones/plan-maestro-de-operaciones.md), preparado
por Adalberto en septiembre de 2026, es el marco sobre el que se apoya el resto del trabajo:
estructura organizacional, dotación por tienda, mallas de horario, estandarización de procesos,
plan de aperturas y KPI. Está **en revisión**.

Lectura corta si vas de entrada: el resumen ejecutivo y el diagnóstico (secciones 1 y 2), y el
plan de acción por fases (sección 13).

## Situación del negocio, en una línea

**7 tiendas y 2 centros de producción**, con 6 tiendas nuevas en desarrollo — La Parada,
Charallave, San Antonio de los Altos, Paraíso, Catia y Valencia — que llevarán la red a **13
puntos de venta**.

## Cómo empezar a trabajar aquí

1. Lee [`00-gobernanza/forma-de-trabajo.md`](00-gobernanza/forma-de-trabajo.md). Son 5 minutos
   y explica cómo evitamos pisarnos el trabajo.
2. Para crear un documento nuevo, copia la plantilla que corresponda de
   [`99-plantillas/`](99-plantillas/) a la carpeta de su área.
3. Nombra el archivo con la convención acordada
   ([`00-gobernanza/convenciones.md`](00-gobernanza/convenciones.md)).
4. Sube el cambio en una rama propia y ábrelo como Pull Request para que el otro lo revise.

### Regla corta

> **Cada documento tiene un responsable.** Si el documento no es tuyo, no lo editas
> directo: propones el cambio en un Pull Request y su responsable lo aprueba.

---

## Estado del repositorio

Inaugurado el **18 de septiembre de 2026**. La estructura está montada, las plantillas listas y
el Plan Maestro de Operaciones cargado; el resto del contenido se irá sumando sobre la marcha.

Pendientes de arranque en
[`00-gobernanza/pendientes-de-arranque.md`](00-gobernanza/pendientes-de-arranque.md).
