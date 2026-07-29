---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Cables
  icon: fluix_glass_cable
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:white_glass_cable
- ae2:orange_glass_cable
- ae2:magenta_glass_cable
- ae2:light_blue_glass_cable
- ae2:yellow_glass_cable
- ae2:lime_glass_cable
- ae2:pink_glass_cable
- ae2:gray_glass_cable
- ae2:light_gray_glass_cable
- ae2:cyan_glass_cable
- ae2:purple_glass_cable
- ae2:blue_glass_cable
- ae2:brown_glass_cable
- ae2:green_glass_cable
- ae2:red_glass_cable
- ae2:black_glass_cable
- ae2:fluix_glass_cable
- ae2:white_covered_cable
- ae2:orange_covered_cable
- ae2:magenta_covered_cable
- ae2:light_blue_covered_cable
- ae2:yellow_covered_cable
- ae2:lime_covered_cable
- ae2:pink_covered_cable
- ae2:gray_covered_cable
- ae2:light_gray_covered_cable
- ae2:cyan_covered_cable
- ae2:purple_covered_cable
- ae2:blue_covered_cable
- ae2:brown_covered_cable
- ae2:green_covered_cable
- ae2:red_covered_cable
- ae2:black_covered_cable
- ae2:fluix_covered_cable
- ae2:white_covered_dense_cable
- ae2:orange_covered_dense_cable
- ae2:magenta_covered_dense_cable
- ae2:light_blue_covered_dense_cable
- ae2:yellow_covered_dense_cable
- ae2:lime_covered_dense_cable
- ae2:pink_covered_dense_cable
- ae2:gray_covered_dense_cable
- ae2:light_gray_covered_dense_cable
- ae2:cyan_covered_dense_cable
- ae2:purple_covered_dense_cable
- ae2:blue_covered_dense_cable
- ae2:brown_covered_dense_cable
- ae2:green_covered_dense_cable
- ae2:red_covered_dense_cable
- ae2:black_covered_dense_cable
- ae2:fluix_covered_dense_cable
- ae2:white_smart_cable
- ae2:orange_smart_cable
- ae2:magenta_smart_cable
- ae2:light_blue_smart_cable
- ae2:yellow_smart_cable
- ae2:lime_smart_cable
- ae2:pink_smart_cable
- ae2:gray_smart_cable
- ae2:light_gray_smart_cable
- ae2:cyan_smart_cable
- ae2:purple_smart_cable
- ae2:blue_smart_cable
- ae2:brown_smart_cable
- ae2:green_smart_cable
- ae2:red_smart_cable
- ae2:black_smart_cable
- ae2:fluix_smart_cable
- ae2:white_smart_dense_cable
- ae2:orange_smart_dense_cable
- ae2:magenta_smart_dense_cable
- ae2:light_blue_smart_dense_cable
- ae2:yellow_smart_dense_cable
- ae2:lime_smart_dense_cable
- ae2:pink_smart_dense_cable
- ae2:gray_smart_dense_cable
- ae2:light_gray_smart_dense_cable
- ae2:cyan_smart_dense_cable
- ae2:purple_smart_dense_cable
- ae2:blue_smart_dense_cable
- ae2:brown_smart_dense_cable
- ae2:green_smart_dense_cable
- ae2:red_smart_dense_cable
- ae2:black_smart_dense_cable
- ae2:fluix_smart_dense_cable
---

# 线缆

<GameScene zoom="3" background="transparent">
  <Import Structure src="/assets/assemblies/cables.snbt" />
  <IsometricCamera yaw="180" pitch="30" />
</GameScene>

虽然相邻的 ME 设备也能构成 ME 网络，但线缆是在更大范围内扩展 ME 网络的主要方式。

不同颜色的线缆可以确保相邻的线缆不会互相连接，从而让[频道](../ae2-mechanics/channels.md)的分配更高效。它们还会影响连接到线缆上的终端颜色，这样你就不必让所有终端都是紫色的了。福鲁伊克斯线缆会与所有其他颜色的线缆连接。

需要注意的是，**频道与线缆颜色毫无关系**。

