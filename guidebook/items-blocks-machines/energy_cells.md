---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Energy Cells
  icon: energy_cell
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:energy_cell
- ae2:dense_energy_cell
- ae2:creative_energy_cell
---

# 能源元件

能源元件为网络提供更多的[能量](../ae2-mechanics/energy.md)存储。  
一定的能量缓冲有助于平抑大量物品插入或提取时的能量尖峰，而更大的能量存储可以让网络在能量不产生时（比如夜间使用太阳能板时）继续运行，或者应对[空间存储](../ae2-mechanics/spatial-io.md)的巨大瞬时能量消耗。  

## 填充条

元件侧面的条对应其存储的能量多少。
* 低于25%时显示0
* 在25%到50%之间时显示1
* 在50%到75%之间时显示2
* 在75%到99%之间时显示3
* 高于99%时显示4

## 元件类型

* 能源元件<ae2:energy_cell>可以存储200k AE，对于大多数使用场景来说一个就足够了，可以轻松应对正常网络使用的功率波动。
* 致密能源元件<ae2:dense_energy_cell>可以存储1.6M AE，适用于你想依靠存储的能量运行网络，或者应对大型[空间存储](../ae2-mechanics/spatial-io.md)装置的巨大瞬时能量消耗的情况。
* 创造能源元件<ae2:creative_energy_cell>是用于测试的创造物品，提供无限能量。

## 配方

<Row>
  <RecipeFor id="energy_cell" />

  <RecipeFor id="dense_energy_cell" />
</Row>
