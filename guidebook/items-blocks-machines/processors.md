---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Processors
  icon: logic_processor
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:logic_processor
- ae2:calculation_processor
- ae2:engineering_processor
- ae2:printed_silicon
- ae2:printed_logic_processor
- ae2:printed_calculation_processor
- ae2:printed_engineering_processor
- ae2:silicon
---

# 处理器
处理器是 AE2 [设备](../ae2-mechanics/devices.md)和机器的主要原料之一。它们也是你最早的自动化挑战之一。  
有三种类型的处理器，分别用金、赛特斯石英水晶<ae2:certus_quartz_crystal>和钻石制作。  
它们使用[压印模板](presses.md)在压印器<ae2:inscriber>中通过多步骤工艺制作（通常通过一系列压印器和过滤管道实现）。  

## 制造过程

<Column gap="5">
  1. 收集/制作所需的原料：硅、红石、金、赛特斯石英水晶<ae2:certus_quartz_crystal>、钻石。

  <RecipeFor id="silicon" />

  <br />

  2.  压印必要的电路板组件

  <Row>
    <RecipeFor id="printed_silicon" />

    <RecipeFor id="printed_logic_processor" />
  </Row>

  <Row>
    <RecipeFor id="printed_calculation_processor" />

    <RecipeFor id="printed_engineering_processor" />
  </Row>

  <br />

  3.  最终组装

  <Row>
    <RecipeFor id="logic_processor" />

    <RecipeFor id="calculation_processor" />
  </Row>

  <RecipeFor id="engineering_processor" />
</Column>
