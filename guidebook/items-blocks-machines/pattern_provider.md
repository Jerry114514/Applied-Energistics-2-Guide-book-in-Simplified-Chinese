---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Pattern Provider
  icon: pattern_provider
  position: 210
categories:
- devices
item_ids:
- ae2:pattern_provider
- ae2:cable_pattern_provider
---

# ME 样板供应器

样板供应器是你的[自动合成](../ae2-mechanics/autocrafting.md)系统与世界交互的主要方式。  
它们将[样板](patterns.md)中的原料推送到相邻的容器中，物品也可以被插入到它们中以插入网络。  
通常可以通过将机器的输出管回附近的样板供应器（通常是推送原料的那个）来节省一个频道，而不是使用 ME 输入总线<ae2:import_bus>将机器的输出拉入网络。  

值得注意的是，由于它们直接从合成 CPU 中的[合成存储](crafting_cpu_multiblock.md#crafting-storage)推送原料，它们的库存中实际上从不包含原料，因此你不能从它们中管出物品。你必须让样板供应器推送到另一个容器（如木桶），然后再从那个容器管出。
还要注意，样板供应器必须一次推送所有原料，它不能推送半批。这值得好好利用。  

样板供应器与[子网络](../ae2-mechanics/subnetworks.md)上的接口有一个特殊的互动：如果接口未被修改（请求槽位中没有任何内容），样板供应器将完全跳过该接口，直接推送到该子网络的[存储](../ae2-mechanics/import-export-storage.md)，跳过接口而不是用配方批次填满它，更重要的是，直到机器中有空间之前不会插入下一批。  

这在阻塞模式下能正常工作，样板供应器会监控机器中的槽位是否有原料，而不是接口中的槽位。  
例如，这个配置会将要烧炼的物品和燃料直接推送到熔炉中对应的槽位。  
你可以用这个来样板供应到一台机器的多个面，或多台机器。  

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/furnace_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        （1）ME 样板供应器：使用赛特斯石英扳手切换为定向变体，并放入相关的处理样板。  

        ![Iron Pattern](../assets/diagrams/furnace_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        （2）ME 接口：保持默认配置。
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="1.3 2 1">
        （3）存储总线 #1：过滤为煤炭。
        <ItemImage id="minecraft:coal" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 2 0" max="1 2.3 1">
        （4）存储总线 #2：使用反相卡过滤为黑名单煤炭。
        <Row><ItemImage id="minecraft:coal" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        连接到主网络
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

这是一个样板供应到多台机器的通用示意图。

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        ME 接口（必须是面板形式，不能是完整方块）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        存储总线
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        你想要样板供应到的位置
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

多个具有相同样板的样板供应器是受支持的，并且可以并行工作。  

样板供应器会尝试将批次轮询分配到它们的所有面，从而并行使用所有已连接的机器。

## 变体

样板供应器有3种不同的变体：普通、定向和面板/[子部件](../ae2-mechanics/cable-subparts.md)。这会影响它们将原料推送到哪些特定面、从哪些面接收物品，以及提供网络连接到哪些面。  

* 普通样板供应器将原料推送到所有面，从所有面接收输入，并且像大多数 AE2 机器一样，像线缆一样为所有面提供[网络连接](../ae2-mechanics/me-network-connections.md)。

* 定向样板供应器是通过对普通样板供应器使用赛特斯石英扳手<ae2:certus_quartz_wrench>来改变其方向制成的。它们只将原料推送到选定的面，从所有面接收输入，并且特别在选定的面上不提供[网络连接](../ae2-mechanics/me-network-connections.md)。如果你想要制作子网络，这允许它们向 AE2 机器推料而不连接网络。

* 面板样板供应器属于一种[线缆子部件](../ae2-mechanics/cable-subparts.md)，因此多个可以放置在同一条线缆上，从而实现紧凑布局。它们的行为类似于定向样板供应器上选定的面，提供样板、接收输入，并且在它们的面上**不**提供[网络连接](../ae2-mechanics/me-network-connections.md)。  
样板供应器可以在合成网格中在普通和面板之间切换。  

## 设置

样板供应器有多种模式：
* **阻塞模式**：如果机器中已经有原料，则阻止样板供应器推送新一批原料。
* **锁定合成**：可以在各种红石条件下锁定样板供应器，或者直到前一次合成的结果被插入到该特定样板供应器中。
* 样板供应器可以在 ME 样板管理终端<ae2:pattern_access_terminal>上显示或隐藏。  

## 优先级
优先级可以通过点击 GUI 右上角的扳手来设置。对于同一个物品有多个[样板](patterns.md)时，较高优先级样板供应器中的样板将优先于较低优先级样板供应器中的样板，除非网络没有较高优先级样板的原料。

## 一个常见的误解

出于某种原因人们总是这样做，我不明白为什么，但我把它放在这里希望能有所帮助。（也许人们误以为 ME 输出总线<ae2:export_bus>是物品离开网络的唯一方式，不知道样板供应器也可以导出东西）  
这不会达到你想要的效果。正如在[线缆](cables.md)中提到的，线缆不是物品管道，它们没有内部库存，样板供应器不会推送到它们中。

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_1.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        不是高炉
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

Since the provider doesn't have anything to push to, it will
not be able to function. All it's doing here is acting like a cable, connecting the <ItemLink id="export_bus" /> to the
network.

The provider will also not somehow tell the <ItemLink id="export_bus" /> what to export, the export bus will just export
everything you put in its filter.

What we've essentially done here is this:

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_2.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        Not A Blast Furnace
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

Likely what you would actually want to make is this, where the pattern provider can export the contents of its patterns to
the adjacent machine:

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_3.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        不是高炉
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

## 与分子装配室一同使用

分子装配室<ae2:molecular_assembler>就像任何其他机器一样。它们有一个可以插入物品的库存，然后对库存中的东西执行操作，然后像许多机器一样，将结果推送到相邻的容器中。  

因此，它们应该像任何其他机器一样与样板供应器搭配使用，但有一个额外功能：  
分子装配室可以从插入到其中的合成样板<ae2:crafting_pattern>、锻造台样板<ae2:smithing_table_pattern>或切石机样板<ae2:stonecutting_pattern>中获取所需的样板。  

这在装配线中很有用，但如果每个合成配方都要一个专用的分子装配室，那会非常烦人。  
因此，样板供应器对分子装配室有一个特殊功能：它们可以随原料一起发送样板数据。  
这样，你只需在样板供应器旁边放一个分子装配室，样板供应器就可以将其用于其所有的合成、锻造和切石样板。  
就是这么简单，只需将样板放入样板供应器中：  
*注意这里正好有8个样板供应器，这是可以路由通过单个分子装配室、样板供应器或非致密线缆的最大频道数。*  

<RecipeFor id="pattern_provider" />

<RecipeFor id="cable_pattern_provider" />
