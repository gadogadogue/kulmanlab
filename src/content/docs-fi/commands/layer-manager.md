---
title: LayerManager — Hallitse Kaikkia Tasoja Yhdessä Taulukossa
description: LayerManager-komento avaa taulukon piirustuksen kaikista tasoista, jonka avulla voit lisätä tasoja ja muokata suoraan kunkin tason jäädytystä, lukitusta, tulostusta, väriä, viivanpaksuutta ja viivatyyppiä.
keywords: [layer manager, CAD tasotaulukko, hallitse tasoja CAD, lisää taso CAD, jäädytä lukitse tulosta taso, kulmanlab tasojen hallinta]
group: layer
order: 1
---

# LayerManager

Komento `LayerManager` avaa taulukon, jossa luetellaan piirustuksen kaikki tasot ja jonka **Freeze** (jäädytys), **Lock** (lukitus), **Plot** (tulostus), **väri**, **viivanpaksuus** ja **viivatyyppi** ovat muokattavissa suoraan rivillä. Se on keskeinen paikka uusien tasojen lisäämiseen ja olemassa olevien tasojen käyttäytymisen säätämiseen — muut tasokomennot ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) tekevät kukin yhden kohdennetun asian avaamatta sitä.

## Layer Managerin avaaminen

- Kirjoita `LayerManager` terminaaliin, **tai**
- Napsauta **Layer Manager**-painiketta tasopaneelissa.

Valintaikkuna avautuu kelluvana paneelina; mitään ei tarvitse valita etukäteen.

## Tasotaulukko

| Sarake | Mitä se hallitsee |
|--------|----------------------|
| Name | Tason nimi, näytetään taulukossa vain luku -tilassa (asetetaan kerran, luontihetkellä) |
| Freeze | Piilottaa tason entiteetit ja sulkee ne pois valinnasta, kunnes jäädytys poistetaan |
| Lock | Estää tason entiteettien muokkaamisen piilottamatta niitä |
| Plot | Sisällytetäänkö tason entiteetit tulostukseen tai PDF-vientiin |
| Color | Tason ACI-väri — napsauta väriruutua avataksesi värivalitsimen |
| Lineweight | Tason viivanpaksuus — napsauta chipiä avataksesi viivanpaksuusvalitsimen |
| Linetype | Tason viivakuvio — napsauta chipiä avataksesi viivatyyppivalitsimen |

Freezen, Lockin tai Plotin vaihtaminen vaikuttaa välittömästi — erillistä tallennusvaihetta ei ole. Entiteetit, joiden väri, viivanpaksuus tai viivatyyppi on asetettu arvoon **ByLayer** (oletusarvo), noudattavat tässä asetettua; entiteetit, joilla on oma eksplisiittinen ohitus, eivät muutu.

## Tason lisääminen

1. Napsauta **+ Add Layer** taulukon alareunassa.
2. Kirjoita nimi ja paina **Enter** vahvistaaksesi, tai **Escape** peruuttaaksesi.

Tason nimet voivat sisältää kirjaimia, numeroita, välilyöntejä sekä merkkejä `_`, `-`, `$`. Tyhjä, jo käytössä oleva tai muita merkkejä sisältävä nimi hylätään rivin sisäisellä virheilmoituksella, ja rivi jää auki uutta yritystä varten.

Uudet tasot alkavat **jäädyttämättöminä, lukitsemattomina, tulostettavina**, värillä 7 (valkoinen/musta), viivanpaksuudella Default ja viivatyypillä Continuous — samat oletusarvot, jotka [Import](../import/) antaa tasolle `0` tyhjässä piirustuksessa.

## Mitä tässä ei voi tehdä

Poistopainiketta ei ole — tasoja ei koskaan poisteta luomisen jälkeen, ne voi vain jäädyttää tai jättää käyttämättä. Taulukko ei myöskään näytä, mikä taso on *nykyinen*; se asetetaan tasopaneelin pudotusvalikosta tai [LayerMakeCurrent](../layer-make-current/)-komennolla, ei tästä valintaikkunasta.

## Näppäinreferenssi

| Näppäin | Toiminto |
|---------|----------|
| `Enter` | Vahvista uuden tason nimi (lisäyksen aikana) |
| `Escape` | Peruuta tason lisääminen, tai sulje valintaikkuna |

## Liittyvät komennot

| Komento | Mitä se tekee |
|---------|-------------|
| [LayerMakeCurrent](../layer-make-current/) | Aseta nykyinen taso vastaamaan napsautetun entiteetin tasoa |
| [LayerMatch](../layer-match/) | Kohdista valitut entiteetit uudelleen lähdeentiteetin tasolle |
| [LayerIsolate](../layer-isolate/) | Jäädytä kaikki tasot paitsi valittujen entiteettien tasot |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Poista kaikkien tasojen jäädytys yhdellä kertaa |
