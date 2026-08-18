---
title: Font+ 命令 — 从命令行上传自定义 TTF 字体
description: Font+ 命令会打开系统文件选择器以上传 .ttf 字体，而无需先打开 Font Manager 对话框。这与 Font Manager 中「Add Font」按钮触发的上传操作完全相同，此处作为独立的命令行命令提供。
keywords: [font add 命令, font+ 命令, 上传 ttf 命令行, 自定义字体 CAD, kulmanlab]
group: style
order: 3
---

# Font+

`Font+` 命令会打开系统文件选择器以上传自定义 `.ttf` 字体，而无需先打开 [Font Manager](../font-manager/) 对话框。这与 Font Manager 中 **Add Font** 按钮触发的上传操作完全相同 —— Font+ 只是从命令行直接到达那里的一条捷径。

## 上传字体

1. 在命令行中输入 `Font+`，或单击 [Font Manager](../font-manager/) 对话框底部的 **Add Font**。
2. 在系统选择器中选择一个 `.ttf` 文件。仅支持 TrueType 字体 —— 不支持 `.otf` 和 `.woff`/`.woff2`。

文件选择器一打开，命令即结束 —— 之后不会再有点击或命令行输入。选定文件后，字体会立即注册并出现在 **User** 分组中。

## 上传时会发生什么

- 文件名(不含扩展名)将成为该字体的名称。上传 `MyFont.ttf` 会添加一个名为 `MyFont` 的字体。
- 上传的文件名如果与现有自定义字体相同,会**替换**该字体。
- 字体会永久保存在浏览器中(IndexedDB),并在您下次打开 KulmanLab CAD 时自动重新加载 —— 它不与当前图纸绑定。

## 键盘参考

Font+ 没有自己的键盘操作 —— 整个命令就是浏览器原生的文件选择对话框。取消该对话框(或不选择任何文件)会使字体列表保持不变。

## 相关命令

| 命令 | 功能 |
|------|------|
| [Font Manager](../font-manager/) | 浏览、预览、选择和删除字体，包括您自己上传的字体 |
| [Text](../text/) | 放置应用字体选择的文字标签 |
