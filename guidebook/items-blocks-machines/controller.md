---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Controller
  icon: controller
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:controller
---

# ME 控制器

ME 控制器是[ME 网络](../ae2-mechanics/me-network-connections.md)的路由枢纽。  

没有它，网络就是“无控的临时网络(ad-hoc)”，最多只能有8个使用频道的[设备](../ae2-mechanics/devices.md)。  

一个[ME 网络](../ae2-mechanics/me-network-connections.md)中不可能有2个控制器。  

控制器每个面提供32个[频道](../ae2-mechanics/channels.md)。  

控制器每个方块需要6 AE/t 才能运行。每个控制器方块可以存储8000 AE，因此更大的网络可能需要额外的能量存储。详情请参阅[能量](../ae2-mechanics/energy.md)。
  
多方块控制器可以以相当自由的形式构建。  

然而，必须遵循一些规则：
1. 所有[ME 网络](../ae2-mechanics/me-network-connections.md)上的控制器方块必须连接；否则方块会变红。  
2. 控制器的尺寸必须在7x7x7以内；否则会变红。  
3. 一个控制器在最多1个轴上可以有2个相邻方块；如果方块违反此规则，它将被禁用并变红。  
只要所有规则都得到遵守并且供电，控制器就应该发光并循环变色。  
你可以右键点击控制器，获得与网络工具<ae2:network_tool>相同的 GUI。  

## 配方

<RecipeFor id="controller" />
