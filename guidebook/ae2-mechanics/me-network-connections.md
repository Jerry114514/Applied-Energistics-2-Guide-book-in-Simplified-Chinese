---
navigation:
    parent: ae2-mechanics/ae2-mechanics-index.md
    title: 网络连接
    icon: fluix_glass_cable
---

# 网络连接

## "网络"是什么意思？

"网络"是由[设备](../ae2-mechanics/devices.md)和能够传递[频道](../ae2-mechanics/channels.md)的方块（如[线缆](../items-blocks-machines/cables.md)、完整方块机器及[设备](../ae2-mechanics/devices.md)）连接而成的整体。
（<ItemLink id="charger" />、<ItemLink id="interface" />、<ItemLink id="drive" />等）
从技术角度来说，一根单独的线缆也是一个网络。

## 关于设备位置的说明

对于具有特定网络功能的[设备](../ae2-mechanics/devices.md)（如向[网络存储](../ae2-mechanics/import-export-storage.md)推送或拉取物品的<ItemLink id="interface" />、读取网络存储内容的<ItemLink id="level_emitter" />、作为网络存储的<ItemLink id="drive" />等），设备的物理位置并不重要。

再次强调，**设备的物理位置并不重要**。唯一重要的是设备已连接到网络（当然，以及它连接到了哪个网络）。

## 网络连接

查看网络上连接了哪些组件的简便方法是使用<ItemLink id="network_tool" />。它会显示网络上的所有组件，因此如果你看到了不应该存在的东西或没看到应该存在的东西，就说明有问题。

例如，下图展示的是2个独立的网络：

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        网络 1
  </BoxAnnotation>

<BoxAnnotation color="#915dcd" min="2 0 0" max="3 2 2">
        网络 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

下图也是2个独立的网络，因为<ItemLink id="quartz_fiber" />只共享[能量](../ae2-mechanics/energy.md)，而不提供网络连接。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        网络 1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="1.3 0 0" max="3 2 2">
        网络 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

然而，下图只是1个网络，而不是2个独立的网络。[量子网桥](../items-blocks-machines/quantum_bridge.md)的作用类似于无线[致密线缆](../items-blocks-machines/cables.md#dense-cable)，因此两端都在同一个网络上。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="7 3 3">
        全部为1个网络
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

下图也只是1个网络，因为[线缆](../items-blocks-machines/cables.md)颜色与网络连接无关（不同颜色的线缆之间互不连接的情况除外）。所有颜色的线缆都可以连接到萤石（或者说"无色"）线缆。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        全部为1个网络
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 不太直观的连接

在下图中，这只是1个网络，因为<ItemLink id="pattern_provider" />作为完整方块设备，其作用类似于线缆，而<ItemLink id="inscriber" />也有类似功能。因此，网络连接会穿过样板供应器和压印器。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        全部为1个网络
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

若要阻止上述情况的发生（这对于涉及[子网络](../ae2-mechanics/subnetworks.md)的许多自动合成设置非常有用），可以用<ItemLink id="certus_quartz_wrench" />右键点击样板供应器，使其变为定向模式。这样它就不会从某一侧传递频道。

<Row gap="40">
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="2 2 2">
        网络 1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="2 0 0" max="4 2 2">
        网络 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_directional_connection.snbt" />

  <BoxAnnotation color="#ee3333" min="1 .3 .3" max="1.3 .7 .7">
        注意线缆是如何不连接的
  </BoxAnnotation>

  <IsometricCamera yaw="255" pitch="30" />
</GameScene>
</Row>

其他不提供定向网络连接的部件包括大多数[子部件](../ae2-mechanics/cable-subparts.md)[设备](../ae2-mechanics/devices.md)，如<ItemLink id="import_bus" />、<ItemLink id="storage_bus" />和<ItemLink id="cable_interface" />。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/subpart_no_connection.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