## 重要提示

**如果你是 AE2 新手，不熟悉频道机制，请尽可能使用智能线缆和致密智能线缆。它们会显示频道在网络中的路由方式，让你更容易理解频道的行为。**

## 另一条提示

**这些不是物品、流体、能量等管道。** 它们没有内部存储空间，样板供应器和机器不会向它们"推送"内容，它们的作用只是将 AE2 [设备](../ae2-mechanics/devices.md)连接成一个网络。

## 玻璃线缆

<GameScene zoom="6" background="transparent">
  <Import Structure src="/assets/assemblies/fluix_glass_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="fluix_glass_cable" /> 是最简单的线缆，可传输能量和最多 8 个[频道](../ae2-mechanics/channels.md)。它有 17 种不同颜色，默认颜色为福鲁伊克斯，可以使用 16 种染料中的任意一种染色。

要制作彩色线缆，用任意类型的染料围住 8 根同类型的线缆（线缆的颜色不重要，但必须是同类型，如玻璃线缆、智能线缆等）。你也可以在游戏世界中用任何兼容 Forge 的画笔给线缆涂色。

用水桶与任意彩色线缆合成可以去除染料。

你可以用羊毛包裹线缆来制作<ItemLink id="fluix_covered_cable" />，也可以制作<ItemLink id="fluix_smart_cable" />来更好地了解[频道](../ae2-mechanics/channels.md)的使用情况。

<RecipeFor id="fluix_glass_cable" />

<RecipeFor id="blue_glass_cable" />

## 包层线缆

<GameScene zoom="6" background="transparent">
  <Import Structure src="/assets/assemblies/fluix_covered_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

包层线缆相比<ItemLink id="fluix_glass_cable" />在游戏机制上没有任何优势。不过，如果你更喜欢包层的外观，它可以作为一种替代的美学选择。

染色方式与<ItemLink id="fluix_glass_cable" />相同。四个<ItemLink id="fluix_covered_cable" />可以与红石和荧石粉合成，制作<ItemLink id="fluix_covered_dense_cable" />。

<Recipe id="network/cables/covered_fluix" />

<RecipeFor id="blue_covered_cable" />

## 致密线缆

<GameScene zoom="6" background="transparent">
  <Import Structure src="/assets/assemblies/fluix_covered_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

更高容量的线缆，可承载 32 个频道，而标准线缆只能承载 8 个。但它不支持总线，因此在使用总线或面板之前，必须先通过致密线缆降级到更小的线缆（如<ItemLink id="fluix_glass_cable" />或<ItemLink id="fluix_smart_cable" />）。

致密线缆会略微覆盖频道的"最短路径"行为：频道会先走最短路径到达致密线缆，然后通过致密线缆走最短路径到达控制器。

<Recipe id="network/cables/dense_covered_fluix" />

<RecipeFor id="blue_covered_dense_cable" />

## 智能线缆

<Row>
<GameScene zoom="6" background="transparent">
  <Import Structure src="/assets/assemblies/fluix_smart_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
<GameScene zoom="6" background="transparent">
  <Import Structure src="/assets/assemblies/fluix_smart_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
</Row>

虽然外观上与<ItemLink id="fluix_covered_cable" />有些相似，但它们提供了诊断功能：通过可视化线缆上的频道使用情况来帮助你了解网络中的频道分配。频道会显示为沿黑色条纹运行的彩色发光线条。对于普通智能线缆，前四个频道显示为与线缆颜色匹配的线条，后四个显示为白色线条。对于致密智能线缆，每条条纹代表 4 个频道。

在带有<ItemLink id="controller" />的网络中，线缆上的线条会显示频道的确切路径。

在临时网络（ad-hoc-network）中，智能线缆会显示整个网络正在使用的频道总数，而不是流经该特定线缆的频道数量。

这些线缆也可以像<ItemLink id="fluix_glass_cable" />一样染色。


<Recipe id="network/cables/smart_fluix" />

<Recipe id="network/cables/dense_smart_fluix" />

<RecipeFor id="blue_smart_cable" />
