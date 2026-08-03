---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Patterns
  icon: crafting_pattern
  position: 410
categories:
- tools
item_ids:
- ae2:blank_pattern
- ae2:crafting_pattern
- ae2:processing_pattern
- ae2:smithing_table_pattern
- ae2:stonecutting_pattern
---

# 样板

样板是在 ME 样板编码终端<ae2:pattern_encoding_terminal>中用空白样板制作的，并插入到 ME 样板供应器<ae2:pattern_provider>或分子装配室<ae2:molecular_assembler>中。  

有几种不同类型的样板用于不同用途：  
* 合成样板<ae2:crafting_pattern>编码工作台制作的配方。它们可以直接放入分子装配室<ae2:molecular_assembler>中，使其在给定原料时合成结果，但它们的主要用途是放在分子装配室旁边的 ME 样板供应器<ae2:pattern_provider>中。在这种情况下，样板供应器有特殊行为：它们会将相关样板连同原料一起发送给相邻的分子装配室。由于分子装配室会自动将合成结果弹出到相邻的容器中，所以在样板供应器旁放一个分子装配室就足以自动化合成样板。

***

* 锻造台样板<ae2:smithing_table_pattern>与合成样板非常相似，但它们编码锻造台配方。它们也由样板供应器和分子装配室自动化，并且功能完全相同。事实上，合成、锻造和切石样板可以在同一个配置中使用。

***

* 切石机样板<ae2:stonecutting_pattern>与合成样板非常相似，但它们编码切石机配方。它们也由样板供应器和分子装配室自动化，并且功能完全相同。事实上，合成、锻造和切石样板可以在同一个配置中使用。

***

* 处理样板<ae2:processing_pattern>是自动合成中大量灵活性的来源。  
它们是最通用的类型，简单地说“如果样板供应器将这些原料推送到相邻的容器中，ME 系统将在不久或遥远的将来收到这些物品”。  

这就是你如何用几乎任何模组机器、熔炉等自动化合成的方式。由于它们使用非常通用，不关心推送原料和接收结果之间发生了什么，你可以做一些非常奇特的事情，比如将原料输入到整个复杂的工厂生产链中，它会整理东西、从无限生产的农场中获取其他原料、打印整个《蜜蜂总动员》剧本，只要 ME 系统得到样板指定的结果，它都不在乎。事实上，它甚至不关心原料是否与结果有任何关系。你可以告诉它“1个樱桃木木板 = 1个下界之星”，然后让你的凋灵农场在收到一个樱桃木木板时杀死一只凋灵，这样就能工作。  

多个具有相同样板的 ME 样板供应器<ae2:pattern_provider>是受支持的，并且可以并行工作。此外，你可以让样板指定，例如，8个圆石 = 8个石头，而不是1个圆石 = 1个石头，这样样板供应器每次操作都会将8个圆石插入你的烧炼设定组，而不是一次一个。

## 配方

<RecipeFor id="blank_pattern" />
