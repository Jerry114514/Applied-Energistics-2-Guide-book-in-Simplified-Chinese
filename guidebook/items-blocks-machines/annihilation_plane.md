---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Annihilation Plane
  icon: annihilation_plane
  position: 210
categories:
- devices
item_ids:
- ae2:annihilation_plane
---

## 毁灭面板

<GameScene zoom="8" background="transparent">
  <Import Structure src="/assets/blocks/annihilation_plane.snbt" />
</GameScene>

毁灭面板可以破坏方块并拾取物品。它的工作原理类似于<ItemLink id="import_bus" />，会将物品推送至[网络存储](../ae2-mechanics/import-export-storage.md)。物品必须与面板正面碰撞才能被拾取，它不会在范围内自动拾取。

毁灭面板可以附上任何镐类附魔，没错，你可以在几个面板上堆叠高等级时运，如果整合包允许的话，甚至可以[自动化矿石处理](../example-setups/ore-fortuner.md)。此外，精准采集的效果如你所料，效率附魔会降低破坏方块时的能量消耗，耐久附魔则有几率不消耗能量。

它们是[线缆子部件](/ae2-mechanics/cable-subparts.md)。

**请记得在领地声明中启用假玩家（Fake Player）权限。**

## 过滤

毁灭面板只有在网络能够存储其掉落物/物品时，才会破坏方块或拾取物品。这意味着要对其进行过滤，*你必须限制其网络能存储的内容*，最常用的方法是将它放在[子网络](../ae2-mechanics/subnetworks.md)上。可以使用<ItemLink id="storage_bus" />或[存储元件](../items-blocks-machines/storage_cells.md)进行[分区](../cell-workbench.md)来实现这一点。

<GameScene zoom="6" interactive={true}>
  <Import Structure src="/assets/assemblies/annihilation_filtering.snbt" />

  <DiamondAnnotation pos="1.0 5.0 0.5" color="#00ff00">
        过滤为你想要破坏的方块所掉落的物品
  </DiamondAnnotation>

  <DiamondAnnotation pos="5.0 5.0 2.5" color="#00ff00">
        分区为你想要破坏的方块所掉落的物品
  </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

再次强调，它是*根据物品掉落物*来过滤的。例如，如果你想要过滤破坏<ItemLink id="minecraft:amethyst_cluster" />，你需要一个附有精准采集的面板，否则每个前生长阶段都不会掉落任何东西，面板就会无视过滤条件将其破坏，因为网络总能存储"无"。

## 配方

<RecipeFor id="annihilation_plane" />