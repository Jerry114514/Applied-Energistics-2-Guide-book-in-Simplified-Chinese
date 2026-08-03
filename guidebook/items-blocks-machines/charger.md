---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Charger
  icon: charger
  position: 310
categories:
- machines
item_ids:
- ae2:charger
---

# 充能器

<BlockImage id="charger" scale="8" />

充能器提供了一种为受支持的工具和<ItemLink id="certus_quartz_crystal" />充能的方式。

能量可通过顶部或底部输入，既可使用AE2的[线缆](cables.md)供电，也可使用其他模组的能量线缆供电。它能接受AE2的能量（AE）或Forge能量（FE）。物品可从任意面输入或取出。只有充能完成的结果可以被取出，因此无需使用过滤器来防止取出赛特斯石英水晶而非充能的赛特斯石英。可使用<ItemLink id="certus_quartz_wrench" />旋转以方便自动化。  

可用于将<ItemLink id="certus_quartz_crystal" />制作成<ItemLink id="charged_certus_quartz_crystal" />，以及将<ItemLink id="minecraft:compass" />制作成<ItemLink id="meteorite_compass" />。

若要手动供能，可在顶部或底部放置<ItemLink id="crank" />，然后右键点击直至物品充能完成。

它还充当AE2村民的工作站点方块。

# 简单自动化

例如，利用其可旋转特性，你可以像这样半自动化充能器：

<GameScene zoom="4" background="transparent">
  <Import Structure src="/assets/assemblies/charger_hopper.snbt" />
  <Isometric Camera yaw="195" pitch="30" />
</GameScene>

## 配方

<RecipeFor id="charger" />
