---
title: LayerManager — Gestionar todas las capas en una sola tabla
description: El comando LayerManager abre una tabla con todas las capas del dibujo, permitiéndote añadir capas y editar directamente para cada una la congelación, el bloqueo, el trazado, el color, el grosor de línea y el tipo de línea.
keywords: [layer manager, tabla de capas CAD, gestionar capas CAD, añadir capa CAD, congelar bloquear trazar capa, gestión de capas kulmanlab]
group: layer
order: 1
---

# LayerManager

El comando `LayerManager` abre una tabla que enumera todas las capas del dibujo, con los ajustes **Freeze** (congelar), **Lock** (bloquear), **Plot** (trazar), **Color**, **Grosor de línea** y **Tipo de línea** editables directamente en la fila. Es el lugar central para añadir capas nuevas y ajustar el comportamiento de las existentes — los demás comandos de capa ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) hacen cada uno una tarea concreta sin necesidad de abrirlo.

## Abrir el Administrador de Capas

- Escribe `LayerManager` en el terminal, **o**
- Haz clic en el botón **Layer Manager** del panel de capas.

El diálogo se abre como un panel flotante; no es necesario seleccionar nada antes.

## La tabla de capas

| Columna | Qué controla |
|---------|---------------|
| Name | El nombre de la capa, mostrado de solo lectura en la tabla (se establece una vez, al crearla) |
| Freeze | Oculta las entidades de la capa y las excluye de la selección hasta que se descongele |
| Lock | Impide editar las entidades de la capa, sin ocultarlas |
| Plot | Si las entidades de la capa se incluyen al imprimir o exportar a PDF |
| Color | El color ACI de la capa — haz clic en la muestra para abrir el selector de color |
| Lineweight | El grosor de línea de la capa — haz clic en el chip para abrir el selector de grosor |
| Linetype | El patrón de trazos de la capa — haz clic en el chip para abrir el selector de tipo de línea |

Activar o desactivar Freeze, Lock o Plot tiene efecto inmediato — no hay un paso de guardado aparte. Las entidades con color, grosor de línea o tipo de línea en **ByLayer** (el valor predeterminado) toman lo que configures aquí; las entidades con su propia anulación explícita no se ven afectadas.

## Añadir una capa

1. Haz clic en **+ Add Layer** al final de la tabla.
2. Escribe un nombre y pulsa **Enter** para confirmar, o **Escape** para cancelar.

Los nombres de capa pueden contener letras, números, espacios y `_`, `-`, `$`. Un nombre vacío, ya en uso, o con cualquier otro carácter se rechaza con un error en línea, y la fila permanece abierta para otro intento.

Las capas nuevas empiezan **descongeladas, desbloqueadas, trazables**, con color 7 (blanco/negro), grosor de línea Default y tipo de línea Continuous — los mismos valores que [Import](../import/) asigna a la capa `0` en un dibujo en blanco.

## Lo que no puedes hacer aquí

No hay botón de eliminar — las capas nunca se eliminan una vez creadas, solo se pueden congelar o dejar sin usar. La tabla tampoco indica cuál capa es la *actual*; eso se establece desde el menú desplegable del panel de capas o con [LayerMakeCurrent](../layer-make-current/), no desde este diálogo.

## Referencia de teclado

| Tecla | Acción |
|-----|--------|
| `Enter` | Confirmar el nombre de una capa nueva (mientras se añade) |
| `Escape` | Cancelar la adición de una capa, o cerrar el diálogo |

## Comandos relacionados

| Comando | Qué hace |
|---------|----------|
| [LayerMakeCurrent](../layer-make-current/) | Establece la capa actual para que coincida con la capa de una entidad seleccionada |
| [LayerMatch](../layer-match/) | Reasigna las entidades seleccionadas para que coincidan con la capa de una entidad origen |
| [LayerIsolate](../layer-isolate/) | Congela todas las capas excepto las de las entidades seleccionadas |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Descongela todas las capas en un solo paso |
