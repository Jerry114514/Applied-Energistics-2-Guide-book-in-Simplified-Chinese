---
navigation:
title: 技巧与窍门
position: 20
---
# 技巧与窍门
一堆零散的小建议
* 移除 Optifine
* 你可以旋转和缩放指南中带有缩放和标注显示/隐藏按钮的场景
* 保持你的网络呈树状，避免回路
* 除非你深入了解[频道](ae2-mechanics/channels.md)如何通过网络路由，否则全方块[设备](ae2-mechanics/devices.md)不要超过8个一组
* 为你的所有[样板](items-blocks-machines/patterns.md)选择一种木材并坚持下去。是的，在样板上启用替换有时能行得通，但处处使用同一种木材类型能大大减少麻烦。
* 在 ME 样板管理终端<ae2:pattern_access_terminal>中垂直排列你的[样板](items-blocks-machines/patterns.md)，并在你的[样板供应器](items-blocks-machines/pattern_provider.md)之间分配样板，以便配方可以并行执行。
* 添加一个[能源元件](items-blocks-machines/energy_cells.md)，以便你的网络能够应对能量尖峰。
* 你可以在物质聚合器<ae2:condenser>中使用水
* 保持网络整洁的最佳方法是不要放入像剑和盔甲这样的随机怪物掉落物。每种独特的附魔和耐久组合都是另一个[类型](ae2-mechanics/bytes-and-types.md)。
* 当返回[处理样板](items-blocks-machines/patterns.md)的结果时，必须发生“物品进入系统”事件，比如通过 ME 输入总线<ae2:import_bus>、ME 接口<ae2:interface>或 ME 样板供应器<ae2:pattern_provider>的返回槽，你不能简单地将结果用管道输入到一个带有 ME 存储总线<ae2:storage_bus>的箱子中。
* 别忘了你可以旋转和缩放指南中带有缩放和标注显示/隐藏按钮的场景
* ME 样板供应器<ae2:pattern_provider>只会推送完整的配方批次，并且只能通过单个面推送。这对于确保机器不会收到不完整的批次非常有用，但有时你希望原料被送到多个地方。你可以使用 ME 接口<ae2:interface>来实现这一点，既可以作为[“管道”子网络](example-setups/pipe-subnet.md)，也可以利用它同时容纳多种不同物品堆叠、流体、化学物质等的能力，将其用作一种中间箱子/储罐。
* 你可以缩放和旋转指南中带有缩放和标注显示/隐藏按钮的场景