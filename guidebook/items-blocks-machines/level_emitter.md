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

# ME 标准发信器

ME 标准发信器根据[网络存储](../ae2-mechanics/import-export-storage.md)中某种物品的数量发出红石信号。  
还有一个版本是根据你的网络中存储的[能量](../ae2-mechanics/energy.md)发出红石信号。  

你可以从 JEI/REI 将物品和流体拖入槽位，即使你实际上并没有那种物品。  

右键点击一个流体容器（如水桶或流体储罐）来将那流体设置为过滤器，而不是水桶或储罐物品。  

它们属于一种[线缆子部件](../ae2-mechanics/cable-subparts.md)。  
与其他[设备](../ae2-mechanics/devices.md)不同，ME 标准发信器*不*需要[频道](../ae2-mechanics/channels.md)。  

## 设置

* ME 标准发信器可以设置为“大于/等于”或“小于”模式
* 当插入合成卡<ae2:crafting_card>时，它可以设置为“在物品合成时发出红石信号”或“发出红石信号以合成物品”

## 升级

ME 标准发信器支持以下[升级](upgrade_cards.md)：  
* 模糊卡<ae2:fuzzy_card>让发信器按耐久度进行过滤和/或忽略物品 NBT
* 合成卡<ae2:crafting_card>启用合成功能

## 合成功能

如果插入了合成卡<ae2:crafting_card>，ME 标准发信器将切换到合成模式。  

这启用两个选项：  
第一个选项，“在物品合成时发出红石信号”，让 ME 标准发信器在您的[自动合成](../ae2-mechanics/autocrafting.md)通过 ME 样板供应器<ae2:pattern_provider>合成某个特定物品时发出红石信号。这对于只在特定高耗能自动化 setup 实际使用时才开启它非常有用。  

第二个选项，“发出红石信号以合成物品”，对于特定使用场景极为有用，比如无限农场和那些只有几率产出而不是必定产出的自动化配置。  

此设置为[自动合成](../ae2-mechanics/autocrafting.md)创建一个虚拟[样板](patterns.md)，用于 ME 标准发信器过滤槽位中的任何物品。  

（为了正确运作，相同物品的实际样板**不应存在于**你的 ME 样板供应器<ae2:pattern_provider>中）  

这种“样板”不定义甚至不关心原料。  
它只表示“如果你从这个 ME 标准发信器发出红石信号，ME 系统将在不久或遥远的将来收到这个物品”。  
这通常用于启动和关闭无需输入原料的无限农场，或者用于启动[处理递归配方的系统](../example-setups/recursive-crafting-setup.md)（标准的自动合成无法理解这些配方），例如，如果你有一台可以刷石机，就可以实现“1圆石 = 2圆石”。  

## 配方

<RecipeFor id="level_emitter" />

<RecipeFor id="energy_level_emitter" />
