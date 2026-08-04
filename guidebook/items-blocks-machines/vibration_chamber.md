---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Vibration Chamber
  icon: vibration_chamber
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:vibration_chamber
---

# 谐振仓

虽然为你的网络提供[能量](../ae2-mechanics/energy.md)的主要预期方式是能源接收器<ae2:energy_acceptor>，但谐振仓可以直接生成小到中等量的 AE。

默认情况下（没有[升级](upgrade_cards.md)和默认配置），它产生40 AE/t。

当网络的[能量](../ae2-mechanics/energy.md)存储已满时，谐振仓会降低功率以节约燃料，但不能完全关闭。

## 设置

* 谐振仓提供用于以 AE 或 E/FE 查看能量的全局设置。

## 升级

谐振仓支持以下[升级](upgrade_cards.md)：  
* 能源卡<ae2:energy_card>使谐振仓的效率提高+50%，最高+150%，即基础效率的250%。
* 加速卡<ae2:speed_card>使谐振仓的燃烧速率提高+50%，最高+150%，即基础功率输出的250%。  

## 配置

谐振仓的属性可以在你的 .minecraft/config/ae2 文件夹中的 common.json 中编辑。  

* baseEnergyPerFuelTick 设置谐振仓的基础、未升级效率。
* minEnergyPerGameTick 设置最低可能的能量生成（即使网络不需要能量，谐振仓也总是会缓慢消耗一些燃料）。
* maxEnergyPerGameTick 设置未升级的最大输出（和速度）。

## 配方

<RecipeFor id="vibration_chamber" />
