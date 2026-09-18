---
titulo: Pendientes de arranque del repositorio
area: Gobernanza
responsable: Omar
estado: vigente
version: 1.1
actualizado: 2026-09-18
---

# Pendientes de arranque

Lo que falta para que el repositorio y el proyecto queden en marcha. Se va tachando.

## Lo primero: renombrar la rama principal

El repositorio se inauguró estando vacío, así que la rama con la que se subió todo quedó
como rama principal por defecto, con un nombre que no sirve para eso a largo plazo.

- [ ] Renombrar la rama principal a `main`:
      **Settings → Branches → junto a la rama, el ícono de lápiz → escribir `main` → Rename branch.**

GitHub conserva todo el historial y no se pierde nada. A partir de ahí, la rama principal
se llama `main` y las ramas de trabajo se abren desde ella, como dice
[`forma-de-trabajo.md`](forma-de-trabajo.md).

## Accesos

- [ ] Invitar a **Adalberto** como colaborador del repositorio
      (Settings → Collaborators → Add people).
- [ ] Invitar a **Cristian** como colaborador.
- [ ] Anotar los usuarios de GitHub de ambos en
      [`.github/CODEOWNERS`](../.github/CODEOWNERS) para que las revisiones se asignen solas.

---

## Preguntas abiertas sobre el Plan Maestro de Operaciones

El [Plan Maestro de Operaciones](../02-operaciones/plan-maestro-de-operaciones.md) de
Adalberto ya está cargado. Estas son las preguntas que quedaron abiertas al revisarlo.

### De data

- [ ] **Guatire.** En la conversación de arranque se mencionó como zona en operación, pero no
      aparece entre las 7 tiendas del plan. ¿Existe el punto, se cerró, o fue confusión con
      Guarenas?
- [ ] **Charallave.** Se mencionó como zona en operación, pero el plan la lista entre las 6
      tiendas nuevas en desarrollo. ¿Cuál de las dos es?
- [ ] **Zona de La Parada.** El plan la nombra sin ubicarla.
- [ ] **Grafía de la marca:** *Abruzzo's* (como en el plan) o *Abruzzos*. Unificar antes de
      que salga material al cliente.
- [ ] **La versión anterior del plan.** El documento se declara revisión de una edición
      previa que no está en el repositorio. Pedírsela a Adalberto y cargarla para tener el
      historial completo.

### De contenido del plan

- [ ] **Completar la frase cortada de la sección 3.1.** La descripción de la Línea 2 termina
      en *"No obstante,"* y se corta. Es justo la frase que delimita la relación entre el
      Gerente de Operaciones y el Supervisor de Operaciones.
- [ ] **Ventas por tienda.** El plan es sólido en estructura y costo, pero no trae una sola
      cifra de venta. Sin eso no se puede validar la clasificación por volumen, ni saber qué
      porcentaje de la venta se lleva la nómina propuesta, ni decidir si $8,900/mes es
      sostenible para una tienda de alto volumen. Es el vacío más importante.
- [ ] **Criterio numérico de la clasificación por volumen.** El plan clasifica las tiendas en
      alto y medio volumen, pero no dice a partir de qué cifra una tienda es de alto volumen.
- [ ] **Nómina proyectada para 13 tiendas.** El consolidado de $58,800/mes cubre la red
      actual. Falta la proyección con las 6 nuevas.
- [ ] **Inversión de apertura por tienda** (obra, equipos, POS, mobiliario, primer surtido).
- [ ] **Abastecimiento de Valencia.** Ningún CDP la cubre de forma natural. Definir si se
      surte desde Caracas, produce en sitio o requiere un tercer CDP.

### De roles del equipo

- [ ] **Confirmar que la Dirección de Operaciones del plan es el rol de Omar.** Y con qué
      nombre se comunica a la organización: el plan reserva *"Gerente de Operaciones"* para el
      cargo **interno** de $1,300/mes, así que usar ese título para alguien de Escala choca
      directamente con la línea de mando del organigrama.
