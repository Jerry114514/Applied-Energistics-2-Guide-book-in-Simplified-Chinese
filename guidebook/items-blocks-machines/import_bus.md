---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME Import Bus
  icon: import_bus
  position: 220
categories:
- devices
item_ids:
- ae2:import_bus
---

# ME 输入总线

ME 输入总线从其所接触的容器中提取物品和流体（以及附加组件支持的任何其他东西），并将它们推入[网络存储](../ae2-mechanics/import-export-storage.md)。  
为了减少卡顿，如果输入总线最近没有导入任何东西，它会进入一种“休眠模式”，在这种模式下它运行缓慢，当它成功导入某物时会唤醒并加速到全速（每秒4次操作）。  
它们属于一种[线缆子部件](../ae2-mechanics/cable-subparts.md)。  

## 过滤

默认情况下，总线会导入它能接触到的任何东西。插入其过滤槽位的物品将作为白名单，只允许导入这些特定物品。  
你可以从 JEI/REI 将物品和流体拖入槽位，即使你实际上并没有任何那种物品。  
右键点击一个流体容器（如水桶或流体储罐）来将那流体设置为过滤器，而不是水桶或储罐物品。  

## 升级

输入总线支持以下[升级](upgrade_cards.md)：
* 容量卡<ae2:capacity_card>增加过滤槽位的数量
* 加速卡<ae2:speed_card>增加每次操作移动的物品数量
* 模糊卡<ae2:fuzzy_card>让总线按耐久度进行过滤和/或忽略物品 NBT
* 反相卡<ae2:inverter_card>将过滤器从白名单切换为黑名单
* 红石卡<ae2:redstone_card>添加红石控制，允许在高信号、低信号或每次脉冲时激活

## 速度

| 加速卡 | 每次操作移动的物品数 |
|:---|:---|
| 0 | 1 |
| 1 | 8 |
| 2 | 32 |
| 3 | 64 |
| 4 | 96 |

## 配方

<RecipeFor id="import_bus" />
