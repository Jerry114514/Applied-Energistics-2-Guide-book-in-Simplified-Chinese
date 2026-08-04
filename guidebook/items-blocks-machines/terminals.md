---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Terminals
  icon: crafting_terminal
  position: 210
categories:
- devices
item_ids:
- ae2:terminal
- ae2:crafting_terminal
- ae2:pattern_encoding_terminal
- ae2:pattern_access_terminal
---

# 终端

虽然 ME 样板供应器<ae2:pattern_provider>、ME 输入总线<ae2:import_bus>、ME 存储总线<ae2:storage_bus>等是 AE2 网络与世界交互的主要方式，但终端是 AE2 网络与*你*交互的主要方式。有几种具有不同功能的变体。  

终端会继承它们所安装的[线缆](cables.md)的颜色。  

它们属于一种[线缆子部件](../ae2-mechanics/cable-subparts.md)。  

## 终端放置

由于终端通常是你放置的第一个[子部件](../ae2-mechanics/cable-subparts.md)，常见的错误是放反终端的方向。

# 终端搜索

搜索框接受正则表达式术语，因此你可以例如输入`“gtceu:.*ore”`来获取格雷科技的所有矿石。学习正则表达式留给读者作为练习。

# 终端

你的基础终端，允许你查看和访问你的[网络存储](../ae2-mechanics/import-export-storage.md)的内容，并从你的[自动合成](../ae2-mechanics/autocrafting.md)配置中请求物品。

## UI

基础终端的 UI 有几个部分。  

中心部分提供对你网络存储的访问。你可以放入和取出东西。有几个鼠标/键盘快捷键：  

* 左键点击抓取一组，右键点击抓取半组。
* 如果物品或流体等可以[自动合成](../ae2-mechanics/autocrafting.md)，你绑定到“选取方块”（通常是中键点击）的任何按键都会弹出 UI 以指定要合成的数量。你也可以输入像 `3*64/2` 这样的公式，或输入 `=32` 来只合成达到存储中32个所需的物品数量。
* 按住 Shift 会冻结显示的物品在当前位置，阻止它们在数量变化或新物品进入系统时重新排列。
* 用水桶或其他流体容器右键点击会存入流体，在终端中用空的流体容器左键点击流体则会取出流体。
左侧部分有设置按钮，用于：
* 按不同属性排序，如名称、模组和数量
* 查看已存储、可合成或两者
* 查看物品、流体或两者
* 更改排序顺序
* 打开详细的终端设置窗口
* 更改终端 UI 的高度  

右侧有显示元件<ae2:view_cell>的槽位。  

中心部分的右上角（锤子按钮）打开[自动合成](../ae2-mechanics/autocrafting.md)状态 UI，允许你查看自动合成的进度以及每个[合成 CPU](crafting_cpu_multiblock.md)正在做什么。

## 配方

<RecipeFor id="terminal" />

<a name="crafting-terminal-ui"></a>

# 合成终端

合成终端与普通终端类似，具有所有相同的设置和部分，但增加了一个合成网格，该网格会自动从[网络存储](../ae2-mechanics/import-export-storage.md)中补充材料。Shift 点击输出时要小心！

你应该尽快将你的终端升级为合成终端。

## UI

合成终端具有与普通终端相同的 UI，但中间增加了一个合成网格。
还有2个额外的按钮，用于将合成网格清空到网络存储或你的物品栏中。

## 配方

<RecipeFor id="crafting_terminal" />

<a name="pattern-encoding-terminal-ui"></a>

# ME 样板编码终端

ME 样板编码终端与普通终端类似，具有所有相同的设置和部分，但增加了一个[样板](patterns.md)编码界面。它看起来类似于合成终端的 UI，但这个合成网格实际上不执行合成。  

你应该在拥有合成终端之外再有一个这个。  

## UI

ME 样板编码终端具有与普通终端相同的 UI，并增加了[样板](patterns.md)编码界面。  

样板编码界面有几个部分：  

一个用于插入空白样板<ae2:blank_pattern>的槽位。  
一个用于编码样板的大箭头。  
一个用于已编码样板的槽位。将已经编码的样板放入此槽位以进行编辑，然后点击“编码”箭头。  
右侧有4个标签页，用于在以下样板类型之间切换：  

* 合成
* 处理
* 锻造
* 切石

中央 UI 根据要编码的样板类型而变化：  

* 在合成模式下：
* 左键点击或从 JEI/REI 拖入原料以组成配方。右键点击移除原料。
* 启用替换允许用任意木板类型合成木棍等。这应该只在绝对必要时使用。
* 流体替换允许使用存储的流体代替成桶的流体。
* 你也可以直接从 JEI/REI 配方界面编码样板。
* 在处理模式下：
* 左键点击或右键点击，或从 JEI/REI 拖入原料以指定配方的输入和输出。
* 用流体容器（如水桶或流体储罐）右键点击来将那流体设置为原料，而不是水桶或储罐物品。
* 当手持一组时，左键点击放置整组，右键点击放置1个。左键点击现有的原料组以移除整组，右键点击使该组减少1个。你绑定到“选取方块”（通常是中键点击）的任何按键让你指定物品或流体的精确数量。
* 输出槽位有一个主要输出和空间用于你可能想让自动合成算法知道的任何次要输出。
* 输入和输出槽位都可以滚动，因此你可以拥有81种不同的原料和26个次要输出。
* 你也可以直接从 JEI/REI 配方界面编码样板。
* 锻造和切石模式的 UI 分别类似于锻造台和切石机。
## 配方

<RecipeFor id="pattern_encoding_terminal" />

<a name="pattern-access-terminal-ui"></a>

# ME 样板管理终端

ME 样板管理终端用于解决一个特定问题：在密集的 ME 样板供应器<ae2:pattern_provider>和分子装配室<ae2:molecular_assembler>塔中，你无法物理接触到样板供应器来插入新样板。

此外，也许你很懒，不想穿过你的基地去插入一个[样板](patterns.md)。ME 样板管理终端允许访问网络上的所有样板供应器。  

## UI

这个终端的 UI 与其他所有终端都不同。  

它有终端高度和要显示哪些样板供应器的设置。  

终端中的每一行对应一个特定的样板供应器。  

终端中的样板供应器按它们所连接的方块排序，或按你给它们起的名称排序（在铁砧中或使用名称压印模板<ae2:name_press>）。  

## 配方

<RecipeFor id="pattern_access_terminal" />
