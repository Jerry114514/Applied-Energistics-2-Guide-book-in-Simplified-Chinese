---
navigation:
    parent: ae2-mechanics/ae2-mechanics-index.md
    title: 自动合成
    icon: pattern_provider
---

# 自动合成

### 最重要的

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/autocraft_setup_greebles.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

作为手动放置配方的更优解，且避免让你像流水线工人一般重复工作，自动合成是 AE2 的主要功能之一。

你可以让你的ME系统为你代劳，或者自动合成物品并将其导出到某个地方。

亦或是通过某些新兴技术使其自动控制存储空间内的物品的数量。对于流体，甚至你如果拥有一些其他模组中含有的流体，例如 "通用机械" 中的气体，上述的内容也同样适用。

这是一个相当复杂的话题，所以让我们赶紧开始吧。

要想组装一个自动合成系统，你需要准备如下物品：

- 能够发送合成请求的东西
- 合成处理器
- **ME样板供应器**

### 工作流程

1. 某物发送了一个制作请求。这可以是在终端中单击可自动合成的物品、输出总线，或是与制作卡的接口，请求他们设置为要输出/入库的物品之一。

   *（**重要提示：**使用您绑定到"选取方块"（通常是鼠标中键）的键位来请求你已有库存的物品，这可能会与库存管理模组冲突）*

2. ME系统计算满足请求所需的材料和必备的制作步骤，并将其存储在选定的合成CPU中。

3. 装有相关[样板](../items-blocks-machines/patterns.md)的样板供应器会将样板中指定的配方推送到任何相邻的库存中。
   - 在工作台配方（"制作模式"）的情况下，这将是一个分子组装器。
   - 在非制作配方（"加工模式"）的情况下，这将是其他方块、机器或精心制作的红石控制装置。

4. 本次合成的结果以某种方式返回给系统，无论是通过输入总线、接口，还是将成品送回样板供应器。
   **请注意，必须发生一个"物品进入系统"的事件，你不能仅仅通过管道将结果输送到一个带有存储总线的箱子中。**

5. 如果该合成的结果是请求中另一个合成的先决条件，则这些物品将存储在该合成CPU中，然后在本次合成中使用。
   例如：合成木斧需要木板和木棍，那么合成CPU将会先尝试合成这两样物品并存储，再尝试合成木斧。

---

# 样板

<ItemImage id="crafting_pattern" scale="4" />

样板在<ItemLink id="pattern_encoding_terminal" />中由空白样板制作而成。

不同类型的样板适用于不同用途：

* <ItemLink id="crafting_pattern" />用于编码工作台配方。它们可以直接放入<ItemLink id="molecular_assembler" />中，使其在收到材料时自动合成产物，但它们主要用于放在分子组装器旁边的<ItemLink id="pattern_provider" />中。
  样板供应器在这种情况下具有特殊行为，会将相关样板连同材料一起发送到相邻的组装器。
  由于组装器会自动将合成产物弹出到相邻库存，因此只需在样板供应器上放置一个组装器即可实现制作样板的自动化。

***

* <ItemLink id="smithing_table_pattern" />与制作样板非常相似，但用于编码锻造台配方。它们同样由样板供应器和分子组装器自动化，功能完全相同。实际上，制作样板、锻造样板和切石样板可以在同一设置中一起使用。

***

* <ItemLink id="stonecutting_pattern" />与制作样板非常相似，但用于编码切石机配方。它们同样由样板供应器和分子组装器自动化，功能完全相同。实际上，制作样板、锻造样板和切石样板可以在同一设置中一起使用。

***

* <ItemLink id="processing_pattern" />是自动合成灵活性的主要来源。它们是最通用的一种类型，简单来说就是"如果样板供应器将材料推送到相邻库存，ME系统将在不久或遥远的将来收到这些物品"。这是你使用几乎任何模组机器、熔炉等进行自动合成的方式。由于它们在使用上非常通用，不关心在推送材料和收到结果之间发生了什么，你可以做一些非常酷的事情，比如将材料输入整个复杂工厂生产线、从不产原料的农场获取其他材料、甚至打印整部《蜜蜂电影》剧本——只要样板指定了结果，ME系统就不在乎。
  事实上，它甚至不关心材料是否与结果有任何关系。你可以告诉它"1个樱桃木木板 = 1个下界之星"，然后让你的凋零农场在收到樱桃木木板时杀死凋零，这也能正常工作。

多个具有相同样板的<ItemLink id="pattern_provider" />受支持且并行工作。此外，你可以让样板设置为例如8个圆石 = 8个石头（而非1个圆石 = 1个石头），这样样板供应器每次操作会向熔炼装置中插入8个圆石，而非一次一个。

---

## "样板"的最通用形式

实际上还有一种比加工样板更"通用"的"样板"形式。带有合成卡的<ItemLink id="level_emitter" />可以设置为发出红石信号来合成物品。这种"样板"不定义，甚至不关心材料。
  它只说"如果你从这个等级发信器发出红石信号，ME系统将在不久或遥远的将来收到这个物品"。这通常用于激活和关闭不需要输入材料的无限农场，或用于处理递归配方（标准自动合成无法理解）的系统，例如"1个圆石 = 2个圆石"（如果你有一台可以复制圆石的机器）。

---

# 合成CPU

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/crafting_cpus.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

