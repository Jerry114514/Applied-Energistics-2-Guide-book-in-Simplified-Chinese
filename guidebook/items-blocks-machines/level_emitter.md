---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Level Emitter
  icon: level_emitter
  position: 220
categories:
- devices
item_ids:
- ae2:level_emitter
- ae2:energy_level_emitter
---

# 发信器

<GameScene zoom="8" background="transparent">
  <Import Structure src="/assets/blocks/level_emitter.snbt" />
</GameScene>

发信器会根据[网络存储](../ae2-mechanics/import-export-storage.md)中某物品的数量来发出红石信号。

还有一种版本会根据网络中存储的[能量](../ae2-mechanics/energy.md)来发出红石信号。

即使你实际上没有任何该物品，也可以从 JEI/REI 将物品和流体拖入槽位。

用流体容器（如桶或储罐）右键点击，可以将该流体设为过滤器，而不是桶或储罐本身。

它们是[线缆子部件](../ae2-mechanics/cable-subparts.md)。

与其他[设备](../ae2-mechanics/devices.md)不同，发信器*不需要*[频道](../ae2-mechanics/channels.md)。

## 设置

*   发信器可以设置为「大于/等于」或「小于」模式。
*   当插入<ItemLink id="crafting_card" />时，可以设置为「合成物品时发出红石信号」或「发出红石信号以合成物品」。

## 升级

发信器支持以下[升级](upgrade-cards.md)：

*   <ItemLink id="fuzzy_card" />让发信器按耐久度过滤和/或忽略物品 NBT。
*   <ItemLink id="crafting_card" />启用合成功能。

## 合成功能

如果插入了<ItemLink id="crafting_card" />，发信器将切换到合成模式。

这会启用两个选项：

第一个选项「合成物品时发出红石信号」，使发信器在[自动合成](../ae2-mechanics/autocrafting.md)通过<ItemLink id="pattern_provider" />合成某个特定物品时发出红石信号。这对于只在实际使用时才开启特定耗电的自动化设备非常有用。

第二个选项「发出红石信号以合成物品」，对于特定用例（如无限农场和只有概率产出而非保证产出的自动化设备）极为有用。此设置为发信器过滤槽中的任何物品创建一个虚拟[样板](patterns.md)，供[自动合成](../ae2-mechanics/autocrafting.md)使用。
（为了正确运行，你的<ItemLink id="pattern_provider" />中**不应存在**该物品的实际样板。）

这个「样板」不定义甚至不关心原料。它只是说：「如果你从这个发信器发出红石信号，ME 系统将在不久或很久后的某个时刻收到这个物品。」这通常用于激活和停用不需要输入原料的无限农场，或激活处理递归配方（标准自动合成无法理解）的系统，例如，如果你有一台复制圆石的机器，就可以使用「1 圆石 = 2 圆石」的配方。

## 配方

<RecipeFor id="level_emitter" />

<RecipeFor id="energy_level_emitter" />
