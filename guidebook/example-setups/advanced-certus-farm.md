---
navigation:
    parent: example-setups/example-setups-index.md
    title: 高级赛特斯石英农场
    icon: certus_quartz_crystal
    position: 120
---

# 高级赛特斯石英农场

这基本上就是[半自动赛特斯石英农场](semiauto-certus-farm.md)，只不过它已经完全集成到你的ME系统中了。

这个设置不是存放大量萌芽方块并偶尔手动刷新它们，而是使用[充能器自动化](charger-automation.md)和[投入水中自动化](throw-in-water-automation.md)来自动完成这一切。

**这是一个复杂的建筑，有些东西隐藏在其他东西后面，请旋转视角从各个角度查看**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/advanced_certus_farm.snbt" />

  <BoxAnnotation color="#ddaaaa" min="3.7 2 1" max="4 3 2">
        (1) 湮灭面 #1：没有GUI可配置，但可以附魔时运。
  </BoxAnnotation>

  <BoxAnnotation color="#ddaaaa" min="2 2 1.7" max="3 3 2">
        (2) 存储总线 #1：过滤为赛特斯石英晶体。
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 2.5 1.5" color="#ff0000">
    水晶簇破坏子网络
  </DiamondAnnotation>

  <BoxAnnotation color="#aaddaa" min="3.7 1 1" max="4 2 2">
        (3) 湮灭面 #2：没有GUI可配置，但附魔了精准采集。
  </BoxAnnotation>

  <BoxAnnotation color="#aaddaa" min="2 1 1.7" max="3 2 2">
        (4) 存储总线 #2：过滤为赛特斯石英方块。
        <BlockImage id="quartz_block" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 1.5 1.5" color="#00ff00">
    赛特斯方块破坏子网络
  </DiamondAnnotation>

  <BoxAnnotation color="#ffddaa" min="4 0.7 1" max="5 1 2">
        (5) 形成面：默认配置。
  </BoxAnnotation>

  <BoxAnnotation color="#ffddaa" min="2 0.7 2" max="3 1 3">
        (6) 输入总线：过滤为瑕疵赛特斯石英萌芽。
        <BlockImage id="flawed_budding_quartz" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 0.5 1.5" color="#ddcc00">
    萌芽方块放置子网络
  </DiamondAnnotation>

  <BoxAnnotation color="#aaaadd" min="1.7 2 2" max="2 3 3">
        (7) 存储总线 #3：过滤为赛特斯石英晶体。优先级设置高于你的主存储。
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#aaaadd" min="2 1 2" max="3 2 3">
        (8) 接口：设置为在其内部保留1个瑕疵赛特斯石英萌芽，拥有合成卡。
        <Row><BlockImage id="flawed_budding_quartz" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="1.5 0.5 0" color="#00ff00">
        连接到主网络、充能器自动化和投入水中自动化
        <Row>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/charger_automation.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/throw_in_water.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        </Row>
    </DiamondAnnotation>

  <IsometricCamera yaw="165" pitch="5" />
</GameScene>

## 配置

### 水晶簇破坏器：

* 第一个<ItemLink id="annihilation_plane" /> (1) 没有GUI，无法配置，但可以附魔时运。
* 第一个<ItemLink id="storage_bus" /> (2) 过滤为<ItemLink id="certus_quartz_crystal" />。

### 赛特斯方块破坏器：

* 第二个<ItemLink id="annihilation_plane" /> (3) 没有GUI，无法配置，但必须附魔精准采集。
* 第二个<ItemLink id="storage_bus" /> (4) 过滤为<ItemLink id="quartz_block" />。

### 萌芽方块放置器：

* <ItemLink id="formation_plane" /> (5) 处于默认配置。
* <ItemLink id="import_bus" /> (6) 过滤为<ItemLink id="flawed_budding_quartz" />。

### 在主网络上：

* 第三个<ItemLink id="storage_bus" /> (7) 过滤为<ItemLink id="certus_quartz_crystal" />，并将其[优先级](../ae2-mechanics/import-export-storage.md#storage-priority)设置高于主存储。
* <ItemLink id="interface" /> (8) 设置为在其内部保留1个瑕疵赛特斯石英萌芽，并拥有一张<ItemLink id="crafting_card" />。

## 工作原理

### 水晶簇破坏器：

水晶簇破坏子网络的工作原理与[简易赛特斯石英农场](simple-certus-farm.md)中的子网络非常相似。

1. <ItemLink id="annihilation_plane" />尝试破坏面前的东西，但只能破坏<ItemLink id="quartz_cluster" />，因为子网络上唯一的存储是过滤为<ItemLink id="certus_quartz_crystal" />的<ItemLink id="storage_bus" />。
2. <ItemLink id="storage_bus" />将赛特斯石英晶体存储到木桶中。

### 赛特斯方块破坏器

赛特斯方块破坏子网络用于在萌芽方块变成普通<ItemLink id="quartz_block" />后将其破坏。
它的工作原理与水晶簇破坏器类似。

1. <ItemLink id="annihilation_plane" />尝试破坏面前的东西，但只能破坏<ItemLink id="quartz_block" />，因为子网络上唯一的存储是过滤为<ItemLink id="quartz_block" />的<ItemLink id="storage_bus" />。该平面需要精准采集附魔，这样萌芽方块在被破坏时不会退化，因此平面不会过早破坏它。
2. <ItemLink id="storage_bus" />将赛特斯石英方块存储到<ItemLink id="interface" />中，允许[投入水中自动化](throw-in-water-automation.md)用它来制造新的<ItemLink id="flawed_budding_quartz" />。

### 萌芽方块放置器

萌芽方块放置子网络用于在破坏子网络破坏旧的耗尽方块时放置新的<ItemLink id="flawed_budding_quartz" />。

1. <ItemLink id="import_bus" />从<ItemLink id="interface" />导入萌芽方块到[网络存储](../ae2-mechanics/import-export-storage.md)
2. 子网络上唯一的存储是<ItemLink id="formation_plane" />，它放置萌芽方块。

### 在主网络上

* <ItemLink id="storage_bus" />使主网络（以及[充能器自动化](charger-automation.md)）能够访问木桶中所有的赛特斯石英晶体。它被设置为高[优先级](../ae2-mechanics/import-export-storage.md#storage-priority)，以便赛特斯石英晶体优先被放回木桶而不是主存储。
* <ItemLink id="interface" />使萌芽方块放置子网络能够访问<ItemLink id="flawed_budding_quartz" />，并为赛特斯方块破坏子网络提供一种将耗尽的方块返回主网络的方式。<ItemLink id="crafting_card" />允许接口从主网络的[自动合成](../ae2-mechanics/autocrafting.md)请求新的萌芽方块。
