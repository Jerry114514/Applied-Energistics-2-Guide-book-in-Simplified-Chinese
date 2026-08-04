---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Storage Cells
  icon: item_storage_cell_1k
  position: 410
categories:
- tools
item_ids:
- ae2:item_cell_housing
- ae2:fluid_cell_housing
- ae2:cell_component_1k
- ae2:cell_component_4k
- ae2:cell_component_16k
- ae2:cell_component_64k
- ae2:cell_component_256k
- ae2:item_storage_cell_1k
- ae2:item_storage_cell_4k
- ae2:item_storage_cell_16k
- ae2:item_storage_cell_64k
- ae2:item_storage_cell_256k
- ae2:fluid_storage_cell_1k
- ae2:fluid_storage_cell_4k
- ae2:fluid_storage_cell_16k
- ae2:fluid_storage_cell_64k
- ae2:fluid_storage_cell_256k
---

# 存储元件

存储元件是应用能源中最主要的存储方式之一。  
它们通过放入 ME 驱动器<ae2:drive>或 ME 箱子<ae2:chest>中使用。  
关于其字节和类型容量的说明，请参阅[字节与类型](../ae2-mechanics/bytes-and-types.md)。  

如果元件为空，手持元件 Shift 右键点击可以将存储组件从外壳中取出。  

你可以通过在合成网格中将存储元件与更高等级的存储组件合成来升级存储元件。其内容将被保留，低等级的组件将被返还。  

## 不同类型数量下的存储容量

[类型的前置成本](../ae2-mechanics/bytes-and-types.md)使得一个只含1种类型的元件可以容纳的物品种类比63种类型全部使用的元件多2倍。

| 元件 | 1种类型使用时的总容量 | 63种类型使用时的总容量 |
| :--- | ---: | ---: |
| 1k ME 物品存储元件<ae2:item_storage_cell_1k> | 8,128 | 4,160 |
| 4k ME 物品存储元件<ae2:item_storage_cell_4k> | 32,512 | 16,640 |
| 16k ME 物品存储元件<ae2:item_storage_cell_16k> | 130,048 | 66,560 |
| 64k ME 物品存储元件<ae2:item_storage_cell_64k> | 520,192 | 266,240 |
| 256k ME 物品存储元件<ae2:item_storage_cell_256k> | 2,080,768 | 1,064,960 |


## 分区

元件可以被过滤为只接受特定物品，类似于 ME 存储总线<ae2:storage_bus>的过滤方式。这是在元件工作台<ae2:cell_workbench>中完成的。  

你可以从 JEI/REI 将物品拖入槽位，即使你实际上并没有那种物品。  

## 升级

存储元件支持以下[升级](upgrade_cards.md)，通过元件工作台<ae2:cell_workbench>插入：

* 模糊卡<ae2:fuzzy_card>（不适用于流体元件）让元件按耐久度进行分区和/或忽略物品 NBT
* 反相卡<ae2:inverter_card>将过滤器从白名单切换为黑名单
* 均分卡<ae2:equal_distribution_card>为每种类型分配相同数量的元件字节空间，这样单一类型无法填满整个元件
* 溢出销毁卡<ae2:void_card>在元件已满时销毁插入的物品（如果使用均分卡，则在该特定类型分配的空间已满时销毁），这对于阻止农场积压很有用。请小心分区！
* 便携元件可以接受能源卡<ae2:energy_card>来增加其电池容量

## 染色

便携物品和流体元件可以像皮革盔甲一样染色，通过将它们与染料一起合成来实现。  

# 外壳

元件可以用一个存储组件和一个外壳制作，或者用外壳配方围绕一个存储组件制作。  

# 存储组件

存储组件是所有 AE2 元件的核心，决定元件的容量。每升一级容量增加4倍，并需要3个上一级的组件。  

# 物品存储元件

物品存储元件最多可以容纳63种不同类型的物品，并提供所有标准容量。  

## 便携物品存储

这些就像一个口袋里的迷你 ME 箱子<ae2:chest>，或者一种背包。它们可以在充能器<ae2:charger>中充能。  

与标准存储元件不同，它们的类型容量会随着字节容量的增加而*减少*，并且总字节容量只有一半。  

除了所有元件都能接受的升级卡外，它们还可以接受能源卡<ae2:energy_card>来升级其内部电池。  

# 流体存储元件

流体存储元件最多可以容纳5种不同类型的流体，并提供所有标准容量。  

## 便携流体存储

这些就像一个口袋里的迷你 ME 箱子<ae2:chest>，或者一种背包。它们可以在充能器<ae2:charger>中充能。  

与标准存储元件不同，它们的类型容量会随着字节容量的增加而*减少*，并且总字节容量只有一半。  

除了所有元件都能接受的升级卡外，它们还可以接受能源卡<ae2:energy_card>来升级其内部电池。  

# 创造存储元件

创造元件**不提供无限存储**。相反，它们充当你所[分区](cell_workbench.md)的任何物品或流体的无限来源和归宿。
