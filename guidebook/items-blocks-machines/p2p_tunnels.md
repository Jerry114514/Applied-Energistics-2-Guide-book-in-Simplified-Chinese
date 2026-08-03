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

# P2P通道

P2P 通道是一种在不直接与网络交互的情况下，在网络中移动物品、流体、红石信号、能量、光和[频道](../ae2-mechanics/channels.md)等东西的方式。P2P 通道有许多变种，但每种只传输其特定类型的东西。它们本质上就像传送门，在远距离直接连接两个方块面。它们不是双向的，有明确的输入端和输出端。 
![P2P传送门](../assets/assemblies/p2p_portal.png)  
例如，面向物品 P2P 的漏斗将表现得如同直接连接到木桶一样，物品会流动。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_hopper_barrel.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

然而，两个并排的木桶不会在彼此之间传输物品。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_barrel_barrel.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

还有其他变种，比如红石 P2P。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_redstone.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

还有ME P2P，可以移动频道。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_channels.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## P2P 通道的类型与调谐

P2P 通道有许多类型。只有 ME P2P 通道可以直接合成，其他类型是通过用特定物品右键点击其他 P2P 通道来制作的：  
- ME P2P 通道：用任意[线缆](../items-blocks-machines/cables.md)右键点击来选择。
- 红石 P2P 通道：用各种红石组件右键点击来选择。
- 物品 P2P 通道：用箱子或漏斗右键点击来选择。
- 流体 P2P 通道：用水桶或瓶子右键点击来选择。
- 能量 P2P 通道：用几乎任何含有能量的物品右键点击来选择。
- 光 P2P 通道：用火把或萤石右键点击来选择。  

有些 P2P 通道类型有一些特殊行为。例如，ME P2P 通道的频道不能穿过其他 ME P2P 通道，而能量 P2P 通道会通过增加其[能量](../ae2-mechanics/energy.md)消耗来间接地对其流经的 FE 或 E 征收5%的“能量税”。

## P2P 最常用的形式

P2P 通道最常见的用途是使用 ME P2P 通道来压缩[频道](../ae2-mechanics/channels.md)传输的密度。  
与其使用一捆致密线缆，不如使用一条致密线缆来携带许多频道。  
在这个例子中，8个 ME P2P 输入从主网络的 ME 控制器<ae2:controller>接收256个频道（8*32），8个 ME P2P 输出将它们输出到其他地方。注意每个 P2P 通道输入或输出占用1个频道。因此我们可以通过一条细线缆运行许多频道。而且由于我们的 P2P 通道位于专用的[子网络](../ae2-mechanics/subnetworks.md)上，我们甚至不占用主网络上的任何频道就能做到这一点！还要注意，虽然 P2P 通道可以直接放置在控制器旁边，但可以在其间放置一条[致密智能线缆](../items-blocks-machines/cables.md#smart-cable)来更容易地可视化频道。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/p2p_compact_channels.snbt" />

  <BoxAnnotation color="#dddddd" min="1.3 1.3 6.3" max="2 2.7 6.7">
        石英纤维在主网络和 P2P 子网络之间共享能量。
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4.1 0 5.7" max="5 2.3 6.4">
        你可以将 P2P 通道输入直接放在控制器上，或者用线缆连接到它。
  </BoxAnnotation>

  <IsometricCamera yaw="225" pitch="30" />
</GameScene>

另一个例子（包括它与[量子桥](quantum_bridge.md)的使用）请看这张我懒得修饰的 MS Paint 示意图：  
![P2P and quantum bridges](../assets/diagrams/p2p_quantum_network.png)  

## 嵌套

然而，你不能用这个来通过一条线缆发送无限频道。  
ME P2P 通道的频道不会穿过另一个 ME P2P 通道，因此你不能递归地嵌套它们。  
注意红色线缆上外层 ME P2P 通道是如何离线的。请注意这仅适用于 ME P2P 通道，其他 P2P 通道类型可以穿过 ME P2P 通道，正如红石 P2P 通道正常工作所见。  

## 链接

P2P 通道连接的端可以使用内存卡<ae2:memory_card>进行链接。频率将显示为通道背面2x2的颜色阵列。  
- Shift 右键点击以生成一个新的 P2P 链接频率。  
- 右键点击以粘贴设置、升级卡或链接频率。  
你 Shift 右键点击的通道将是输入端，你右键点击的通道将是输出端。你可以有多个输出端，但对于 ME P2P 通道，流入输入端的频道将在输出端之间分配，因此你不能复制频道。  

## 配方

<RecipeFor id="me_p2p_tunnel" />