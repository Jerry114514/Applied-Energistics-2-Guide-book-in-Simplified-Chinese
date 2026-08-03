---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Network Tool
  icon: network_tool
  position: 410
categories:
- tools
item_ids:
- ae2:network_tool
---

# 网络工具

网络工具是一种改进的[扳手](wrench.md)，它还能显示网络诊断信息，并且可以存储[升级卡](upgrade_cards.md)。  
虽然它保留了扳手快速拆卸物品和从线缆上拉下[子部件](../ae2-mechanics/cable-subparts.md)的能力，但它不能旋转物品。  
它有9个槽位用于存储[升级卡](upgrade_cards.md)，如果工具在你的物品栏中任何位置，这些升级卡将在任何 AE2 设备 UI 中可用。  
右键点击网络的任何部分将显示一个诊断信息窗口，类似于右键点击 ME 控制器<ae2:controller>。  

此窗口显示：
* 网络上正在使用的频道数量
* 一个开关，用于全局设置以 AE 或 E/FE 查看能量
* 网络中存储的[能量](../ae2-mechanics/energy.md)数量，以及网络的最大能量容量
* 进入网络和被网络使用的能量数量
* 网络上所有[设备](../ae2-mechanics/devices.md)和组件的列表  

此窗口在摆弄[子网络](../ae2-mechanics/subnetworks.md)时，也有助于判断两条不同的线缆或设备是否属于同一个网络。

## 隐藏线缆伪装板

手持网络工具时，[线缆伪装板](facades.md)将被隐藏。  
你可以与隐藏的线缆伪装板后面的方块进行交互，而无需先移除线缆伪装板。  

## 配方

<RecipeFor id="network_tool" />
