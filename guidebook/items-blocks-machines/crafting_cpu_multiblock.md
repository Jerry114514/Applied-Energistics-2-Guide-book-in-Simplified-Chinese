---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Crafting CPU Multiblock (Storage, Coprocessor, Monitor, Unit)
  icon: 1k_crafting_storage
  position: 210
categories:
- devices
item_ids:
- ae2:1k_crafting_storage
- ae2:4k_crafting_storage
- ae2:16k_crafting_storage
- ae2:64k_crafting_storage
- ae2:256k_crafting_storage
- ae2:crafting_accelerator
- ae2:crafting_monitor
- ae2:crafting_unit
---

# 合成 CPU

<Game Scene zoom ="4" background ="transparent ">
  <Import Structure src ="  /assets /assemblies /crafting cpus snbt " />
  <Isometric Camera yaw ="195" pitch ="30" />
</Game Scene >

<Row >
  <Block Image id ="1k crafting storage " scale ="4" />

  <Block Image id ="crafting accelerator " scale ="4" />

  <Block Image id ="crafting monitor " scale ="4" />

  <Block Image id ="crafting unit " scale ="4" />
</Row >

合成 CPU 负责管理合成请求/任务。在执行多步骤合成任务时，它们会存储中间产物，并影响大型任务的处理能力，在一定程度上也影响完成速度。更多详情请参阅[自动合成](../ae2-mechanics/autocrafting.md)。

每个合成 CPU 只能处理 1 个请求或任务，因此如果你想同时请求一个计算处理器和 256 个平滑石，就需要 2 个 CPU 多方块结构。

它们可以设置为处理来自玩家、自动化设备（输出总线和接口）或两者的请求。

右键点击可打开合成状态界面，你可以在其中查看该 CPU 正在处理的合成任务的进度。

## 设置

*   CPU 可以设置为仅接受来自玩家的请求、仅接受自动化设备（如装有<Item Link id ="crafting card" />的<Item Link id ="export bus" />）的请求，或同时接受两者。

## 构建

合成 CPU 是多方块结构，必须构成实心长方体，不能有缺口。它们由多种组件构成。

每个 CPU 必须包含至少 1 个合成存储方块（最小可行的 CPU 实际上只是一个 1k 合成存储）。

# 合成单元

<Block Image id ="crafting unit " scale ="4" />

（可选）合成单元仅用于填充 CPU 中的空间，使其成为实心长方体——如果你没有足够的其他组件的话。它们也是其他组件的基础材料。

<Recipe For id ="crafting unit" />

# 合成存储

<Row >
  <Block Image id ="1k crafting storage " scale ="4" />

  <Block Image id ="4k crafting storage " scale ="4" />

  <Block Image id ="16k crafting storage " scale ="4" />

  <Block Image id ="64k crafting storage " scale ="4" />

  <Block Image id ="256k crafting storage " scale ="4" />
</Row >

（必需）合成存储提供所有标准元件规格（1k、4k、16k、64k、256k）。它们存储合成过程中涉及的原料和中间产物，因此处理包含更多原料的合成任务时，需要更大或更多的存储。

<Column >
  <Row >
    <Recipe For id ="1k crafting storage" />

    <Recipe For id ="4k crafting storage" />

    <Recipe For id ="16k crafting storage" />
  </Row >

  <Row >
    <Recipe For id ="64k crafting storage" />

    <Recipe For id ="256k crafting storage" />
  </Row >
</Column >

# 合成协处理单元

<Block Image id ="crafting accelerator " scale ="4" />

（可选）合成协处理器能让系统更频繁地从<Item Link id ="pattern provider" />发送原料批次，从而跟上处理速度较快的机器。例如，当样板供应器周围环绕着<Item Link id ="molecular assembler" />时，协处理器能让原料推送速度超过单个组装器的处理速度，从而将原料批次分配到周围的多个组装器中。

<Recipe For id ="crafting accelerator" />

# 合成监视器

<Block Image id ="crafting monitor " scale ="4" />

（可选）合成监视器会显示该 CPU 当前正在处理的任务。可以使用<Item Link id ="color applicator" />为其屏幕染色。

<RecipeFor id="crafting_monitor" />
