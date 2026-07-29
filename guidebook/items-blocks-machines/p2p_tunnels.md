---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: P2P Tunnels
  icon: me_p2p_tunnel
  position: 210
categories:
- devices
item_ids:
- ae2:me_p2p_tunnel
- ae2:redstone_p2p_tunnel
- ae2:item_p2p_tunnel
- ae2:fluid_p2p_tunnel
- ae2:fe_p2p_tunnel
- ae2:light_p2p_tunnel
---

# P2P隧道

<GameScene zoom="6" background="transparent">
  <ImportStructure src="/assets/assemblies/p2p_tunnels.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

P2P 隧道是一种在网络中传输物品、流体、红石信号、能量、光线以及[频道](/ae2-mechanics/channels.md)的方式，且这些内容不会直接与网络交互。P2P 隧道有许多变种，但每种只传输其特定类型的事物。它们本质上就像传送门，能在一定距离内直接连接两个方块面。它们不是双向的，有明确的输入和输出。

![传送门](/assets/assemblies/p2p_portal.png)

例如，对准物品 P2P 的漏斗会表现得像直接连接到了木桶上，物品会流动。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="/assets/assemblies/p2p_hopper_barrel.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

然而，两个相邻的木桶之间不会互相传输物品。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="/assets/assemblies/p2p_barrel_barrel.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

还有其他变种，比如红石 P2P。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="/assets/assemblies/p2p_redstone.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## P2P 隧道的类型与调谐

<GameScene zoom="6" background="transparent">
  <ImportStructure src="/assets/assemblies/p2p_tunnels.snbt" />
  <IsometricCamera yaw="180" pitch="90" />
</GameScene>

P2P 隧道有很多类型。只有 ME P2P 隧道可以直接合成，其他类型需要通过手持特定物品右键点击 P2P 隧道来转换：
- 手持任意[线缆](/items-blocks-machines/cables.md)右键点击可转换为 ME P2P 隧道。
- 手持各种红石元件右键点击可转换为红石 P2P 隧道。
- 手持箱子或漏斗右键点击可转换为物品 P2P 隧道。
- 手持桶或瓶子右键点击可转换为流体 P2P 隧道。
- 手持几乎任何含能量物品右键点击可转换为能量 P2P 隧道。
- 手持火把或荧石右键点击可转换为光线 P2P 隧道。

某些隧道类型有特殊机制。例如，ME P2P 隧道的频道不能穿过其他 ME P2P 隧道；能量 P2P 隧道会通过增加自身的[能量](/ae2-mechanics/energy.md)消耗，间接对流经自身的 FE 或 E 抽取 5% 的能量“税”。

## P2P 最常用的形式

P2P 隧道最常见的用途是使用 ME P2P 隧道来压缩[频道](/ae2-mechanics/channels.md)传输的密度。与其用一捆致密线缆，不如用一根致密线缆来承载大量频道。

在这个例子中，8 个 ME P2P 输入端从主网络的 <ItemLink id="controller" /> 获取 256 个频道（8×32），8 个 ME P2P 输出端将它们输出到其他地方。注意每个 P2P 隧道输入端或输出端占用 1 个频道。这样我们就可以通过一根细线缆传输大量频道。而且由于我们的 P2P 隧道位于专用的[子网络](/ae2-mechanics/subnetworks.md)上，我们甚至没有消耗主网络的任何频道！还要注意，虽然 P2P 隧道可以直接贴在控制器上，但中间可以放置一根[致密智能线缆](/items-blocks-machines/cables.md#smart-cable)来更方便地观察频道。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="/assets/assemblies/p2p_compact_channels.snbt" />

  <BoxAnnotation color="#dddddd" min="1 3 1 3 6 3" max="2 2 7 6 7">
        石英纤维在主网络和 P2P 子网络之间共享能量
  </BoxAnnotation>

  <IsometricCamera yaw="225" pitch="30" />
</GameScene>

另一个例子（包括与[量子网桥](quantum-bridge.md)的配合使用）请看这张我懒得再修的 MS Paint 示意图：

![P2P 与量子网桥](/assets/diagrams/p2p_quantum_network.png)

## 嵌套

但是，你不能用这种方法通过一根线缆发送无限频道。ME P2P 隧道的频道不会穿过另一个 ME P2P 隧道，所以你不能递归地嵌套它们。注意红色线缆上的外层 ME P2P 隧道处于离线状态。请注意，这仅适用于 ME P2P 隧道，其他类型的 P2P 隧道可以穿过 ME P2P 隧道，正如红石 P2P 隧道正常工作所示。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="/assets/assemblies/p2p_nesting.snbt" />
  <IsometricCamera yaw="225" pitch="30" />
</GameScene>

## 链接

<GameScene zoom="6" background="transparent">
  <ImportStructure src="/assets/assemblies/p2p_linking_frequency.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

P2P 隧道连接的两端可以使用 <ItemLink id="memory_card" /> 进行链接。链接频率会以 2×2 的颜色阵列显示在隧道背面。
- 按住 Shift 右键点击可生成新的 P2P 链接频率。
- 右键点击可粘贴设置、升级卡或链接频率。

你按住 Shift 右键点击的隧道将成为输入端，右键点击的隧道将成为输出端。你可以有多个输出端，但对于 ME P2P 隧道，输入端的频道会在输出端之间分配，因此你不能复制频道。

## 配方

<RecipeFor id="me_p2p_tunnel" />