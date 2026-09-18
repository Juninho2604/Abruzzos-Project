---
titulo: Forma de trabajo en el repositorio
area: Gobernanza
responsable: Compartido (Omar / Adalberto)
estado: vigente
version: 1.0
actualizado: 2026-09-18
---

# Forma de trabajo

El objetivo de estas reglas es simple: **que dos personas puedan trabajar al mismo tiempo
sin pisarse ni perder trabajo.**

---

## 1. Cada documento tiene un responsable

En el encabezado de cada documento va el campo `responsable`. Esa persona decide qué
entra y qué no entra en ese documento.

- Si el documento es tuyo → lo editas y lo subes.
- Si el documento **no** es tuyo → no lo editas directo. Propones el cambio en un Pull
  Request y su responsable lo revisa.
- ¿Urgente y el responsable no está? Haz el cambio, súbelo en su rama y avísale. Queda el
  historial para que lo revise después.

## 2. Una rama por trabajo

Nunca se trabaja directo sobre la rama principal. Cada cambio va en su propia rama:

```
<tu-nombre>/<tema-corto>
```

Ejemplos:

```
omar/manual-apertura-tienda
omar/checklist-supervision
adalberto/procedimiento-compras
adalberto/auditoria-inventario-agosto
```

Así, aunque los dos estemos trabajando el mismo día, cada uno tiene su carril.

## 3. Todo entra por Pull Request

Cuando el documento esté listo (o listo para comentarios), se abre un Pull Request hacia
la rama principal:

1. El otro PM lo revisa y comenta.
2. Se ajusta lo que haga falta.
3. Se aprueba y se une.

El Pull Request es donde queda la conversación: por qué se hizo, qué se discutió, qué se
cambió. Eso vale tanto como el documento.

**Excepción:** correcciones menores de tu propio documento (una fecha, un error de
tipeo, un enlace roto) pueden ir directo. Cualquier cosa que cambie el fondo, va por PR.

## 4. Documentos pequeños, no documentos monstruo

Un documento = un tema. Es preferible tener seis archivos claros que uno de cuarenta
páginas que todos editan al mismo tiempo. Los archivos grandes y compartidos son
justamente los que generan conflictos.

Si un documento empieza a crecer demasiado, se divide y se deja un índice que apunte a
las partes.

## 5. Estados de un documento

Todo documento declara su estado en el encabezado:

| Estado | Significa |
|---|---|
| `borrador` | En construcción. No usar para tomar decisiones. |
| `en revisión` | Terminado por su autor, esperando revisión del otro PM o de Cristian. |
| `aprobado` | Revisado y aprobado. Se puede presentar al cliente. |
| `vigente` | Aprobado y en aplicación en las tiendas. Es la versión que manda. |
| `archivado` | Ya no aplica. Se conserva por historial. |

Un procedimiento **no se aplica en tienda hasta que esté `vigente`**.

## 6. Los PDF y las imágenes van en `recursos/`

Los archivos binarios (PDF, fotos, escaneos, presentaciones) van en
[`recursos/`](../recursos/) y se enlazan desde el documento que los usa.

Motivo: el historial de un PDF no se puede comparar como el de un texto. Si el contenido
lo produjimos nosotros, el documento fuente es el `.md` y el PDF es solo la versión para
entregar.

Los PDF que vienen del cliente o de terceros (facturas, contratos, planos) sí viven
directamente en `recursos/pdf/` como fuente.

## 7. Las decisiones se anotan

Cuando tomemos una decisión que cambie el rumbo de algo (un proceso, una estructura, un
criterio), se deja una nota corta en [`decisiones/`](decisiones/). Dos párrafos bastan:
qué se decidió, por qué, y qué alternativa se descartó.

Dentro de tres meses nadie se va a acordar del motivo. El archivo sí.

## 8. Antes de empezar a editar, actualiza

```bash
git pull origin main
```

La mitad de los conflictos se evitan con esto.
