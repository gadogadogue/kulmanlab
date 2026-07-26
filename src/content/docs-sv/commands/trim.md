---
title: "Trim-kommandot — Klipp segment vid skärningspunkter"
description: "Trim-kommandot tar bort den del av en Line, Arc, Circle, Ellipse, Polyline eller Spline som ligger mellan två intilliggande skärningspunkter närmast markören. Förhandsvisningen visar exakt vilket segment som kommer klippas innan du klickar."
keywords: [CAD trim-kommando, klipp linje CAD, klipp cirkel CAD, klipp båge CAD, klipp ellips CAD, klipp polylinje CAD, klipp spline CAD, klipp linjeskärning, hover trim-förhandsvisning, kulmanlab]
group: edit
order: 8
---

# Trim

`trim`-kommandot tar bort den del av en [Line](../line/), [Arc](../arc/), [Circle](../circle/), [Ellipse](../ellipse/), [Polyline](../polyline/) eller Spline som ligger mellan två intilliggande skärningspunkter, och delar entiteten i en eller flera kvarvarande delar. Vilket segment som klipps bestäms av markörens position — håll markören över den del du vill ta bort och klicka för att klippa den.

## Klippa en entitet

1. Skriv `trim` i terminalen eller klicka på **Trim**-knappen i verktygsfältet.
2. **Håll markören över segmentet** du vill ta bort — en förhandsvisning markerar exakt den del som kommer klippas.
3. **Klicka** för att ta bort det segmentet.

Kommandot förblir aktivt efter varje klippning, så du kan fortsätta hålla markören över och klicka för att klippa fler segment — på samma entitet eller en annan. Tryck **Escape** för att avsluta.

```
  Före:                        Efter att mittsegmentet klippts:

  ──────●──────●──────        ──────●          ●──────
       skärning  skärning       (vänster del)  (höger del)
                                 (mittsegmentet borttaget)
```

## Hur klippsegmentet bestäms

Kommandot projicerar markörens position på den entitet markören befinner sig över och hittar alla skärningspunkter entiteten har med andra entiteter. Dessa skärningar delar upp entiteten i segment — för en Line, Arc, öppen Polyline eller Spline fungerar entitetens egna ändpunkter som ytterligare fasta gränser. En fullständig Circle eller Ellipse, eller en stängd Polyline (inklusive en Rectangle), har inga egna ändpunkter, så minst två skärningspunkter krävs innan den överhuvudtaget kan klippas. Segmentet vars intervall innehåller markörens projektion markeras och tas bort vid klick.

- **Line, Arc, öppen Polyline och Spline** — det borttagna segmentet kan vara den inledande delen (före den första skärningen), en mellersta del (mellan två skärningar, vilket delar entiteten i två), eller den avslutande delen (efter den sista skärningen).
- **Circle, Ellipse och stängd Polyline/Rectangle** — eftersom det inte finns någon fast start eller slut kan endast bågen mellan två *skärningspunkter* tas bort. Med färre än två skärningar visas ingen förhandsvisning och ett klick gör ingenting. Resten av formen blir den enda kvarvarande delen.

## Vad klippningen ger

| Entitet | Resultat efter klippning |
|--------|------------------------|
| Line | Upp till två kortare Line-entiteter |
| Arc | Upp till två kortare Arc-entiteter |
| Circle | En [Arc](../arc/)-entitet — cirkelns slutna form försvinner, så den kvarvarande delen lagras som en båge |
| Ellipse | En Ellipse-entitet med start- och slutvinkel — den kvarvarande delen förblir en Ellipse, nu partiell |
| Polyline (öppen) | Upp till två kortare Polyline-entiteter |
| Polyline (stängd) / Rectangle | En öppen Polyline-entitet — den stängda formen försvinner, så den kvarvarande delen lagras öppen |
| Spline | Upp till två kortare Spline-entiteter, omanpassade från samplade punkter längs originalkurvan |

## Snabbreferens tangentbord

| Tangent | Åtgärd |
|-----|--------|
| `Escape` | Avslutar trim-läget |

## Entiteter som stöds

| Entitet | Kan klippas? |
|--------|----------------|
| Line | Ja |
| Arc | Ja |
| Circle | Ja — kräver 2 eller fler skärningspunkter |
| Ellipse | Ja — kräver 2 eller fler skärningspunkter |
| Polyline (öppen) | Ja |
| Polyline (stängd) / Rectangle | Ja — kräver 2 eller fler skärningspunkter |
| Spline | Ja |
| Text, Dimension, Leader | Nej |

Entiteterna som används som **klippgränser** kan vara Line, Arc, Circle, Ellipse, Polyline eller Spline. Text-, Dimension- och Leader-entiteter registrerar aldrig skärningar, så de kan inte heller fungera som gränser.

## Trim jämfört med Extend

| | Trim | Extend |
|---|------|--------|
| Vad det gör | Tar bort ett segment av en entitet | Sträcker en linjeändpunkt till en gräns |
| Utlösare | Håll markören över segmentet som ska klippas | Håll markören nära ändpunkten som ska förlängas |
| Resultat | Entiteten delas eller kortas av | Linjens ändpunkt flyttas till gränsen |
| Entiteter som stöds | Line, Arc, Circle, Ellipse, Polyline, Spline | Endast Line |
