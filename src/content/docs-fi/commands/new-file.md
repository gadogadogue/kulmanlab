---
title: New File — Aloita Tyhjä Piirustus KulmanLab CAD:issa
description: New File -komento tyhjentää piirtoalueen ja avaa uuden, tyhjän piirustuksen. Yksinkertainen tiedostonimi luodaan automaattisesti ja tallennetaan selaimen tallennustilaan.
keywords: [uusi CAD-tiedosto, uusi piirustus, tyhjä piirtoalue CAD, luo uusi piirustus verkossa, aloita uusi DXF, KulmanLab uusi tiedosto, nollaa piirtoalue, tyhjennä piirustus]
group: file
order: 2
---

# New File

Komento **New File** tyhjentää piirtoalueen ja aloittaa uuden, tyhjän piirustuksen. Ainutlaatuinen tiedostonimi luodaan automaattisesti.

## Näin luot uuden tiedoston

Napsauta **New File**-painiketta (uusi sivu -kuvake) File-paneelissa. Piirtoalue tyhjenee välittömästi — ei kehotteita tai vahvistusvalintaikkunoita.

## Mitä uusi tiedosto sisältää

Vasta luotu tiedosto alkaa seuraavilla:

- **Ei entiteettejä** piirtoalueella.
- **Yksi oletustaso** nimeltä `0` valkoisella värillä ja linetyypillä `Continuous`.
- **Luotu tiedostonimi**, `kulman.dxf` — tai `kulman (2).dxf`, `kulman (3).dxf`, … jos nimi on jo käytössä.

Tiedosto tallennetaan automaattisesti selaimen tallennustilaan ja näkyy [File Managerissa](../file-manager/), ja sen voi [nimetä uudelleen](../file-manager/#tiedoston-uudelleennimeäminen) milloin tahansa.

## Varoitus — tallentamaton työ hylätään

**New File**-painikkeen napsauttaminen hylkää kaikki nykyisen piirtoalueen entiteetit ilman varoitusta. Jos haluat säilyttää nykyisen piirustuksen, [vie](../export-manager/) se ensin.

## Milloin käyttää New Filea vs Importia

| Tilanne | Suositeltu toimenpide |
|-----------|-------------------|
| Piirustuksen aloittaminen alusta | **New File** |
| Olemassa olevan DXF- tai JSON-tiedoston avaaminen | [Import](../import/) |
| Piirustuksen kopioiminen variaation työstämiseksi | [Vie](../export-manager/) nykyinen tiedosto, [tuo](../import/) sitten kopio |

## Liittyvät komennot

- [Import](../import/) — avaa olemassa oleva DXF- tai JSON-piirustus
- [Export Manager](../export-manager/) — lataa piirustus ennen alusta aloittamista
- [File Manager](../file-manager/) — palauta aiempi piirustus selaimen tallennustilasta
