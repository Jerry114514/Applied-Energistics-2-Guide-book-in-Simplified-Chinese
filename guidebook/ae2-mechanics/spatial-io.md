---
AIGC:
    ContentProducer: Minimax Agent AI
    ContentPropagator: Minimax Agent AI
    Label: AIGC
    ProduceID: 3181bf8e800be50689fd61e50d623ed7
    PropagateID: 3181bf8e800be50689fd61e50d623ed7
    ReservedCode1: 304402200220892c102e963fa4c0be13dee4330507eab36e2ee4fa1137e4222e890c8d50022072fa706683d8332e3988d9709c1d083265374f55650978758a726bfe79aad4c0
    ReservedCode2: 30440220319287e76ccd4f335104425dfe40ef73f078ea09eb6b9038afc1b9a1fda7de9602207d24312f860f2c0c8d2cba4a383220c81e0a27ef80cdfac0eafa50fd95a43993
navigation:
    icon: spatial_storage_cell_2
    parent: ae2-mechanics/ae2-mechanics-index.md
    title: 跨空间IO
---

# 跨空间IO

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/spatial_storage_1x1x1.snbt" />

  <BoxAnnotation color="#33dd33" min="1 1 1" max="2 2 2">
        将被移动的体积
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />

</GameScene>

跨空间IO是一种剪切-粘贴世界中物理体积的方法。它可以用来移动<ItemLink id="flawless_budding_quartz" />、在你的基地中设置一个可以切换各种内部装饰的房间以用于不同目的，甚至可以移动末地传送门！

它的工作原理是将定义的体积与跨空间存储维度中相同大小的体积进行*交换*，将塔阵列中的物品发送到跨空间存储维度，并将维度中的物品发送到塔阵列。

这意味着如果你有维度间旅行的方法（跨空间IO*可以*用来制作传送门，但这非常复杂，有点别扭，且超出了本指南的范围），你可以像使用自定义大小的紧凑机器或口袋维度一样使用它们。

---

# 多方块设置

跨空间IO需要特定排列的组件才能工作，并定义要剪切-粘贴的体积。

所有组件必须位于同一[网络](me-network-connections.md)上才能工作，并且一个网络上只能有一个跨空间IO设置。因此，建议使用[子网络](subnetworks.md)。

## 跨空间IO端口

<BlockImage id="spatial_io_port" p:powered="true" scale="4" />

<ItemLink id="spatial_io_port" />控制跨空间IO操作。它显示多方块设置的统计信息，并容纳[空间元件](../items-blocks-machines/spatial_cells.md)

它显示：
- 网络中存储的和最大的[能量](energy.md)
- 执行操作所需的能量。这可能非常大且是瞬时使用的，因此请确保你有足够的[能源元件](../items-blocks-machines/energy_cells.md)来容纳所有能量
- 塔阵列的效率
- 定义的体积大小

要执行跨空间IO操作，将空间存储元件放入输入槽，并向跨空间IO端口发送红石脉冲。
然后它将塔中的体积与跨空间存储维度中的体积进行*交换*。这意味着如果你将一组方块发送到跨空间存储维度，*然后在塔中放置另一组方块*，将元件放回输入槽，并再次触发IO端口，第二组方块将消失，第一组方块将重新出现。

**请小心，被定义体积中的任何实体（包括你自己）都将被携带同行，如果你没有办法出去，你将被困在跨空间存储维度中的一个黑暗、无特征的盒子中。** 用这个来恶作剧你的朋友吧！

## 塔

<BlockImage id="spatial_pylon" p:powered_on="true" scale="4" />

<ItemLink id="spatial_pylon" />是跨空间IO设置的主要部分，并定义要影响的体积。

体积由塔外部的边界框定义，在所有方向上向内收缩1个方块。

规则如下：
- 最小尺寸为3x3x3（定义1x1x1体积）
- 所有空间塔必须位于外部边界框内
- 所有空间塔必须在同一网络上
- 所有塔必须至少2个方块长

例如，假设你想定义一个3x3x3体积。根据规则2，所有塔必须在你想要定义的体积周围的5x5x5外壳内。它们几乎可以是任何配置，只要它们包含在那1个方块厚的5x5x5外壳内。

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/spatial_storage_3x3x3_pylon_demonstration.snbt" />

<BoxAnnotation color="#33dd33" min="1 1 1" max="4 4 4">
        将被移动的体积
  </BoxAnnotation>

<BoxAnnotation color="#3333ff" min="5 5 0" max="0 0 5">
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

一个更合理的设置是这样的：

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/better_spatial_storage_3x3x3.snbt" />

<BoxAnnotation color="#33dd33" min="1 1 1" max="4 4 4">
        将被移动的体积
  </BoxAnnotation>

<BoxAnnotation color="#3333ff" min="5 5 0" max="0 0 5">
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 效率

塔阵列的效率取决于你填充的外壳数量。大型体积周围的最小设置将非常低效，可能需要*数十亿*的AE。

## 元件尺寸

一旦[空间元件](../items-blocks-machines/spatial_cells.md)被使用，它将获得一组永久定义的XYZ尺寸（例如3x4x2），并链接到跨空间存储维度中的一个空间体积。**使用后，你无法重置、重新格式化或调整空间元件的大小。** 如果你想使用不同尺寸，请制作新元件。

这些与元件名称中的尺寸不同，16^3元件可以有任何*最大*16x16x16的尺寸。

请注意，这个体积是定向的，不能旋转。2x2x3体积与3x2x2体积不同，即使它们大小相同。

如果元件的XYZ尺寸与定义的体积不匹配（在IO端口中可见），IO端口将无法操作。
