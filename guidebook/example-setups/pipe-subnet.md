---
navigation:
    parent: example-setups/example-setups-index.md
    title: 物品/流体"管道"子网络
    icon: storage_bus
---

# 物品/流体"管道"子网络

一种使用AE2[设备](../ae2-mechanics/devices.md)模拟物品和/或流体管道的方法，可用于任何你使用物品或流体管道的场景。
这包括将合成结果返回到<ItemLink id="pattern_provider" />。

通常有两种不同的方法来实现这一点：

## 输入总线 -> 存储总线

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) 输入总线：可以过滤。
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) 存储总线：可以过滤。这个（和其他你希望作为目的地的存储总线）必须是网络上唯一的存储。
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        来源
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        目的地
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

源库存上的<ItemLink id="import_bus" /> (1) 导入物品或流体，并尝试将其存储到[网络存储](../ae2-mechanics/import-export-storage.md)中。
由于网络上唯一的存储是<ItemLink id="storage_bus" /> (2)（这就是为什么这是一个子网络而不是在你的主网络上），物品或流体被放置到目标库存中，从而实现传输。能量通过<ItemLink id="quartz_fiber" />提供。
输入总线和存储总线都可以进行过滤，但如果不应用过滤，该设置将传输所有可访问的内容。
此设置也可以使用多个输入总线和多个存储总线。

## 存储总线 -> 输出总线

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) 存储总线：可以过滤。这个（和其他你希望作为来源的存储总线）必须是网络上唯一的存储。
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) 输出总线：必须过滤。
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        来源
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        目的地
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

目标库存上的<ItemLink id="export_bus" />尝试从其过滤器中的[网络存储](../ae2-mechanics/import-export-storage.md)拉取物品。
由于网络上唯一的存储是<ItemLink id="storage_bus" />（这就是为什么这是一个子网络而不是在你的主网络上），物品或流体从源库存中被拉取，从而实现传输。能量通过<ItemLink id="quartz_fiber" />提供。
因为输出总线必须进行过滤才能工作，所以此设置只有在过滤输出总线时才会运行。
此设置也可以使用多个存储总线和多个输出总线。

## 不起作用的一种设置（输入总线 -> 输出总线）

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_export_pipe.snbt" />

<BoxAnnotation color="#dd3333" min="3.7 0 0" max="4 1 1">
        输入总线：由于网络没有存储，它无法导入任何东西。
  </BoxAnnotation>

<BoxAnnotation color="#dd3333" min="1 0 0" max="1.3 1 1">
        (2) 输出总线：由于网络没有存储，它无法导出任何东西。
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#ff0000">
        来源
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#ff0000">
        目的地
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

仅使用输入和输出总线的设置是行不通的。输入总线将尝试从源库存中拉取物品或流体并将其存储到网络存储中。输出总线将尝试从网络存储中拉取物品或流体并将其放入目标库存中。然而，由于这个网络**没有存储**，输入总线无法导入，输出总线也无法导出，所以什么都不会发生。

## 通过一个面输入和输出

假设你有一个可以通过一个面接收输入并拉取输出的机器。（比如<ItemLink id="charger" />）
你可以通过结合两种管道子网络方法来同时推入材料和拉出结果：

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="4 1 1" max="5 1.3 2">
        (1) 输入总线：可以过滤。
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 1 1" max="3 1.3 2">
        (2) 存储总线：可以过滤。这个（和其他你希望推入和拉取物品的存储总线）必须是网络上唯一的存储。
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 1" max="3 1 2">
        (3) 你想要推入和拉取的物品：这里是充能器。
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 1" max="1 1.3 2">
        (4) 输出总线：必须过滤。
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 1.5" color="#00ff00">
        来源
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 1.5" color="#00ff00">
        目的地
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 接口

事实证明，除了输入总线和输出总线之外，还有[设备](../ae2-mechanics/devices.md)可以向[网络存储](../ae2-mechanics/import-export-storage.md)推送和从中拉取物品！
这里涉及到的是<ItemLink id="interface" />。如果插入的物品是接口未设置为存储的，接口会将其推送到网络存储，我们可以像利用输入总线 -> 存储总线管道一样来利用这一点。将接口设置为存储某些物品会从网络存储中拉取它，类似于存储总线 -> 输出总线管道。接口可以设置为存储某些物品而不存储其他物品，允许你通过存储总线远程推送和拉取，如果你出于某种原因想要这样做的话。

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/interface_pipes.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        接口
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        存储总线
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.7 0 2" max="4 1 3">
        存储总线
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 2" max="1 1.3 3">
        存储总线
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 一对多和多对一（以及多对多）

当然，你不必只使用一个<ItemLink id="import_bus" />或<ItemLink id="export_bus" />或<ItemLink id="storage_bus" />

<GameScene zoom="3" background="transparent">
<ImportStructure src="../assets/assemblies/many_to_many_pipe.snbt" />

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

## 向多个地方供应

从这里，我们可以推导出一种方法，将原料从一个<ItemLink id="pattern_provider" />的一个面发送到多个不同的位置，比如一组机器，或者一个机器的多个不同面。

我们不希望使用输入 -> 存储管道或存储 -> 输出管道，因为<ItemLink id="pattern_provider" />实际上从不包含材料。相反，供应器*推送*材料到相邻的库存，所以我们需要一个也能导入物品的相邻库存。

这听起来像是...一个<ItemLink id="interface" />！
确保供应器处于方向性子部件或平面子部件模式，和/或接口处于平面子部件模式，这样两者就不会形成网络连接。

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        接口（必须是平面的，不是完整方块）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        存储总线
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        你想要样板供应的地方（多个机器，或一个机器的多个面）
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>
