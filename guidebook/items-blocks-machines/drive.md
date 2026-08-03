---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME Drive
  icon: drive
  position: 210
categories:
- devices
item_ids:
- ae2:drive
---

# ME 驱动器

ME 驱动器是你插入[存储元件](storage_cells.md)以将其用作[网络存储](../ae2-mechanics/import-export-storage.md)的[设备](../ae2-mechanics/devices.md)。它有10个槽位，每个槽位可以容纳一个元件。  

如果出于某种原因你想这么做，你可以使用任何物品物流方式（如漏斗或 AE2 总线）从其库存中推出和拉入元件。  

它可以使用赛特斯石英扳手<ae2:certus_quartz_wrench>进行旋转。  

## 元件状态 LED

驱动器中的元件上有一个 LED 显示其状态：
| 颜色 | 状态 |
| :--- | :--- |
| 绿色 | 空 |
| 蓝色 | 有一些内容 |
| 橙色 | [类型](../ae2-mechanics/bytes-and-types.md)已满，无法添加新类型 |
| 红色 | [字节](../ae2-mechanics/bytes-and-types.md)已满，无法插入更多物品 |
| 黑色 | 无能量或驱动器没有[频道](../ae2-mechanics/channels.md) |

## 优先级

优先级可以通过点击 GUI 右上角的扳手来设置。  
进入网络的物品将以最高优先级的存储作为第一目的地。  

如果两个存储或元件具有相同优先级，且其中一个已经包含该物品，它们将优先选择该存储。当与其他存储处于同一优先级组时，任何[分区](cell_workbench.md)的元件都将被视为已包含该物品。从存储中移除的物品将从优先级最低的存储中移除。这个优先级系统意味着当物品被插入和移出网络存储时，高优先级的存储将被填满，而低优先级的存储将被清空。

## 配方

<RecipeFor id="drive" />
