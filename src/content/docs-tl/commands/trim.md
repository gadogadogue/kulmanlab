---
title: "Trim — Putulin ang Segment sa mga Intersection"
description: "Tinatanggal ng Trim command ang bahagi ng Line, Arc, Circle, Ellipse, Polyline, o Spline sa pagitan ng dalawang magkatabing intersection point na pinakamalapit sa cursor. Ipinapakita ng preview kung aling segment ang puputulin bago ka mag-click."
keywords: [CAD trim command, putulin ang linya CAD, putulin ang bilog CAD, putulin ang arc CAD, putulin ang ellipse CAD, putulin ang polyline CAD, putulin ang spline CAD, cut line intersection, hover trim preview, kulmanlab]
group: edit
order: 8
---

# Trim

Tinatanggal ng `trim` command ang bahagi ng [Line](../line/), [Arc](../arc/), [Circle](../circle/), [Ellipse](../ellipse/), [Polyline](../polyline/), o Spline na nasa pagitan ng dalawang magkatabing intersection point, hinahati ang entity sa isa o higit pang natitirang bahagi. Ang segment na puputulin ay tinutukoy ng posisyon ng cursor — mag-hover sa bahaging gusto mong tanggalin at mag-click para i-trim ito.

## Pag-trim ng isang entity

1. I-type ang `trim` sa terminal o i-click ang **Trim** button sa toolbar.
2. **Mag-hover sa segment** na gusto mong tanggalin — hinihighlight ng preview nang eksakto ang bahaging puputulin.
3. **Mag-click** para tanggalin ang segment na iyon.

Nananatiling aktibo ang command pagkatapos ng bawat trim, kaya puwede kang magpatuloy sa pag-hover at pag-click para putulin pa ang ibang segment — sa parehong entity o sa iba. Pindutin ang **Escape** para lumabas.

```
  Before:                     After trimming middle segment:

  ──────●──────●──────        ──────●          ●──────
      intersect  intersect       (left part)  (right part)
                                 (middle segment removed)
```

## Paano tinutukoy ang trim segment

Nag-p-project ang command ng posisyon ng cursor papunta sa hino-hover na entity at hinahanap ang lahat ng intersection point ng entity na iyon sa ibang mga entity. Hinahati ng mga intersection na ito ang entity sa mga segment — para sa isang Line, Arc, bukas na Polyline, o Spline, ang sariling endpoint ng entity ang siyang gumaganap bilang karagdagang fixed boundary. Ang isang kumpletong Circle o Ellipse, o isang saradong Polyline (kasama ang Rectangle), ay walang sariling endpoint, kaya kailangan ng hindi bababa sa dalawang intersection point bago ito ma-trim. Ang segment na ang interval ay naglalaman ng projection ng cursor ang hinihighlight at tatanggalin sa pag-click.

- **Line, Arc, bukas na Polyline, at Spline** — ang tatanggaling segment ay maaaring ang naunang bahagi (bago ang unang intersection), ang gitnang bahagi (sa pagitan ng dalawang intersection, hinahati ang entity sa dalawa), o ang huling bahagi (pagkatapos ng huling intersection).
- **Circle, Ellipse, at saradong Polyline/Rectangle** — dahil walang fixed na simula o wakas, ang arc lang sa pagitan ng dalawang *intersection point* ang puwedeng tanggalin. Kung mas kaunti sa dalawa ang intersection, walang ipapakitang preview at walang mangyayari sa pag-click. Ang natitirang bahagi ng hugis ang magiging tanging natitirang bahagi.

## Ano ang resulta ng pag-trim

| Entity | Resulta pagkatapos ma-trim |
|--------|------------------------|
| Line | Hanggang dalawang mas maikling Line entity |
| Arc | Hanggang dalawang mas maikling Arc entity |
| Circle | Isang [Arc](../arc/) entity — mawawala ang saradong hugis ng circle, kaya nakaimbak ang natitirang bahagi bilang arc |
| Ellipse | Isang Ellipse entity na may starting at ending angle — nananatiling Ellipse ang natitirang bahagi, pero ngayon ay bahagi na lang |
| Polyline (bukas) | Hanggang dalawang mas maikling Polyline entity |
| Polyline (sarado) / Rectangle | Isang bukas na Polyline entity — mawawala ang saradong hugis, kaya nakaimbak ang natitirang bahagi bilang bukas |
| Spline | Hanggang dalawang mas maikling Spline entity, muling in-fit mula sa mga sampol na punto sa kahabaan ng orihinal na curve |

## Keyboard reference

| Key | Aksyon |
|-----|--------|
| `Escape` | Lumabas sa trim mode |

## Mga suportadong entity

| Entity | Puwede bang i-trim? |
|--------|----------------|
| Line | Oo |
| Arc | Oo |
| Circle | Oo — kailangan ng 2 o higit pang intersection point |
| Ellipse | Oo — kailangan ng 2 o higit pang intersection point |
| Polyline (bukas) | Oo |
| Polyline (sarado) / Rectangle | Oo — kailangan ng 2 o higit pang intersection point |
| Spline | Oo |
| Text, Dimension, Leader | Hindi |

Ang mga entity na ginagamit bilang **cutting boundary** ay puwedeng Line, Arc, Circle, Ellipse, Polyline, o Spline. Hindi kailanman nagre-register ng intersection ang mga entity na Text, Dimension, at Leader, kaya hindi rin sila puwedeng maging boundary.

## Trim vs Extend

| | Trim | Extend |
|---|------|--------|
| Ano ang ginagawa | Tinatanggal ang segment ng isang entity | Iniuunat ang endpoint ng linya papunta sa isang boundary |
| Trigger | Mag-hover sa segment na puputulin | Mag-hover malapit sa endpoint para i-extend |
| Resulta | Nahahati o napapaikli ang entity | Gumagalaw ang endpoint ng linya papunta sa boundary |
| Mga suportadong entity | Line, Arc, Circle, Ellipse, Polyline, Spline | Line lang |
