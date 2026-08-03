---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Molecular Assembler
  icon: molecular_assembler
  position: 310
categories:
- machines
item_ids:
- ae2:molecular_assembler
---

# 分子装配室

分子装配室接收输入到其中的物品，并执行由相邻的 ME 样板供应器<ae2:pattern_provider>所定义的操作，或者执行插入的合成样板<ae2:crafting_pattern>、锻造台样板<ae2:smithing_table_pattern>或切石机样板<ae2:stonecutting_pattern>所定义的操作，然后将结果推送到相邻的容器中。  
这个分子装配室有一个合成样板，指定了1个橡木原木 = 4个橡木木板 的配方。当橡木原木被送入上方的漏斗时，分子装配室会合成并将橡木木板吐入下方的漏斗。

## 分子装配室的主要用途

然而，它们的主要用途是放在 ME 样板供应器<ae2:pattern_provider>旁边。在这种情况下，样板供应器有特殊行为：它们会将相关样板的信息连同原料一起发送给相邻的分子装配室。由于分子装配室会自动将合成结果弹出到相邻的容器中（从而进入样板供应器的返回槽位），所以在样板供应器旁放一个分子装配室就足以自动化合成样板。  

## 升级

分子装配室支持以下[升级](upgrade_cards.md)：
* 加速卡<ae2:speed_card>

## 配方

<RecipeFor id="molecular_assembler" />

## 注意

Optifine 会破坏“推送到相邻容器”的功能，因此大多数带有分子装配室的合成配置将无法工作。