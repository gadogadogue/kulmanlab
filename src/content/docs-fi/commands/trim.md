---
title: Trim-komento — Leikkaa segmenttejä leikkauspisteistä
description: Trim-komento poistaa sen osan Line-, Arc-, Circle-, Ellipse-, Polyline- tai Spline-entiteetistä, joka sijaitsee kahden vierekkäisen leikkauspisteen välillä lähinnä kohdistinta. Esikatselu näyttää tarkalleen, mikä segmentti leikataan ennen napsautusta.
keywords: [CAD trim-komento, leikkaa viiva CAD, leikkaa ympyrä CAD, leikkaa kaari CAD, leikkaa ellipsi CAD, leikkaa polyline CAD, leikkaa spline CAD, leikkaa viivan risteys, hover trim -esikatselu, kulmanlab]
group: edit
order: 8
---

# Trim

Komento `trim` poistaa sen osan [Line](../line/)-, [Arc](../arc/)-, [Circle](../circle/)-, [Ellipse](../ellipse/)-, [Polyline](../polyline/)- tai Spline-entiteetistä, joka sijaitsee kahden vierekkäisen leikkauspisteen välillä, jakaen entiteetin yhteen tai useampaan jäljelle jäävään osaan. Leikattava segmentti määräytyy kohdistimen sijainnin mukaan — pidä kohdistinta poistettavan osan päällä ja napsauta leikataksesi sen.

## Entiteetin leikkaaminen

1. Kirjoita `trim` terminaaliin tai napsauta **Trim**-painiketta työkalurivillä.
2. **Pidä kohdistinta poistettavan segmentin päällä** — esikatselu korostaa tarkalleen osan, joka leikataan.
3. **Napsauta** poistaaksesi kyseisen segmentin.

Komento pysyy aktiivisena jokaisen leikkauksen jälkeen, jotta voit jatkaa hoveringia ja napsauttamista leikataksesi lisää segmenttejä — samalla entiteetillä tai toisella. Paina **Escape** poistuaksesi.

```
  Ennen:                        Keskisegmentin leikkaamisen jälkeen:

  ──────●──────●──────        ──────●          ●──────
      risteys  risteys           (vasen osa)  (oikea osa)
                                 (keskisegmentti poistettu)
```

## Miten trim-segmentti määräytyy

Komento projisoi kohdistimen sijainnin entiteetille, jonka päällä se on, ja löytää kaikki leikkauspisteet, jotka entiteetillä on muiden entiteettien kanssa. Nämä leikkauspisteet jakavat entiteetin segmentteihin — Line-, Arc-, avoimella Polyline- tai Spline-entiteetillä sen omat päätepisteet toimivat lisäkiinteinä rajoina. Täydellisellä Circle- tai Ellipse-entiteetillä, tai suljetulla Polyline-entiteetillä (mukaan lukien Rectangle), ei ole omia päätepisteitä, joten sitä ei voi leikata ennen kuin sillä on vähintään kaksi leikkauspistettä. Segmentti, jonka väli sisältää kohdistimen projektion, korostuu ja poistetaan napsautettaessa.

- **Line, Arc, avoin Polyline ja Spline** — poistettava segmentti voi olla johtava osa (ennen ensimmäistä leikkauspistettä), keskiosa (kahden leikkauspisteen välissä, jakaen entiteetin kahtia), tai loppuosa (viimeisen leikkauspisteen jälkeen).
- **Circle, Ellipse ja suljettu Polyline/Rectangle** — koska kiinteää alkua tai loppua ei ole, vain kahden *leikkauspisteen* välinen kaari voidaan poistaa. Jos leikkauspisteitä on vähemmän kuin kaksi, esikatselua ei näytetä eikä napsauttaminen tee mitään. Muodon loppuosasta tulee ainoa jäljelle jäävä osa.

## Mitä leikkaus tuottaa

| Entiteetti | Tulos leikkauksen jälkeen |
|--------|------------------------|
| Line | Enintään kaksi lyhyempää Line-entiteettiä |
| Arc | Enintään kaksi lyhyempää Arc-entiteettiä |
| Circle | Yksi [Arc](../arc/)-entiteetti — ympyrän suljettu muoto katoaa, joten jäljelle jäävä osa tallennetaan kaarena |
| Ellipse | Yksi Ellipse-entiteetti, jolla on alku- ja loppukulma — jäljelle jäävä osa pysyy Ellipse-entiteettinä, nyt osittaisena |
| Polyline (avoin) | Enintään kaksi lyhyempää Polyline-entiteettiä |
| Polyline (suljettu) / Rectangle | Yksi avoin Polyline-entiteetti — suljettu muoto katoaa, joten jäljelle jäävä osa tallennetaan avoimena |
| Spline | Enintään kaksi lyhyempää Spline-entiteettiä, sovitettu uudelleen alkuperäistä käyrää pitkin otetuista näytepisteistä |

## Näppäinreferenssi

| Näppäin | Toiminto |
|-----|--------|
| `Escape` | Poistu trim-tilasta |

## Tuetut entiteetit

| Entiteetti | Voidaanko leikata? |
|--------|----------------|
| Line | Kyllä |
| Arc | Kyllä |
| Circle | Kyllä — vaatii 2 tai useamman leikkauspisteen |
| Ellipse | Kyllä — vaatii 2 tai useamman leikkauspisteen |
| Polyline (avoin) | Kyllä |
| Polyline (suljettu) / Rectangle | Kyllä — vaatii 2 tai useamman leikkauspisteen |
| Spline | Kyllä |
| Text, Dimension, Leader | Ei |

Entiteetit, joita käytetään **leikkausrajoina**, voivat olla Line, Arc, Circle, Ellipse, Polyline tai Spline. Text-, Dimension- ja Leader-entiteetit eivät koskaan rekisteröi leikkauspisteitä, joten nekään eivät voi toimia rajoina.

## Trim vs Extend

| | Trim | Extend |
|---|------|--------|
| Mitä se tekee | Poistaa entiteetin segmentin | Venyttää viivan päätepisteen rajaan |
| Laukaisin | Pidä kohdistinta segmentin päällä leikataksesi | Pidä kohdistinta lähellä päätepistettä jatkaaksesi |
| Tulos | Entiteetti jakautuu tai lyhenee | Viivan päätepiste siirtyy rajaan |
| Tuetut entiteetit | Line, Arc, Circle, Ellipse, Polyline, Spline | Vain Line |
