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

ME IO 端口允许你快速地将[存储元件](../items-blocks-machines/storage_cells.md)填满或清空到[网络存储](../ae2-mechanics/import-export-storage.md)中。  
它可以使用赛特斯石英扳手<ae2:certus_quartz_wrench>进行旋转。  

## 设置

* IO 端口可以设置为在元件为空、已满或工作完成时将元件移动到输出槽位。
* 如果插入了红石卡<ae2:redstone_card>，将会有各种红石条件的选项。
* 在 GUI 的中心，有一个箭头用于设置物品传输的方向，从元件到[网络存储](../ae2-mechanics/import-export-storage.md)，或从存储到元件。

## 升级

IO 端口支持以下[升级](upgrade_cards.md)：  
* 加速卡<ae2:speed_card>增加每次操作移动的物品数量
* 红石卡<ae2:redstone_card>添加红石控制，允许在高信号、低信号或每次脉冲时激活

## 配方

<RecipeFor id="io_port" />