合成CPU管理合成请求/任务。它们存储中间材料，同时执行多步骤的合成任务，并影响任务可以有多大、在一定程度上影响完成速度。它们是多方块结构，必须是至少带有1个合成存储的矩形棱柱。

合成CPU由以下组件构成：

* **（必需）**[合成存储](../items-blocks-machines/crafting_cpu_multiblock.md)，有所有标准元件容量（1k、4k、16k、64k、256k）。它们存储合成中的材料和中间产物，因此处理更多材料的合成任务需要更大或更多的存储。
* **（可选）**<ItemLink id="crafting_accelerator" />，它们使系统从样板供应器发出更多的材料批次。例如，允许样板供应器被6个分子组装器包围，同时向所有6个发送材料并使用它们，而非只使用一个。
* **（可选）**<ItemLink id="crafting_monitor" />，它们显示CPU当前正在处理的任务。可以通过<ItemLink id="color_applicator" />为它们着色。
* **（可选）**<ItemLink id="crafting_unit" />，它们只是填充空间以使CPU成为矩形棱柱。

每个合成CPU处理1个请求或任务，因此如果你想同时请求计算处理器和256个平滑石头，则需要2个CPU多方块。

它们可以设置为处理来自玩家的请求、自动化（输出总线和接口）或两者。

---

# 样板供应器

<Row>
<BlockImage id="pattern_provider" scale="4" />

<BlockImage id="pattern_provider" p:push_direction="up" scale="4" />

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/blocks/cable_pattern_provider.snbt" />
</GameScene>
</Row>

<ItemLink id="pattern_provider" />是自动合成系统与世界互动的主要方式。它们将[样板](../items-blocks-machines/patterns.md)中的材料推送到相邻库存，物品可以插入其中以将其输入网络。
  通常，通过管道将机器输出送回附近的样板供应器（通常是推送材料的那个）可以节省频道，而非使用<ItemLink id="import_bus" />将机器输出拉入网络。

值得注意的是，由于它们直接从合成CPU的[合成存储](../items-blocks-machines/crafting_cpu_multiblock.md#crafting-storage)推送材料，因此它们实际上从不在库存中包含材料，所以你不能从它们管道输出。你必须让供应器推送到另一个库存（如木桶），然后再从那里管道输出。

另一个值得注意的是，供应器必须一次性推送所有材料，不能推送半批次。这可以用来利用。

样板供应器在[子网络](../ae2-mechanics/subnetworks.md)上的接口有特殊交互：如果接口未被修改（请求槽中什么都没有），供应器将完全跳过接口，直接推送到该子网络的[存储](../ae2-mechanics/import-export-storage.md)，跳过接口且不会用配方批次填充它，更重要的是，在存储中有空间之前不会插入下一批次。

多个具有相同样板的样板供应器受支持且并行工作。

样板供应器会尝试轮流向所有面发送批次，从而并行使用所有连接的机器。

## 变体

样板供应器有3种不同的变体：普通、定向和平面。这会影响它们推送材料的具体面、接收物品的面以及提供网络连接的面。

* **普通样板供应器**向所有面推送材料，从所有面接收输入，并且像大多数AE2机器一样，像线缆一样向所有面提供网络连接。

* **定向样板供应器**通过在普通样板供应器上使用<ItemLink id="certus_quartz_wrench" />来改变方向。它们只向所选面推送材料，从所有面接收输入，并且特别不在所选面上提供网络连接。如果你想要创建子网络，这允许它们向AE2机器推送而不连接网络。

* **平面样板供应器**是一种[线缆子部件](../ae2-mechanics/cable-subparts.md)，因此可以多个放置在同一根线缆上，实现紧凑布局。它们的行为类似于定向样板供应器上的所选面，提供样板、接收输入、并且不在其面上提供网络连接。

样板供应器可以在合成网格中切换普通和平面模式。

## 设置

样板供应器有多种模式：

* **阻塞模式**阻止供应器在机器中已有材料时推送新批次。
* **锁定合成**可以在各种红石条件下锁定供应器，或直到上一个合成的结果插入到该特定样板供应器中。
* 可以在<ItemLink id="pattern_access_terminal" />上显示或隐藏供应器。

## 优先级

可以通过点击GUI右上角的扳手来设置优先级。当存在同一物品的多个[样板](../items-blocks-machines/patterns.md)时，优先级较高的供应器中的样板将优先于优先级较低的供应器中的样板使用，除非网络没有更高优先级样板所需的材料。

---

# 分子组装器

<BlockImage id="molecular_assembler" scale="4" />

<ItemLink id="molecular_assembler" />接收输入的物品，执行相邻<ItemLink id="pattern_provider" />或插入的<ItemLink id="crafting_pattern" />、<ItemLink id="smithing_table_pattern" />或<ItemLink id="stonecutting_pattern" />所定义的操作，然后将结果推送到相邻库存。

它们主要用于<ItemLink id="pattern_provider" />旁边。样板供应器在这种情况下具有特殊行为，会将相关样板的信息连同材料一起发送到相邻的组装器。由于组装器会自动将合成产物弹出到相邻库存（从而进入样板供应器的返回槽），因此只需在样板供应器上放置一个组装器即可实现制作样板的自动化。

<GameScene zoom="4" background="transparent">
<ImportStructure src="../assets/assemblies/assembler_tower.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>
