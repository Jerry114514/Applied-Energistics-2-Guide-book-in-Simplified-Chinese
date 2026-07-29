---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME IO Port
  icon: io_port
  position: 210
categories:
- devices
item_ids:
- ae2:io_port
---

# ME IO 端口

<BlockImage id="io_port" p:powered="true" scale="8" />

IO 端口可以让你快速将[存储元件](items-blocks-machines/storage-cells.md)中的物品填充到[网络存储](ae2-mechanics/import-export-storage.md)中，或从中清空。

可以使用<ItemLink id="certus_quartz_wrench" />旋转。

## 设置

*   IO 端口可以设置为在元件为空、已满或工作完成时将其移至输出槽位。
*   如果插入<ItemLink id="redstone_card" />，将提供各种红石条件的选项。
*   在 GUI 中央有一个箭头，用于设置物品传输方向：从元件到[网络存储](ae2-mechanics/import-export-storage.md)，或从存储到元件。

## 升级

IO 端口支持以下[升级](upgrade-cards.md)：

*   <ItemLink id="speed_card" />：提高每次操作移动的物品数量。
*   <ItemLink id="redstone_card" />：增加红石控制，可选择高信号激活、低信号激活或每次脉冲激活。

## 配方

<RecipeFor id="io_port" />
