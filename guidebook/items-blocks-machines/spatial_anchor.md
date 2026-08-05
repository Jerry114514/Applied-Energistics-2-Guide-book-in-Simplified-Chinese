---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Spatial Anchor
  icon: spatial_anchor
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:spatial_anchor
---

# 空间锚

AE2 网络需要被加载区块，其任何[设备](../ae2-mechanics/devices.md)才能正常工作，如果只有部分被加载，可能无法正确运行。空间锚解决了这个问题。它会强制加载其网络所占据的区块。  

一条延伸过区块边界的线缆就足以加载那个新区块。  

它会将“加载”效果传播到[量子网桥](quantum_bridge.md)上，但不能跨维度传播，所以如果你有一个通往地狱的量子网桥，你需要在主基地的网络和地狱的网络中各放一个空间锚。  

默认情况下，它还会在其加载的区块中启用随机刻，这可以在 AE2 配置中关闭。  

如果出于某种原因你想旋转它，可以使用赛特斯石英扳手<ae2:certus_quartz_wrench>。  

## 设置

* 空间锚提供用于以 AE 或 E/FE 查看能量的全局设置。
* 可以显示一个世界中的全息图来展示正在加载的区块。  

## 能量

空间锚会根据以下公式使用[能量](../ae2-mechanics/energy.md)：  

e = 80 + (x\*(x+1))/2  

其中 x 是被加载的区块数。  

空间锚的耗电公式是：总耗电 = 80 + (区块数 × (区块数 + 1)) / 2。它有 80 AE/t 的基础起步价，然后每多加载一个区块，额外耗电都会比上一个区块更高，而且涨得越来越快——因为这部分是按平方级增长的。  

举个简单的例子：  
加载 1 个区块时，总能耗为 80 + 1 = 81 AE/t。  
加载 8 个区块时，总能耗为 80 + 36 = 116 AE/t。  
加载 64 个区块时，总能耗为 80 + 2080 = 2160 AE/t。  
加载 128 个区块时，总能耗为 80 + 8256 = 8336 AE/t。  

由此可见，加载少量区块时能耗非常低廉，但随着区块数增加，能耗会急剧飙升。少加载省钱，多加载烧钱，越往后越不划算。  

## 配方

<RecipeFor id="spatial_anchor" />
