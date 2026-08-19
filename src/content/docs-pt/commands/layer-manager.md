---
title: LayerManager — Gerencie Todas as Camadas em uma Única Tabela
description: O comando LayerManager abre uma tabela com todas as camadas do desenho, permitindo adicionar camadas e editar diretamente para cada uma o congelamento, o bloqueio, a impressão, a cor, a espessura de linha e o tipo de linha.
keywords: [layer manager, tabela de camadas CAD, gerenciar camadas CAD, adicionar camada CAD, congelar bloquear imprimir camada, kulmanlab gerenciamento de camadas]
group: layer
order: 1
---

# LayerManager

O comando `LayerManager` abre uma tabela listando todas as camadas do desenho, com as configurações **Freeze** (congelar), **Lock** (bloquear), **Plot** (imprimir), **Cor**, **Espessura de linha** e **Tipo de linha** editáveis diretamente na linha. É o local central para adicionar novas camadas e ajustar o comportamento das existentes — os demais comandos de camada ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) fazem, cada um, uma única coisa focada sem precisar abri-lo.

## Abrindo o Gerenciador de Camadas

- Digite `LayerManager` no terminal, **ou**
- Clique no botão **Layer Manager** no painel de camadas.

O diálogo abre como um painel flutuante; nada precisa estar selecionado antes.

## A tabela de camadas

| Coluna | O que controla |
|--------|------------------|
| Name | O nome da camada, exibido apenas para leitura na tabela (definido uma vez, na criação) |
| Freeze | Oculta as entidades da camada e as exclui da seleção até ser descongelada |
| Lock | Impede a edição de entidades na camada, sem ocultá-las |
| Plot | Se as entidades da camada são incluídas ao imprimir ou exportar para PDF |
| Color | A cor ACI da camada — clique na amostra para abrir o seletor de cores |
| Lineweight | A espessura de linha da camada — clique no chip para abrir o seletor de espessura |
| Linetype | O padrão de traços da camada — clique no chip para abrir o seletor de tipo de linha |

Alternar Freeze, Lock ou Plot tem efeito imediato — não há uma etapa de salvamento separada. Entidades definidas como **ByLayer** para cor, espessura de linha ou tipo de linha (o padrão) adotam o que você define aqui; entidades com sua própria substituição explícita não são afetadas.

## Adicionando uma camada

1. Clique em **+ Add Layer** na parte inferior da tabela.
2. Digite um nome e pressione **Enter** para confirmar, ou **Escape** para cancelar.

Nomes de camada podem conter letras, números, espaços e `_`, `-`, `$`. Um nome vazio, já em uso, ou que contenha qualquer outro caractere é rejeitado com um erro em linha, e a linha permanece aberta para outra tentativa.

Novas camadas começam **descongeladas, desbloqueadas, imprimíveis**, com cor 7 (branco/preto), espessura de linha Default e tipo de linha Continuous — os mesmos padrões que [Import](../import/) atribui à camada `0` em um desenho em branco.

## O que você não pode fazer aqui

Não há botão de exclusão — camadas nunca são removidas depois de criadas, apenas congeladas ou deixadas sem uso. A tabela também não indica qual camada é a *atual*; isso é definido pelo menu suspenso do painel de camadas ou por [LayerMakeCurrent](../layer-make-current/), não por este diálogo.

## Referência de teclado

| Tecla | Ação |
|-------|------|
| `Enter` | Confirma o nome de uma nova camada (durante a adição) |
| `Escape` | Cancela a adição de uma camada, ou fecha o diálogo |

## Comandos relacionados

| Comando | O que faz |
|---------|-----------|
| [LayerMakeCurrent](../layer-make-current/) | Define a camada ativa para corresponder à camada da entidade clicada |
| [LayerMatch](../layer-match/) | Reatribui as entidades selecionadas à camada de uma entidade de origem |
| [LayerIsolate](../layer-isolate/) | Congela todas as camadas exceto as das entidades selecionadas |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Descongela todas as camadas de uma vez |
