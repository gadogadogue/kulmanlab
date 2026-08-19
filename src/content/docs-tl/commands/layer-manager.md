---
title: LayerManager — Pamahalaan ang Lahat ng Layer sa Isang Table
description: Binubuksan ng LayerManager command ang table ng lahat ng layer sa drawing, na nagbibigay-daan sa iyong magdagdag ng layer at direktang i-edit ang freeze, lock, plot, kulay, lineweight, at linetype ng bawat isa.
keywords: [layer manager, CAD layer table, pamahalaan ang layer CAD, magdagdag ng layer CAD, freeze lock plot layer, kulmanlab layer management]
group: layer
order: 1
---

# LayerManager

Binubuksan ng `LayerManager` command ang table na naglilista sa lahat ng layer sa drawing, na may mga setting na **Freeze**, **Lock**, **Plot**, **Kulay**, **Lineweight**, at **Linetype** na direktang na-e-edit sa row. Ito ang pangunahing lugar para magdagdag ng bagong layer at i-adjust kung paano kumikilos ang mga existing layer — ginagawa ng ibang layer command ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) ang bawat isa ng isang tiyak na bagay nang hindi ito binubuksan.

## Pagbukas ng Layer Manager

- I-type ang `LayerManager` sa terminal, **o**
- I-click ang **Layer Manager** button sa layer panel.

Bubukas ang dialog bilang lumulutang na panel; walang kailangang piliin muna.

## Ang layer table

| Column | Ano ang kinokontrol nito |
|--------|-----------------------------|
| Name | Ang pangalan ng layer, ipinapakita bilang read-only sa table (itinatakda isang beses, sa paglikha) |
| Freeze | Itinatago ang mga entity ng layer at hindi isinasama sa selection hanggang ma-unfreeze |
| Lock | Pinipigilan ang pag-edit ng mga entity sa layer, nang hindi ito itinatago |
| Plot | Kung isasama ang mga entity ng layer kapag nagprint o nag-export sa PDF |
| Color | Ang ACI color ng layer — i-click ang swatch para buksan ang color picker |
| Lineweight | Ang lineweight ng layer — i-click ang chip para buksan ang lineweight picker |
| Linetype | Ang dash pattern ng layer — i-click ang chip para buksan ang linetype picker |

Agad na may epekto ang pag-toggle ng Freeze, Lock, o Plot — walang hiwalay na save step. Ang mga entity na naka-set sa **ByLayer** para sa kulay, lineweight, o linetype (ang default) ay susunod sa itinakda mo rito; hindi maaapektuhan ang mga entity na may sariling explicit na override.

## Pagdagdag ng layer

1. I-click ang **+ Add Layer** sa ibaba ng table.
2. Mag-type ng pangalan at pindutin ang **Enter** para kumpirmahin, o **Escape** para kanselahin.

Maaaring maglaman ng mga letra, numero, espasyo, at `_`, `-`, `$` ang pangalan ng layer. Tatanggihan ang pangalang blangko, ginagamit na, o may ibang character, kasama ang inline error, at mananatiling bukas ang row para sa isa pang pagsubok.

Ang mga bagong layer ay nagsisimula na **hindi naka-freeze, hindi naka-lock, plottable**, na may kulay 7 (puti/itim), lineweight na Default, at linetype na Continuous — ang parehong default na itinatakda ng [Import](../import/) sa layer `0` sa isang blangkong drawing.

## Ano ang hindi mo magagawa dito

Walang delete button — hindi kailanman inaalis ang mga layer pagkatapos malikha, maaari lang itong i-freeze o hayaang hindi ginagamit. Hindi rin ipinapakita ng table kung aling layer ang *current*; itinatakda iyon mula sa dropdown sa layer panel o sa pamamagitan ng [LayerMakeCurrent](../layer-make-current/), hindi mula sa dialog na ito.

## Keyboard reference

| Key | Aksyon |
|-----|--------|
| `Enter` | Kumpirmahin ang pangalan ng bagong layer (habang nagdaragdag) |
| `Escape` | Kanselahin ang pagdagdag ng layer, o isara ang dialog |

## Kaugnay na commands

| Command | Ano ang ginagawa nito |
|---------|-------------|
| [LayerMakeCurrent](../layer-make-current/) | Itakda ang kasalukuyang layer para tumugma sa layer ng na-click na entity |
| [LayerMatch](../layer-match/) | Baguhin ang layer ng mga napiling entity para tumugma sa layer ng source entity |
| [LayerIsolate](../layer-isolate/) | I-freeze ang lahat ng layer maliban sa mga layer ng napiling entity |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | I-unfreeze ang lahat ng layer sa isang hakbang |
