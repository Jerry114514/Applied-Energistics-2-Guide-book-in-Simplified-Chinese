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

# 控制器

<BlockImage id="controller" p:state="online" scale="8" />  

控制器是 [ME 网络](../ae2-mechanics/me-network-connections.md) 的路由枢纽。没有控制器时，网络处于"临时"状态，最多只能连接 8 个使用频道的[设备](../ae2-mechanics/devices.md)。

一个 [ME 网络](../ae2-mechanics/me-network-connections.md) 中不能存在两个控制器。

控制器每面提供 32 个[频道](../ae2-mechanics/channels.md)。

每个控制器方块需要 6 AE/t 来运行。每个控制器方块可存储 8000 AE，因此较大的网络可能需要额外的能源存储。详情请参阅[能源](../ae2-mechanics/energy.md)。

多方块控制器可以相当自由地搭建：

<GameScene zoom="2" background="transparent">
  <ImportStructure src="/assets/assemblies/controllers.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

不过，必须遵守以下几条规则：

1. 一个 [ME 网络](../ae2-mechanics/me-network-connections.md) 中的所有控制器方块必须相连；否则方块会变红。
2. 控制器的尺寸不得超过 7×7×7；否则会变红。
3. 一个控制器最多只能在一个轴向上有 2 个相邻方块；如果某个方块违反此规则，它将被禁用并变红。

<GameScene zoom="2" background="transparent">
  <ImportStructure src="/assets/assemblies/controller_rules.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

只要所有规则都得到遵守并且供电充足，控制器就会发光并循环变色。

右键点击控制器可以打开与 <ItemLink id="network_tool" /> 相同的 GUI。

## 配方

<RecipeFor id="controller" />
