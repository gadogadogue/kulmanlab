---
title: LayerManager — Gérer tous les calques dans un seul tableau
description: La commande LayerManager ouvre un tableau de tous les calques du dessin, permettant d'ajouter des calques et de modifier directement pour chacun le gel, le verrouillage, le tracé, la couleur, l'épaisseur de ligne et le type de ligne.
keywords: [layer manager, tableau des calques CAO, gérer les calques CAO, ajouter un calque CAO, geler verrouiller tracer calque, gestion calques kulmanlab]
group: layer
order: 1
---

# LayerManager

La commande `LayerManager` ouvre un tableau listant tous les calques du dessin, avec les réglages **Freeze** (gel), **Lock** (verrouillage), **Plot** (tracé), **Couleur**, **Épaisseur de ligne** et **Type de ligne** modifiables directement dans la ligne. C'est l'endroit central pour ajouter de nouveaux calques et ajuster le comportement des calques existants — les autres commandes de calque ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) accomplissent chacune une tâche précise sans l'ouvrir.

## Ouvrir le Gestionnaire de Calques

- Tapez `LayerManager` dans le terminal, **ou**
- Cliquez sur le bouton **Layer Manager** dans le panneau des calques.

La boîte de dialogue s'ouvre comme un panneau flottant ; rien n'a besoin d'être sélectionné au préalable.

## Le tableau des calques

| Colonne | Ce qu'elle contrôle |
|---------|----------------------|
| Name | Le nom du calque, affiché en lecture seule dans le tableau (défini une seule fois, à la création) |
| Freeze | Masque les entités du calque et les exclut de la sélection jusqu'à ce qu'il soit dégelé |
| Lock | Empêche la modification des entités sur le calque, sans les masquer |
| Plot | Si les entités du calque sont incluses lors de l'impression ou de l'export en PDF |
| Color | La couleur ACI du calque — cliquez sur la pastille pour ouvrir le sélecteur de couleur |
| Lineweight | L'épaisseur de ligne du calque — cliquez sur la puce pour ouvrir le sélecteur d'épaisseur |
| Linetype | Le motif de tirets du calque — cliquez sur la puce pour ouvrir le sélecteur de type de ligne |

Basculer Freeze, Lock ou Plot prend effet immédiatement — il n'y a pas d'étape de sauvegarde séparée. Les entités réglées sur **ByLayer** pour la couleur, l'épaisseur de ligne ou le type de ligne (le réglage par défaut) reprennent ce que vous définissez ici ; les entités ayant leur propre substitution explicite ne sont pas affectées.

## Ajouter un calque

1. Cliquez sur **+ Add Layer** en bas du tableau.
2. Tapez un nom et appuyez sur **Entrée** pour confirmer, ou **Échap** pour annuler.

Les noms de calque peuvent contenir des lettres, des chiffres, des espaces, et `_`, `-`, `$`. Un nom vide, déjà utilisé, ou contenant tout autre caractère est rejeté avec une erreur affichée en ligne, et la ligne reste ouverte pour un nouvel essai.

Les nouveaux calques démarrent **dégelés, déverrouillés, traçables**, avec la couleur 7 (blanc/noir), l'épaisseur de ligne Default et le type de ligne Continuous — les mêmes réglages que [Import](../import/) attribue au calque `0` dans un dessin vide.

## Ce que vous ne pouvez pas faire ici

Il n'y a pas de bouton de suppression — les calques ne sont jamais supprimés une fois créés, seulement gelés ou laissés inutilisés. Le tableau n'indique pas non plus quel calque est *courant* ; cela se règle depuis le menu déroulant du panneau des calques ou via [LayerMakeCurrent](../layer-make-current/), pas depuis cette boîte de dialogue.

## Référence clavier

| Touche | Action |
|--------|--------|
| `Entrée` | Confirmer le nom d'un nouveau calque (pendant la saisie) |
| `Échap` | Annuler l'ajout d'un calque, ou fermer la boîte de dialogue |

## Commandes associées

| Commande | Ce qu'elle fait |
|----------|----------------|
| [LayerMakeCurrent](../layer-make-current/) | Définit le calque actif pour qu'il corresponde au calque de l'entité cliquée |
| [LayerMatch](../layer-match/) | Réassigne les entités sélectionnées au calque d'une entité source |
| [LayerIsolate](../layer-isolate/) | Gèle tous les calques sauf ceux des entités sélectionnées |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Dégèle tous les calques en une seule étape |
