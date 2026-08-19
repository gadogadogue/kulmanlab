---
title: LayerManager — 在一个表格中管理所有图层（KulmanLab CAD）
description: LayerManager 命令打开一个包含图形所有图层的表格，让您添加图层并直接为每个图层编辑冻结、锁定、打印、颜色、线宽和线型。
keywords: [图层管理器, CAD 图层表, 管理图层 CAD, 添加图层 CAD, 冻结锁定打印图层, kulmanlab 图层管理]
group: layer
order: 1
---

# LayerManager

`LayerManager` 命令打开一个列出图形所有图层的表格，**Freeze**（冻结）、**Lock**（锁定）、**Plot**（打印）、**颜色**、**线宽**和**线型**都可以直接在行中编辑。这是添加新图层和调整现有图层行为的核心位置 — 其他图层命令（[LayerMakeCurrent](../layer-make-current/)、[LayerMatch](../layer-match/)、[LayerIsolate](../layer-isolate/)、[LayerUnfreezeAll](../layer-unfreeze-all/)）各自完成一件专注的事，无需打开它。

## 打开图层管理器

- 在命令行中输入 `LayerManager`，**或**
- 单击图层面板中的 **Layer Manager** 按钮。

对话框以浮动面板形式打开；事先不需要选中任何内容。

## 图层表

| 列 | 控制的内容 |
|----|--------------|
| Name | 图层名称，在表中以只读方式显示（创建时设置一次） |
| Freeze | 隐藏图层的图元并将其排除在选择之外，直到解冻 |
| Lock | 阻止编辑图层上的图元，但不隐藏它们 |
| Plot | 打印或导出为 PDF 时是否包含该图层的图元 |
| Color | 图层的 ACI 颜色 — 单击色样打开颜色选择器 |
| Lineweight | 图层的线宽 — 单击色块打开线宽选择器 |
| Linetype | 图层的虚线图案 — 单击色块打开线型选择器 |

切换 Freeze、Lock 或 Plot 会立即生效 — 没有单独的保存步骤。颜色、线宽或线型设置为 **ByLayer**（默认值）的图元会采用您在此处的设置；拥有自己显式覆盖值的图元不受影响。

## 添加图层

1. 单击表格底部的 **+ Add Layer**。
2. 输入名称并按 **Enter** 确认，或按 **Escape** 取消。

图层名称可以包含字母、数字、空格以及 `_`、`-`、`$`。空白、已被使用或包含其他字符的名称会被拒绝并显示内联错误，该行会保持打开以便再次尝试。

新图层默认**未冻结、未锁定、可打印**，颜色为 7（白/黑），线宽为 Default，线型为 Continuous — 与 [Import](../import/) 在空白图形中赋予图层 `0` 的默认值相同。

## 这里做不到的事

没有删除按钮 — 图层一旦创建就永远不会被移除，只能冻结或不再使用。表格也不会显示哪个图层是*当前*图层；这是通过图层面板的下拉菜单或 [LayerMakeCurrent](../layer-make-current/) 设置的，而不是从这个对话框设置的。

## 键盘参考

| 按键 | 操作 |
|-----|------|
| `Enter` | 确认新图层的名称（添加过程中） |
| `Escape` | 取消添加图层，或关闭对话框 |

## 相关命令

| 命令 | 功能 |
|------|------|
| [LayerMakeCurrent](../layer-make-current/) | 将单击图元所在图层设为当前图层 |
| [LayerMatch](../layer-match/) | 将选中图元的图层重新指定为与源图元相同 |
| [LayerIsolate](../layer-isolate/) | 冻结除选中图元所在图层以外的所有图层 |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | 一键解冻所有图层 |
