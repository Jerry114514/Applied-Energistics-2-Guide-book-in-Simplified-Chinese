---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Quantum Bridge
  icon: quantum_ring
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:quantum_link
- ae2:quantum_ring
---

# 量子网桥

![一个已成型的量子网桥](../assets/diagrams/quantum_bridge_demonstration.png)  

量子网桥可以将[网络](../ae2-mechanics/me-network-connections.md)扩展到无限远的距离，甚至跨维度。  
它们总共可以承载32个频道（无论线缆如何连接到每个面），本质上就像一个无线[致密线缆](cables.md#dense-cable)。  

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/quantum_bridge_internal_structure_1.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/quantum_bridge_internal_structure_2.snbt" />

  <BoxAnnotation color="#33dd33" min="1 1 1" max="6 2 3">
        两个端点之间的一条虚拟线缆
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

需要注意的是，**两端的区块都必须被加载**，因此如果两侧相距很远，必须使用空间锚<ae2:spatial_anchor>或其他区块加载器。
Carpet模组当中的`FakePlayer`也算是其中一种。

# 量子环

将8个这样的方块围绕着一个量子链接仓<ae2:quantum_link>放置，就会创建一个量子网桥。  
只有与量子链接仓<ae2:quantum_link>相邻的4个量子环<ae2:quantum_ring>方块会接受网络连接，4个角落的方块不能连接线缆。  

## 配方

<RecipeFor id="quantum_link" />
