---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Budding Certus Quartz
  icon: flawless_budding_quartz
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:flawless_budding_quartz
- ae2:flawed_budding_quartz
- ae2:chipped_budding_quartz
- ae2:damaged_budding_quartz
- ae2:small_quartz_bud
- ae2:medium_quartz_bud
- ae2:large_quartz_bud
- ae2:quartz_cluster
---

# 萌芽的赛特斯石英母岩

（另见：[赛特斯石英生长](../ae2-mechanics/certus-growth.md)）  

<GameScene zoom="4" background="transparent">
  <Import Structure src="/assets/assemblies/budding_blocks.snbt" />
  <Isometric Camera yaw="195" pitch="30" />
</GameScene>

赛特斯石英芽会从萌芽的赛特斯石英母岩方块上生长出来，类似于紫水晶。这些方块可在[陨石](../ae2-mechanics/meteorites.md)中找到。

萌芽的赛特斯石英母岩有 4 个品级：**无瑕的**、**有瑕的**、**开裂的**和**损坏的**。借助 HWYLA、Jade、The One Probe 等模组（或 F3 调试屏幕）可以最方便地识别它们。

对于有瑕的、开裂的和损坏的萌芽赛特斯石英母岩，每当芽体生长到下一阶段时，母岩都有几率降级一级，最终变成普通的<ItemLink id="quartz_block" />。

无瑕的萌芽赛特斯石英母岩不会因芽体生长而降级，可作为无限来源使用。

如果用普通镐子挖掘，萌芽的赛特斯石英母岩会降级 1 级。如果用带有精准采集附魔的镐子挖掘，它们不会降级——**除非是无瑕的**。**这意味着无瑕的萌芽赛特斯石英母岩无法用镐子采集并移动**。取而代之的是，可以使用[跨空间存储](../ae2-mechanics/spatial-io.md)来剪切粘贴无瑕的萌芽方块。

## 配方

有瑕的、开裂的和损坏的萌芽赛特斯石英母岩可以通过将上一品级的萌芽方块（或一个<ItemLink id="quartz_block" />）与一个或多个<ItemLink id="charged_certus_quartz_crystal" />一起丢入水中来合成。

无瑕的萌芽赛特斯石英母岩无法合成，只能在世界中寻找。



<Row>
  <RecipeFor id="damaged_budding_quartz" />

  <RecipeFor id="chipped_budding_quartz" />

  <RecipeFor id="flawed_budding_quartz" />
</Row>
