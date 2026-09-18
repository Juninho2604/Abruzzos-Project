# Contexto para Claude

Este repositorio es **documental, no de código**. Es el espacio de trabajo de Escala
Consultores para el proyecto de Abruzzos, una cadena de pizzerías en Venezuela en proceso
de expansión.

No hay que compilar, ni probar, ni desplegar nada. Lo que se produce aquí son documentos:
procedimientos, planes, propuestas, informes y reportes que van a ser usados por personas
que trabajan en tiendas y en una consultoría.

## Antes de escribir cualquier cosa

Lee estos tres documentos. Contienen las reglas que rigen todo lo demás:

- [`00-gobernanza/roles-y-responsabilidades.md`](00-gobernanza/roles-y-responsabilidades.md) — quién hace qué.
- [`00-gobernanza/forma-de-trabajo.md`](00-gobernanza/forma-de-trabajo.md) — cómo se sube el trabajo.
- [`00-gobernanza/convenciones.md`](00-gobernanza/convenciones.md) — nombres de archivo y encabezados.

## Reglas de este repositorio

1. **Todo en español**, incluidos los mensajes de commit y los nombres de rama.
2. **Todo documento lleva encabezado** con `titulo`, `area`, `responsable`, `estado`,
   `version` y `actualizado`. Sin excepción.
3. **Nombres de archivo** en minúsculas, sin acentos, sin espacios, con guiones. Los
   documentos con fecha llevan `AAAA-MM-DD` delante.
4. **Cada carpeta tiene un responsable.** Operaciones es de Omar, Auditoría y Control es de
   Adalberto. No modificar documentos de un área sin que su responsable lo sepa.
5. **Usar las plantillas** de [`99-plantillas/`](99-plantillas/) cuando exista una para lo
   que se está creando.
6. **Los PDF y las imágenes** van en [`recursos/`](recursos/) y se enlazan.
7. **Ramas:** `<persona>/<tema-corto>`. Nunca trabajar directo sobre la rama principal.

## Cómo escribir aquí

El destinatario de estos documentos es un gerente de tienda, un pizzero o un auditor —
no un lector técnico. Eso condiciona la forma:

- **Concreto y verificable.** "Mantener limpia el área" no se puede supervisar; "limpiar y
  sanitizar la mesa de armado al cierre de cada turno" sí.
- **Con responsable y momento.** Quién hace cada cosa y cuándo.
- **Corto.** Un documento por tema. Si pasa de dos páginas, probablemente son dos
  documentos.
- **Sin relleno.** Una tabla vale más que tres párrafos de introducción.

## Lo que no se debe hacer

- **No inventar datos del negocio.** Si no se sabe el número de tiendas, el nombre de un
  gerente, una cifra de venta o una fecha, se deja marcado como `_(por completar)_` o como
  `> **Por completar:**`. Un dato inventado en un procedimiento operativo termina aplicado
  en una tienda real.
- **No cargar datos personales** del personal de Abruzzos: cédulas, datos de contacto,
  información médica o de nómina. Aquí se manejan cargos, dotación y desempeño operativo.
- **No marcar un documento como `vigente`** por iniciativa propia. Ese estado significa que
  se está aplicando en las tiendas, y lo decide el responsable del área.
- **No convertir el repositorio en depósito de archivos pesados.** Si algo pasa de ~25 MB,
  va a la nube y se enlaza.

## Estados de documento

`borrador` → `en revisión` → `aprobado` → `vigente` → `archivado`

Un procedimiento no se aplica en tienda hasta que esté `vigente`.
