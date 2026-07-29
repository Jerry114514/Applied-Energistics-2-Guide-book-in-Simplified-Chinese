---
navigation:
  title: Tips and Tricks
  position: 20
---

# 提示和技巧

一堆随机的小建议

* 移除 Optifine。

* 您可以旋转和放大具有缩放和 注释隐藏/显示 按钮的指南场景。

* 保持网络以树状结构排布以避免循环。

* 除非您深入了解[频道](ae2-mechanicals/channels.md)的工作原理，否则请以8个或更少数量的设备来组装“设备组”，从而阻止[设备](ae2-mechanicals/devices.md)通过网络路由。

*   为所有样板选择同一种木材，并坚持使用。是的，在样板中启用替代品有时可行，但统一使用同一种木材能大大减少麻烦。

*   为所有[样板](items-blocks-machines/patterns.md)统一选择一种木材。是的，在样板中启用替代物有时可行，但全程使用同一种木材能大大减少麻烦。

*   将你的[样板](items-blocks-machines/patterns.md)在<ItemLink id="pattern_access_terminal" />中垂直排列，或将其分配到各个[样板供应器](items-blocks-machines/pattern-provider.md)之间，以便配方可以并行处理。

*   添加一个[能源元件](items-blocks-machines/energy-cells.md)，让你的网络能够应对能量峰值。

*   你可以在<ItemLink id="condenser" />中使用水。

*   保持网络整洁的最佳方法是不要将随机的怪物掉落物（如剑和盔甲）存入其中。每一种附魔和耐久度的独特组合都会增加一个[类型](ae2-mechanics/bytes-and-types.md)。

*   当[加工样板](items-blocks-machines/patterns.md)的处理结果返回时，必须触发一个“物品进入系统”的事件，例如通过<ItemLink id="import_bus" />、<ItemLink id="interface" />或<ItemLink id="pattern_provider" />的返回槽。你不能仅仅将产物通过管道输入到一个带有<ItemLink id="storage_bus" />的箱子中。

*   别忘了，你可以旋转和缩放指南书中那些带有缩放和注释隐藏/显示按钮的场景。

*   <ItemLink id="pattern_provider" />只会推送完整的配方批次，并且只通过单个面进行。这对于确保机器不会收到不完整的批次非常有用，但有时你可能希望将材料发送到多个地方。你可以使用<ItemLink id="interface" />来实现这一点，既可以将其用作[“管道”子网络](example-setups/pipe-subnet.md)，也可以利用其同时容纳多种不同物品、流体、化学品等的能力，将其用作一种中间箱子/储罐。

*   你可以缩放和旋转指南书中那些带有缩放和注释隐藏/显示按钮的场景。
