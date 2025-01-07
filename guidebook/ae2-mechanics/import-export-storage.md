---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Import, Export, and Storage
---

# 输入，输出，以及存储

**你的ME系统与世界**

AE2中的一个重要概念是网络存储的概念。 其所指的是存储网络中的内容的地方。
一般是在[存储元件](../items-blocks-machines/storage_cells.md)或连接到存储总线的任何容器。
大多数的 AE2 [设备](../ae2-mechanics/devices.md) 都通过某种方式与之交互。

举例来说，  

*   **ME输入总线** 将物品推送至网络存储中。  
*   **ME输出总线** 从网络存储中输出物品。  
*   **ME接口** 兼具两种ME总线的功能。  
*   [终端](../items-blocks-machines/terminals.md) 在你拿取/放入物品时相当于执行了ME输入/输出总线的功能。也可以自动填充合成格。  
*   **ME存储总线** 并不真正向存储推送内容或从存储中拉取内容，而是会向连接的存储部位进行这一步操作，以便将其用作网络存储(所以实际上是其他设备向)

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/import_export_storage.snbt" />

  <BoxAnnotation color="#dddddd" min="8 1 1" max="9 1.3 2">
        导入总线将指向的库存中的东西导入网络存储
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="8 2 1" max="9 3 1.3">
        从您的库存中向终端导入内容，与网络导入内容相同
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="7 0 1" max="8 1 2">
        Interfaces will import from their internal inventories if that slot is not configured to stock anything, or there are more
        items in that slot than are configured to be stocked, so things can be pushed into them to insert into the network
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="6 0 1" max="7 1 2">
        Pattern Providers will import from their internal return slot inventory, so things can be pushed into them to insert into the network
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 1 1" max="5 2 2">
        Drives provide the inserted cells as network storage
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="4 1.3 2">
        Storage Busses use the inventory they're pointing at as network storage
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 1 1" max="2 1.3 2">
        Export Busses export things from network storage into inventories they're pointing at
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 1" max="2 3 1.3">
        Pulling something out of a terminal counts as the network exporting it
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 1 1" max="1 2 2">
        Interfaces will export to their internal inventories if that slot is configured to stock something,
        so things can be pulled from them to extract from the network
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

The actions/events of pushing to and pulling from network storage are important to keep in mind when designing automation
and logistics setups.

## Storage Priority

Priorities can be set by clicking the wrench in the top-right of some GUIs.
Items entering the network will start at the highest priority storage, as
their first destination, in the case of two storages have the same priority,
if one already contains the item, they will prefer that storage over any
other. Any Whitelisted cells will be treated as already containing the item
when in the same priority group as other storages. Items being removed from storage will
be removed from the storage with the lowest priority. This priority system means as items are inserted and removed
from network storage, higher priority storages will be filled and lower priority storages will be emptied.
