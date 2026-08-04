---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Toggle Bus
  icon: toggle_bus
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:toggle_bus
- ae2:inverted_toggle_bus
---

# ME 触发总线

一种总线，功能类似于福鲁伊克斯色 ME 玻璃线缆<ae2:fluix_glass_cable>或其他线缆，但它允许通过红石切换其连接状态。这允许你切断[ME 网络](../ae2-mechanics/me-network-connections.md)的一部分。  

当收到红石信号时，该部件启用连接；ME 反相触发总线<ae2:inverted_toggle_bus>则提供相反的行为，改为禁用连接。  

值得注意的是，切换这些可能会导致网络重新启动并重新计算已连接的设备。  

它们属于一种[线缆子部件](../ae2-mechanics/cable-subparts.md)。  

## 配方

<RecipeFor id="toggle_bus" />

<RecipeFor id="inverted_toggle_bus" />