- [ ] **Definir dónde encaja Adalberto en el organigrama.** El plan pone Compras, Logística e
      inventario bajo el Gerente de Operaciones (interno) y la auditoría OER bajo el Supervisor
      de Operaciones (externo), pero no dice en qué punto entra la auditoría que Adalberto hace
      desde Escala sobre inventarios, compras y caja.
- [ ] **Honorarios de la Dirección de Operaciones y de los Supervisores de Operaciones.** Son
      los dos cargos externos del organigrama y el plan los deja "a definir". Acuerdo con
      Cristian.
- [ ] **Confirmar si los Supervisores de Operaciones los aporta Escala o los contrata
      Abruzzo's.** Cambia el alcance de la consultoría.

---

## Información del cliente por cargar

- [x] Listado de tiendas — cargado desde el plan maestro en
      [`01-abruzzos/tiendas.md`](../01-abruzzos/tiendas.md). Faltan direcciones, gerentes y
      fechas de apertura.
- [x] Organigrama — el propuesto está en
      [`01-abruzzos/organigrama.md`](../01-abruzzos/organigrama.md). Faltan los nombres reales.
- [ ] Completar el perfil del negocio en
      [`01-abruzzos/perfil-del-negocio.md`](../01-abruzzos/perfil-del-negocio.md): carta,
      ticket promedio, perfil del cliente, competencia, proveedores.
- [ ] **Dotación actual real por tienda**, para contrastarla con la dotación propuesta en la
      sección 6 del plan y saber de qué tamaño es el ajuste.
- [ ] Cuáles son las 3 tiendas que hoy sí tienen Sub-Gerente.
- [ ] Cargar los documentos y procesos que ya existan hoy en Abruzzo's, aunque estén
      incompletos o desactualizados. Sirven de punto de partida.

---

## Primeros documentos a levantar

El plan de acción del plan maestro ya fija las prioridades. Esta lista sigue ese orden.

### Fase 1 — Fundamentos (mes 1–2)

- [ ] **Manual de Operaciones Estándar, versión 1.** Es el entregable central de la fase.
      Empezar por: recetas y gramajes, tiempos de servicio, checklist de apertura/cierre y
      mallas de horario. Va en [`02-operaciones/estandares/`](../02-operaciones/estandares/).
- [ ] Perfiles de cargo por posición (insumo para RR. HH. y para la selección de las tiendas
      nuevas) → [`02-operaciones/personal/`](../02-operaciones/personal/).
- [ ] Formato de auditoría OER a partir del checklist de la sección 9.3 del plan →
      [`99-plantillas/`](../99-plantillas/) o
      [`02-operaciones/supervision/`](../02-operaciones/supervision/).

### Fase 2 — Estandarizar la red actual (mes 2–4)

- [ ] Plan de capacitación de la Academia Abruzzo's →
      [`02-operaciones/capacitacion/`](../02-operaciones/capacitacion/).
- [ ] Procedimiento de compras centralizado (foco del mes de Adalberto) →
      [`03-auditoria-y-control/compras/`](../03-auditoria-y-control/compras/).
- [ ] Procedimiento de conteo de inventario →
      [`03-auditoria-y-control/inventarios/`](../03-auditoria-y-control/inventarios/).
- [ ] Procedimiento de arqueo y control de caja →
      [`03-auditoria-y-control/caja/`](../03-auditoria-y-control/caja/).
- [ ] Línea base: primera ronda de auditorías OER en las 7 tiendas.

### Expansión

- [ ] Expediente de cada una de las 6 plazas →
      [`04-expansion/plazas/`](../04-expansion/plazas/). Empezar por Valencia.
- [ ] Definir el orden de las oleadas de apertura.

---

## Acuerdos por cerrar con Cristian

- [ ] Revisar y aprobar el Plan Maestro de Operaciones, o devolverlo con ajustes.
- [ ] Confirmar el alcance formal de la consultoría y el horizonte de la expansión.
- [ ] Honorarios de las figuras externas (Dirección de Operaciones y Supervisores).
- [ ] Definir el tablero de indicadores que se le reporta a la dirección. El plan ya propone 8
      KPI (sección 14): confirmar si esos son los que se reportan.
- [ ] Definir la periodicidad de los reportes y quién los firma.
- [ ] Definir cada cuánto se revisa el avance del proyecto en conjunto.
