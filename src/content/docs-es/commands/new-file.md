---
title: New File — Iniciar un dibujo en blanco en KulmanLab CAD
description: El comando New File limpia el lienzo y abre un nuevo dibujo en blanco. Se genera automáticamente un nombre de archivo con marca de tiempo y se guarda en el almacenamiento del navegador.
keywords: [nuevo archivo CAD, nuevo dibujo, lienzo en blanco CAD, crear nuevo dibujo en línea, iniciar nuevo DXF, nuevo archivo KulmanLab, restablecer lienzo, limpiar dibujo]
group: file
order: 2
---

# New File

El comando **New File** limpia el lienzo y comienza un nuevo dibujo en blanco. Se genera automáticamente un nombre de archivo único con una marca de tiempo.

## Cómo crear un nuevo archivo

Haz clic en el botón **New File** de la barra de herramientas (icono de página nueva) en el panel File. El lienzo se limpia de inmediato — sin indicaciones ni diálogos de confirmación.

## Qué contiene el nuevo archivo

Un archivo recién creado comienza con:

- **Sin entidades** en el lienzo.
- **Una capa predeterminada** llamada `0` con color blanco y tipo de línea `Continuous`.
- Un **nombre de archivo generado**, `kulman.dxf` — o `kulman (2).dxf`, `kulman (3).dxf`, … si ese nombre ya está en uso.

El archivo se guarda automáticamente en el almacenamiento del navegador y aparece en el [File Manager](../file-manager/), y se puede [renombrar](../file-manager/#renombrar-un-archivo) en cualquier momento.

## Advertencia — el trabajo no guardado se descarta

Hacer clic en **New File** descarta todas las entidades del lienzo actual sin advertencia. Si deseas conservar el dibujo actual, [expórtalo](../export-manager/) primero.

## Cuándo usar New File vs Import

| Situación | Acción recomendada |
|-----------|-------------------|
| Comenzar un dibujo desde cero | **New File** |
| Abrir un archivo DXF o JSON existente | [Import](../import/) |
| Copiar un dibujo para trabajar en una variante | [Exporta](../export-manager/) el archivo actual, luego [importa](../import/) la copia |

## Comandos relacionados

- [Import](../import/) — abrir un dibujo DXF o JSON existente
- [Export Manager](../export-manager/) — descargar el dibujo antes de comenzar uno nuevo
- [File Manager](../file-manager/) — restaurar un dibujo anterior desde el almacenamiento del navegador
