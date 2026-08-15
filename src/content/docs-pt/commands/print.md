---
title: Comando Print — Exportar o Desenho como PNG, JPEG, WebP ou PDF
description: O comando Print abre o Print Manager — uma janela de exportação dedicada com prévia ao vivo, seletor de formato, opção monocromática e seleção de área opcional. Exporta até 2000×2000 px. Suporta PNG, JPEG, WebP e PDF.
keywords: [CAD exportar PNG, CAD exportar PDF, imprimir desenho CAD, print manager, exportar monocromático, kulmanlab export]
group: file
order: 4
---

# Print

O comando `print` abre o **Print Manager** — uma janela de exportação dedicada com canvas de prévia ao vivo, seletor de formato (PNG / JPEG / WebP / PDF), opção monocromática e recorte de área opcional. Nada é enviado a uma impressora física; a saída é baixada como um arquivo.

## Abrindo o Print Manager

Clique no botão **Print** na barra de ferramentas ou digite `print` no terminal. O Print Manager abre imediatamente mostrando uma prévia do viewport atual.

## Layout do Print Manager

A janela tem dois painéis:
- **Barra lateral esquerda** — todos os controles de exportação.
- **Painel direito** — canvas de prévia ao vivo que atualiza ao mudar as configurações.

### Controles da barra lateral

| Controle | Descrição |
|----------|-----------|
| **Mudar Área** | Recorte para um retângulo personalizado no canvas (veja abaixo) |
| **Monocromático** (ativar/desativar) | Converte todas as linhas coloridas para preto — ativado por padrão para saída de impressão limpa |
| **Formato** (menu suspenso) | PNG, JPEG, WebP ou PDF |
| **Exportar** (botão) | Gera e baixa o arquivo |

## Qualidade e resolução

O menu suspenso **Qualidade** define o DPI no qual a exportação é renderizada: Rascunho (72), Normal (150, padrão), Apresentação (300) ou Máxima (600). Uma Qualidade mais alta produz uma imagem maior e mais nítida no mesmo tamanho físico — as espessuras de linha aumentam junto com a resolução, então uma linha mantém a mesma espessura física no papel em qualquer configuração de Qualidade. A única exceção é uma linha fina (espessura 0), que permanece com largura fixa de 1 pixel em qualquer nível de Qualidade.

Alterar a Qualidade renderiza novamente a visualização imediatamente, para que você veja a nitidez real antes de exportar.

## Selecionando uma área de exportação personalizada

Por padrão a prévia mostra exatamente o que estava visível no canvas quando você abriu o Print Manager. Para exportar uma região específica:

1. Clique em **Mudar Área** — o Print Manager se oculta e o canvas torna-se interativo.
2. **Clique no primeiro canto** do retângulo de exportação.
3. **Clique no canto oposto** — o Print Manager reabre com a área selecionada na prévia.

Pressione `Escape` durante a seleção de área para cancelar e restaurar a área anterior.

O canvas de prévia redimensiona dinamicamente para corresponder à **proporção exata** da área selecionada, de modo que a prévia é precisa ao pixel.

## Formatos de exportação

| Formato | Ideal para | Notas |
|---------|-----------|-------|
| **PNG** | Sem perda, linhas nítidas | Fundo branco, sem transparência |
| **JPEG** | Arquivo menor para compartilhamento | Qualidade 95%, leve compressão |
| **WebP** | Arquivo menor para web | Mesma qualidade 95%, melhor compressão que JPEG |
| **PDF** | Documentos prontos para impressão | Imagem incorporada a 150 DPI no contêiner PDF |

O arquivo exportado é nomeado `kulman-<timestamp>.<ext>` e é baixado automaticamente.

## Resolução e fundo de exportação

- Resolução máxima: **2000 × 2000 pixels**, escalada proporcionalmente à área selecionada.
- O fundo é sempre **branco**.
- Camadas marcadas como **não plotáveis** são excluídas da exportação.

## Referência de teclado

| Tecla | Ação |
|-------|------|
| `Escape` (durante seleção de área) | Cancela a seleção de área, restaura a área anterior |
| `Escape` (no Print Manager) | Fecha o Print Manager |
