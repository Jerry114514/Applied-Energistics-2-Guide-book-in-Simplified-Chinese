---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Network Connections
  icon: fluix_glass_cable
---

# 网络连接

## "网络"是什么意思？

"网络"是指由能够传递[频道](/ae2-mechanics/channels.md)的方块（如[线缆](/items-blocks-machines/cables.md)或完整方块机器和[设备](/ae2-mechanics/devices.md)）连接起来的一组[设备](/ae2-mechanics/devices.md)（<ItemLink id="charger" />、<ItemLink id="interface" />、<ItemLink id="drive" /> 等）。严格来说，单根线缆本身就是一个网络。

## 关于设备位置的说明

对于具有特定网络功能的[设备](/ae2-mechanics/devices.md)（例如 <ItemLink id="interface" /> 向[网络存储](/ae2-mechanics/import-export-storage.md)推送和拉取物品、<ItemLink id="level emitter" /> 读取网络存储的内容、<ItemLink id="drive" /> 作为网络存储等），设备的物理位置无关紧要。

再次强调，**设备的物理位置无关紧要**。唯一重要的是设备是否连接到了网络（当然，还要看它连接的是哪个网络）。

## 网络连接

判断网络中连接了哪些设备的一种简单方法是使用 <ItemLink id="network tool" />。它会显示网络上的所有组件，因此如果你看到了不该有的东西，或者没看到该有的东西，那就说明有问题了。

例如，这是两个独立的网络：

<GameScene zoom="6" background="transparent">
  <ImportStructure src="/assets/assemblies/2_networks_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        网络 1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="2 0 0" max="3 2 2">
        网络 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

这也是两个独立的网络，因为 <ItemLink id="quartz_fiber" /> 只共享[能量](/ae2-mechanics/energy.md)，而不提供网络连接：

<GameScene zoom="6" background="transparent">
  <ImportStructure src="/assets/assemblies/2_networks_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        网络 1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="1 3 0 0" max="3 2 2">
        网络 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>


这也是两个独立的网络，因为 <ItemLink id="quartz_fiber" /> 只共享[能源](ae2-mechanics/energy.md)，而不提供网络连接。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="assets/assemblies/2_networks_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        网络 1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="1 3 0 0" max="3 2 2">
        网络 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

然而，这只是一个网络，而不是两个独立的网络。[量子网桥](items-blocks-machines/quantum_bridge.md)的作用类似于无线[致密线缆](items-blocks-machines/cables.md#dense-cable)，因此两端位于同一个网络上。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="assets/assemblies/actually_1_network.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="7 3 3">
        全部是 1 个网络
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

这也是同一个网络，因为[线缆](items-blocks-machines/cables.md)的颜色与网络连接无关，只是不同颜色的线缆不会相互连接。所有颜色的线缆都能连接到福鲁伊克斯（或“无色”）线缆。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="assets/assemblies/actually_1_network_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        全部是 1 个网络
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 不太直观的连接

在这种情况下，这只是一个网络，因为<ItemLink id="pattern_provider" />作为一个完整方块设备，其作用类似于线缆，而<ItemLink id="inscriber" />也是如此。因此，网络连接会穿过样板供应器和压印器。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        全部位于一个网络内
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

为了防止这种情况（对于许多涉及[子网络](/ae2-mechanics/subnetworks.md)的自动合成设置很有用），你可以使用<ItemLink id="certus_quartz_wrench" />右键点击样板供应器，使其变为定向模式。在此模式下，它将不会从一侧传递频道。

<Row gap="40">
<GameScene zoom="6" background="transparent">
  <ImportStructure src="/assets/assemblies/pattern_provider_network_connection_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="2 2 2">
        网络 1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="2 0 0" max="4 2 2">
        网络 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="6" background="transparent">
  <ImportStructure src="/assets/assemblies/pattern_provider_directional_connection.snbt" />

  <BoxAnnotation color="#ee3333" min="1 3 3" max="1 7 7">
        注意线缆并未连接
  </BoxAnnotation>

  <IsometricCamera yaw="255" pitch="30" />
</GameScene>
</Row>

其他不提供定向网络连接的部件大多是[子部件](/ae2-mechanics/cable-subparts.md)或[设备](/ae2-mechanics/devices.md)，例如<ItemLink id="import_bus" />、<ItemLink id="storage_bus" />和<ItemLink id="cable_interface" />。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="/assets/assemblies/subpart_no_connection.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>