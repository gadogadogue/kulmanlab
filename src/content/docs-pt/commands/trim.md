---
title: Comando Trim — Cortar Segmentos em Interseções
description: O comando Trim remove a porção de uma Line, Arc, Circle, Ellipse, Polyline ou Spline entre dois pontos de interseção adjacentes mais próximos ao cursor. Uma prévia mostra exatamente qual segmento será cortado antes de clicar.
keywords: [CAD comando trim, cortar linha CAD, cortar círculo CAD, cortar arco CAD, cortar elipse CAD, cortar polilinha CAD, cortar spline CAD, cortar linha interseção, prévia trim hover, kulmanlab]
group: edit
order: 8
---

# Trim

O comando `trim` remove a porção de uma [Line](../line/), [Arc](../arc/), [Circle](../circle/), [Ellipse](../ellipse/), [Polyline](../polyline/) ou Spline que fica entre dois pontos de interseção adjacentes, dividindo a entidade em uma ou mais partes restantes. O segmento a cortar é determinado pela posição do cursor — passe sobre a parte que deseja remover e clique para cortar.

## Cortando uma entidade

1. Digite `trim` no terminal ou clique no botão **Trim** na barra de ferramentas.
2. **Passe o cursor sobre o segmento** que deseja remover — uma prévia destaca exatamente a porção que será cortada.
3. **Clique** para remover esse segmento.

O comando permanece ativo após cada corte, então você pode continuar passando o cursor e clicando para cortar mais segmentos — na mesma entidade ou em outra. Pressione **Escape** para sair.

```
  Antes:                         Após cortar segmento central:

  ──────●──────●──────           ──────●          ●──────
      intersec  intersec             (parte esquerda)  (parte direita)
                                     (segmento central removido)
```

## Como o segmento a cortar é determinado

O comando projeta a posição do cursor na entidade passada e encontra todos os pontos de interseção que ela tem com outras entidades. Essas interseções dividem a entidade em segmentos — em uma Line, Arc, Polyline aberta ou Spline, os próprios extremos da entidade atuam como limites fixos adicionais. Um Circle ou uma Ellipse completos, ou uma Polyline fechada (incluindo um Retângulo), não têm extremos próprios, então são necessários pelo menos dois pontos de interseção antes que possam ser cortados. O segmento cujo intervalo contém a projeção do cursor é destacado e será removido ao clicar.

- **Line, Arc, Polyline aberta e Spline** — o segmento removido pode ser a porção inicial (antes da primeira interseção), uma porção central (entre duas interseções, dividindo a entidade em duas partes), ou a porção final (após a última interseção).
- **Circle, Ellipse e Polyline fechada/Retângulo** — como não há um início ou fim fixo, apenas o arco entre dois *pontos de interseção* pode ser removido. Com menos de duas interseções, nenhuma prévia aparece e clicar não faz nada. O resto da forma se torna a única parte restante.

## O que o corte produz

| Entidade | Resultado após o corte |
|--------|------------------------|
| Line | Até duas entidades Line mais curtas |
| Arc | Até duas entidades Arc mais curtas |
| Circle | Uma entidade [Arc](../arc/) — a forma fechada do círculo desaparece, então a parte restante é armazenada como arco |
| Ellipse | Uma entidade Ellipse com ângulo inicial e final — a parte restante continua sendo uma Ellipse, agora parcial |
| Polyline (aberta) | Até duas entidades Polyline mais curtas |
| Polyline (fechada) / Retângulo | Uma entidade Polyline aberta — a forma fechada desaparece, então a parte restante é armazenada aberta |
| Spline | Até duas entidades Spline mais curtas, recalculadas a partir de pontos amostrados ao longo da curva original |

## Referência de teclado

| Tecla | Ação |
|-------|------|
| `Escape` | Sai do modo trim |

## Entidades suportadas

| Entidade | Pode ser cortada? |
|----------|------------------|
| Line | Sim |
| Arc | Sim |
| Circle | Sim — requer 2 ou mais pontos de interseção |
| Ellipse | Sim — requer 2 ou mais pontos de interseção |
| Polyline (aberta) | Sim |
| Polyline (fechada) / Retângulo | Sim — requer 2 ou mais pontos de interseção |
| Spline | Sim |
| Texto, Cota, Leader | Não |

As entidades usadas como **bordas de corte** podem ser uma Line, Arc, Circle, Ellipse, Polyline ou Spline. Entidades de Texto, Cota e Leader nunca registram interseções, então também não podem atuar como bordas.

## Trim vs Extend

| | Trim | Extend |
|---|------|--------|
| O que faz | Remove um segmento de uma entidade | Estica um endpoint de uma linha até uma borda |
| Trigger | Passe o cursor sobre o segmento a cortar | Passe o cursor próximo ao endpoint a estender |
| Resultado | A entidade se divide ou encurta | O endpoint da linha se move até a borda |
| Entidades suportadas | Line, Arc, Circle, Ellipse, Polyline, Spline | Apenas Line |
