# 05 — Propuestas

Propuestas formales a Abruzzos y documentos comerciales de Escala Consultores.

**Aprueba: Cristian.** Ninguna propuesta se presenta al cliente sin su visto bueno.

## Qué va aquí

- Propuestas de servicio y de alcance de la consultoría.
- Propuestas de proyecto o de intervención puntual (reestructurar un área, montar un
  proceso, resolver un problema específico).
- Presentaciones a la dirección de Abruzzos.
- Documentos de cierre de alcance y acuerdos.

## Nombres

```
AAAA-MM-DD-propuesta-<tema>.md
```

Ejemplo:

```
2026-09-20-propuesta-reestructuracion-centro-de-produccion.md
```

Usa [`99-plantillas/plantilla-propuesta.md`](../99-plantillas/plantilla-propuesta.md).

## Flujo

1. Se redacta en una rama propia, en `estado: borrador`.
2. Se abre Pull Request. El otro PM la revisa.
3. Cristian la aprueba → pasa a `aprobado`.
4. Se exporta a PDF para entregar. El PDF se guarda en
   [`recursos/pdf/`](../recursos/pdf/) y se enlaza desde la propuesta.
5. El `.md` sigue siendo la fuente. Si cambia, se sube la versión y se exporta de nuevo.

## Lo que hace que una propuesta funcione

Una propuesta se sostiene sobre el problema del cliente, no sobre nuestra lista de
servicios. En orden:

1. **El problema**, dicho en los términos del cliente y con números si los hay.
2. **Qué cuesta no resolverlo.**
3. **Qué proponemos hacer**, concreto.
4. **Qué entregamos**, enumerado.
5. **En cuánto tiempo.**
6. **Qué necesitamos del cliente** para poder hacerlo.
7. **Cuánto cuesta.**

Si el punto 1 está flojo, ninguno de los demás importa.
