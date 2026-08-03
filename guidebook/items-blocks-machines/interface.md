---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Interface
  icon: interface
  position: 210
categories:
- devices
item_ids:
- ae2:interface
- ae2:cable_interface
---

# ME 接口
接口就像一个小箱子和流体储罐的结合体，它会根据你在其槽位中设置的库存量，从[网络存储](../ae2-mechanics/import-export-storage.md)中自动填满或清空自己。  
它试图在一个游戏刻内完成这一过程，因此它可以在每个游戏刻内填满或清空最多9组物品，使其成为一种快速的导入或导出方式，前提是你有快速的物品管道。  
另一个有用的特性是，大多数流体储罐只能存储1种流体，而接口可以存储多达9种流体，以及物品。  
它们本质上就是带有一些额外功能的箱子/多流体储罐，你可以通过将它们与任何网络断开连接来阻止这些额外功能。  
因此，在一些特殊情况下它们非常有用，比如你想少量存储一堆不同种类的东西。  

## 接口内部工作原理

如前所述，接口本质上就是一个箱子/储罐，上面连接着一些超级厉害的 ME 输入总线<ae2:import_bus>和 ME 输出总线<ae2:export_bus>，以及一堆 ME 标准发信器<ae2:level_emitter>。

## 特殊互动

接口与其他 AE2 [设备](../ae2-mechanics/devices.md)还有一些特殊功能：  
一个未配置的接口上的 ME 存储总线<ae2:storage_bus>会将其网络的[网络存储](../ae2-mechanics/import-export-storage.md)的全部内容呈现给存储总线所在的网络，就像接口的网络是一个大箱子，而存储总线就放在这个大箱子上一样。  
在接口的过滤槽位中设置要储备的物品会禁用此功能。  

样板供应器与[子网络](../ae2-mechanics/subnetworks.md)上的接口有一个特殊的互动：如果接口未被配置，样板供应器将完全跳过该接口，直接推送到该子网络的[存储](../ae2-mechanics/import-export-storage.md)，跳过接口而不是用配方批次填满它，更重要的是，直到存储中有空间之前不会插入下一批。

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
       接口（必须是面板形式，不能是完整方块）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        多个存储总线
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        你想要样板供应到的位置（多台机器，或一台机器的多个面）
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

## 变体

接口有2种不同的变体：普通和面板/[子部件](../ae2-mechanics/cable-subparts.md)。这会影响它们可以从哪些特定面访问其库存，以及它们提供网络连接到哪些面。  
* 普通接口允许从所有面推入、拉出和访问其库存，并且像大多数 AE2 机器一样，像线缆一样为所有面提供网络连接。
* 面板接口属于一种[线缆子部件](../ae2-mechanics/cable-subparts.md)，因此多个可以放置在同一条线缆上，从而实现紧凑布局。它们允许从其面推入、拉出和访问其库存，但不在其面上提供网络连接。
接口可以在合成网格中在普通和面板之间切换。  

## 设置

接口中的上方槽位决定接口设置为何物在其内部储备。当有东西放入其中或从 JEI/REI 拖入时，会出现一个扳手，让你设置数量。  
右键点击一个流体容器（如水桶或流体储罐）来将那流体设置为过滤器，而不是水桶或储罐物品。  
当你将槽位设置为储备模式时，它也会阻止外部机器将任何其他物品插入该槽位。  

## 升级

接口支持以下[升级](upgrade_cards.md)：  
* 模糊卡<ae2:fuzzy_card>让总线按耐久度进行过滤和/或忽略物品 NBT
* 合成卡<ae2:crafting_card>让接口向你的[自动合成](../ae2-mechanics/autocrafting.md)系统发送合成请求以获取它想要的物品。在请求合成新物品之前，它会尽可能先从存储中提取物品。

## 优先级

优先级可以通过点击 GUI 右上角的扳手来设置。较高优先级的接口会比较低优先级的接口先获得物品。  

## 配方

<Recipe id="network/blocks/interfaces_interface" />

<RecipeFor id="cable_interface" />
