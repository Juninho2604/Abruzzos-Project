---
titulo: Pendientes de arranque del repositorio
area: Gobernanza
responsable: Omar
estado: vigente
version: 1.0
actualizado: 2026-09-18
---

# Pendientes de arranque

Lo que falta para que el repositorio quede completamente operativo. Se va tachando.

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

## Información del cliente por cargar

- [ ] Completar el listado real de tiendas en [`01-abruzzos/tiendas.md`](../01-abruzzos/tiendas.md):
      nombre, dirección, fecha de apertura, gerente, turnos.
- [ ] Completar el organigrama en [`01-abruzzos/organigrama.md`](../01-abruzzos/organigrama.md).
- [ ] Completar el perfil del negocio en
      [`01-abruzzos/perfil-del-negocio.md`](../01-abruzzos/perfil-del-negocio.md).
- [ ] Cargar los documentos y procesos que ya existan hoy en Abruzzos (aunque estén
      incompletos o desactualizados). Sirven de punto de partida: es más rápido corregir
      que inventar.

## Primeros documentos a levantar

### Operaciones (Omar)

- [ ] Checklist de apertura de tienda.
- [ ] Checklist de cierre de tienda.
- [ ] Formato de visita/supervisión de tienda.
- [ ] Perfil de cargo del gerente de tienda.
- [ ] Plan de capacitación de gerentes de operaciones.
- [ ] Estándar de atención al cliente.

### Auditoría y control (Adalberto)

- [ ] Procedimiento de conteo de inventario.
- [ ] Procedimiento de compras (foco del mes).
- [ ] Procedimiento de arqueo y control de caja.
- [ ] Formato de informe de auditoría.

### Compartido

- [ ] Plan maestro de expansión ([`04-expansion/plan-maestro.md`](../04-expansion/plan-maestro.md)).
- [ ] Expedientes de las plazas de Lechería y Puerto La Cruz.
- [ ] Definir la periodicidad de los reportes al cliente (semanal / mensual) y quién los firma.

## Acuerdos por cerrar con Cristian

- [ ] Confirmar el alcance formal de la consultoría y el horizonte de la expansión.
- [ ] Definir el tablero de indicadores que se le reporta a la dirección.
- [ ] Definir cada cuánto se revisa el avance del proyecto en conjunto.
