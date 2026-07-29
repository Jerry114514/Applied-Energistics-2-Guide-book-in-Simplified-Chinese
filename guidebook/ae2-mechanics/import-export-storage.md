---
navigation:
    parent: ae2-mechanics/ae2-mechanics-index.md
    title: 输入，输出，以及存储
---

# 输入，输出，以及存储

**你的ME系统与世界**

AE2中的一个重要概念是网络存储的概念。其所指的是存储网络中的内容的地方。
一般是在[存储元件](../items-blocks-machines/storage_cells.md)或连接到存储总线的任何容器。
大多数的 AE2 [设备](../ae2-mechanics/devices.md) 都通过某种方式与之交互。

举例来说：

* **ME输入总线** 将物品推送至网络存储中。
* **ME输出总线** 从网络存储中输出物品。
* **ME接口** 兼具两种ME总线的功能。
* [终端](../items-blocks-machines/terminals.md) 在你拿取/放入物品时相当于执行了ME输入/输出总线的功能。也可以自动填充合成格。
* **ME存储总线** 并不真正向存储推送内容或从存储中拉取内容，而是会向连接的存储部位进行这一步操作，以便将其用作网络存储（所以实际上是其他设备向存储推送内容）

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/import_export_storage.snbt" />

  <BoxAnnotation color="#dddddd" min="8 1 1" max="9 1.3 2">
        导入总线将指向的库存中的东西导入网络存储
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="8 2 1" max="9 3 1.3">
        从您的库存中向终端导入内容，与网络导入内容相同
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="7 0 1" max="8 1 2">
        如果该槽未配置存储任何东西，或该槽中有比配置存储数量更多的物品，接口将从其内部库存导入，这样物品可以被推入其中以输入网络
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="6 0 1" max="7 1 2">
        样板供应器将从其内部返回槽库存导入，这样物品可以被推入其中以输入网络
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 1 1" max="5 2 2">
        驱动器将插入的元件作为网络存储提供
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="4 1.3 2">
        存储总线将其指向的库存用作网络存储
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 1 1" max="2 1.3 2">
        导出总线将物品从网络存储导出到其指向的库存中
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 1" max="2 3 1.3">
        从终端中取出物品算作网络导出它
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 1 1" max="1 2 2">
        如果该槽配置为存储某些物品，接口将导出到其内部库存，这样物品可以从中拉取以从网络提取
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

在设计自动化和物流设置时，记住推送到网络存储和从网络存储拉取的操作/事件是很重要的。

## 存储优先级

可以通过点击某些GUI右上角的扳手来设置优先级。
物品进入网络时将首先从最高优先级的存储开始，作为它们的首选目的地，
如果两个存储具有相同优先级，其中一个已经包含该物品，它们将优先选择该存储而非其他存储。
在同一优先级组中与其他存储时，任何白名单元件将被视为已包含该物品。
从存储中移除物品时，将从最低优先级的存储中移除。这个优先级系统意味着当物品被插入和从网络存储中移除时，
更高优先级的存储将被填满，而更低优先级的存储将被清空。
