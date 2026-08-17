---
title: New File — Start een Lege Tekening in KulmanLab CAD
description: Het New File-commando wist het canvas en opent een nieuwe lege tekening. Er wordt automatisch een eenvoudige bestandsnaam gegenereerd en opgeslagen in browseropslag.
keywords: [nieuw CAD-bestand, nieuwe tekening, leeg canvas CAD, nieuwe tekening online maken, nieuwe DXF starten, KulmanLab nieuw bestand, canvas resetten, tekening wissen]
group: file
order: 2
---

# New File

Het commando **New File** wist het canvas en start een nieuwe lege tekening. Er wordt automatisch een unieke bestandsnaam gegenereerd.

## Een nieuw bestand maken

Klik op de **New File**-werkbalkknop (nieuwe-paginaicoon) in het Bestand-paneel. Het canvas wordt onmiddellijk gewist — zonder prompts of bevestigingsvensters.

## Wat het nieuwe bestand bevat

Een nieuw aangemaakt bestand begint met:

- **Geen entiteiten** op het canvas.
- **Eén standaardlaag** genaamd `0` met kleur wit en lijntype `Continuous`.
- Een **gegenereerde bestandsnaam**, `kulman.dxf` — of `kulman (2).dxf`, `kulman (3).dxf`, … als die naam al bezet is.

Het bestand wordt automatisch opgeslagen in browseropslag en verschijnt in [File Manager](../file-manager/), en kan op elk moment worden [hernoemd](../file-manager/#een-bestand-hernoemen).

## Waarschuwing — niet-opgeslagen werk gaat verloren

Klikken op **New File** verwijdert alle entiteiten op het huidige canvas zonder waarschuwing. Als u de huidige tekening wilt behouden, [exporteer](../export-manager/) deze dan eerst.

## Wanneer New File versus Import gebruiken

| Situatie | Aanbevolen actie |
|-----------|-------------------|
| Een tekening vanaf nul beginnen | **New File** |
| Een bestaand DXF- of JSON-bestand openen | [Import](../import/) |
| Een tekening kopiëren om aan een variant te werken | [Exporteer](../export-manager/) het huidige bestand, en [importeer](../import/) daarna de kopie |

## Gerelateerde commando's

- [Import](../import/) — een bestaande DXF- of JSON-tekening openen
- [Export Manager](../export-manager/) — de tekening downloaden voordat u opnieuw begint
- [File Manager](../file-manager/) — een eerdere tekening herstellen uit browseropslag
