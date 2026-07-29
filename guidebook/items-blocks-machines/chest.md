---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME Chest
  icon: chest
  position: 210
categories:
- devices
item_ids:
- ae2:chest
---

# ME 箱子

<GameScene zoom="8" background="transparent">
<Import Structure src="/assets/blocks/chest.snbt" />
</GameScene>

ME 箱子就像一个微型网络，集成了<ItemLink id="terminal" />、<ItemLink id="drive" />和<ItemLink id="energy acceptor" />的功能。虽然它可以作为一个微型存储网络使用，但由于只能容纳一个[存储元件](../items-blocks-machines/storage_cells.md)，其用途相当有限。

相反，它的真正价值在于与内部安装的存储元件进行交互。其集成的终端只能查看和访问已安装驱动器中的物品，而主网络上的[设备](../ae2-mechanics/devices.md)则可以访问任何[网络存储](../ae2-mechanics/import-export-storage.md)中的物品，包括 ME 箱子。

ME 箱子有 2 种不同的 GUI，并且具有物品运输的方向性。与顶部终端交互会打开集成终端。物品可以通过这个面插入到已安装的存储元件中，但不能取出。与其他面交互会打开包含存储元件槽位和优先级设置的 GUI。存储元件只能通过带有元件槽位的面由物流系统插入和取出。

可以使用<ItemLink id="certus_quartz_wrench" />旋转。

它有一个小型的 AE 能量存储缓冲，因此如果所在网络没有[能源元件](../items-blocks-machines/energy-cells.md)，一次性插入或取出太多物品可能会导致其断电。

终端可以使用<ItemLink id="color_applicator" />染色。

<GameScene zoom="6" background="transparent">
<Import Structure src="/assets/assemblies/chest_color.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 设置

ME 箱子拥有与<ItemLink id="terminal" />或<ItemLink id="crafting_terminal" />相同的所有设置。但它不支持<ItemLink id="view_cell" />。

## 元件状态 LED

箱子中的元件上有一个 LED，用于显示其状态：

| 颜色   | 状态                                                                             |
| :----- | :------------------------------------------------------------------------------- |
| 绿色   | 空                                                                               |
| 蓝色   | 有部分内容                                                                       |
| 橙色   | [类型](../ae2-mechanics/bytes-and-types.md)已满，无法添加新类型                   |
| 红色   | [字节](../ae2-mechanics/bytes-and-types.md)已满，无法再插入物品                   |
| 黑色   | 无电力或驱动器没有[频道](../ae2-mechanics/channels.md)                           |

## 优先级

可以通过点击元件槽位 GUI 右上角的扳手来设置优先级。进入网络的物品会优先存入优先级最高的存储。如果两个存储或元件具有相同的优先级，且其中一个已包含该物品，则会优先选择该存储。任何[分区](cell-workbench.md)过的元件在与其它存储处于同一优先级组时，会被视为已包含该物品。从存储中取出的物品会从优先级最低的存储中取出。这种优先级系统意味着，随着物品在网络存储中的插入和取出，高优先级的存储会被填满，而低优先级的存储会被清空。

## 配方

<RecipeFor id="chest" />
