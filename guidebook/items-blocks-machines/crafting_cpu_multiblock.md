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

合成 CPU 管理合成请求/任务。它们会在执行多步骤合成任务时存储中间原料，影响任务的最大规模，并在一定程度上影响任务完成的速度。更多细节请参阅[自动合成](../ae2-mechanics/autocrafting.md)。  

每个合成 CPU 处理1个请求或任务，因此如果你想同时请求一个运算处理器和256个平滑石头，你需要2个 CPU 多方块结构。
它们可以设置为处理来自玩家、自动化（输出总线和接口）或两者的请求。  

右键点击一个 CPU 会打开一个合成状态 UI，你可以在其中查看该 CPU 正在处理的合成任务的进度。  

## 设置

* CPU 可以设置为仅接受来自玩家的请求、仅接受来自自动化的请求（如带有合成卡<ae2:crafting_card>的 ME 输出总线<ae2:export_bus>），或同时接受两者的请求。

## 构建

合成 CPU 是多方块结构，必须是实心的长方体，不能有缺口。它们由几个组件构成。  
每个 CPU 必须包含至少1个合成存储方块（而最小可行的 CPU 实际上只是一个单独的1k 合成存储）。

# Crafting Unit

<BlockImage id="crafting_unit" scale="4" />

(Optional) Crafting units simply fill space in a CPU in order to make it a solid rectangular prism, if you don't have enough
of the other components. They are also a base ingredient in the other components.

<RecipeFor id="crafting_unit" />

# 合成存储

（必需）合成存储提供所有标准元件尺寸（1k、4k、16k、64k、256k）。它们存储合成过程中涉及的原料和中间原料，因此 CPU 需要更大或更多的存储来处理包含更多原料的合成任务。

# 合成并行处理单元

（可选）合成并行处理单元通过让 CPU 的 tick 速度更快，使系统更频繁地从 ME 样板供应器<ae2:pattern_provider>发送原料批次。  

这使得它们能够跟上处理速度快的机器。一个例子是，一个被分子装配室<ae2:molecular_assembler>包围的样板供应器能够比单个分子装配室处理得更快地推送原料，从而将原料批次分配给周围的分子装配室。  
一些复杂的配方有多个可以并行执行的步骤，比如同时制作木板和书来制作书架。在合成状态界面（通过右键点击 CPU 或点击[终端](terminals.md)中的锤子图标可见）中，这些步骤都会显示为“已计划”。每个额外的并行处理单元允许这些步骤中多一个并行执行（从而显示为“正在合成”）。  
然而，这并不是那么重要，因为你通常会有更多的并行处理单元纯粹为了插入速度，而不是配方中可能并行执行的步骤数。

# 合成监控器

（可选）合成监控器显示 CPU 当前正在处理的任务。
屏幕可以使用染色器<ae2:color_applicator>进行染色。
