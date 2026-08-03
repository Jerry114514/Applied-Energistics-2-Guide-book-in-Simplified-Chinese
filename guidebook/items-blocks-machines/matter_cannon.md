---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Matter Cannon
  icon: matter_cannon
  position: 410
categories:
- tools
item_ids:
- ae2:matter_cannon
---

# 物质炮

物质炮是一种便携式轨道炮，可以发射小型物品作为射弹，比如物质球<ae2:matter_ball>和金属粒。伤害取决于所发射的物品，像金粒（10点伤害）这样的“较重”物品会比像物质球（2点伤害）这样的轻物品造成更多伤害。  
每次射击消耗基础能量1600 AE。  

当配置选项“matterCannonBlockDamage”为 true 时，物质炮会根据方块硬度和弹药伤害来破坏方块。  

它的能量可以在充能器<ae2:charger>中重新充能。  
物质炮就像[存储元件](storage_cells.md)一样，它的弹药匣可以通过将物质炮插入 ME 箱子<ae2:chest>中的存储元件槽位来最容易地填满。  

## 升级

物质炮支持以下[升级](upgrade_cards.md)，通过元件工作台<ae2:cell_workbench>插入：  
* 模糊卡<ae2:fuzzy_card>让元件按耐久度进行分区和/或忽略物品 NBT
* 反相卡<ae2:inverter_card>将过滤器从白名单切换为黑名单
* 加速卡<ae2:speed_card>增加每次射击消耗的能量，使其以更大的威力射击。
* 溢出销毁卡<ae2:void_card>在元件已满时销毁插入的物品。请小心分区！
* 能源卡<ae2:energy_card>用于增加电池容量

## 配方

<RecipeFor id="matter_cannon" />
