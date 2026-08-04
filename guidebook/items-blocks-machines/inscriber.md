---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Inscriber
  icon: inscriber
  position: 310
categories:
- machines
item_ids:
- ae2:inscriber
---

# 压印器

压印器用于使用[压印模板](presses.md)来压印电路和[处理器](processors.md)，以及将各种物品粉碎成粉。  
它可以接受 AE2 的能量（AE）或 Fabric/Forge 能量（E/FE）。它可以分面使用，这样从不同面插入物品会将它们插入到其库存中的不同槽位。为了便于实现这一点，它可以使用赛特斯石英扳手<ae2:certus_quartz_wrench>进行旋转。  

它也可以设置为将合成结果推送到相邻的容器中。  
输入缓冲区的大小可以调整。例如，如果你想让一个容器向一大排压印器供料，你需要一个小缓冲区，以便材料能更优化地分配在各压印器之间（而不是第一个压印器填满到64，其余的都是空的）。  

4个电路压印模板用于制作[处理器](processors.md)。  
而名称压印模板可以用来像铁砧一样给方块命名，这对于在 ME 样板管理终端<ae2:pattern_access_terminal>中标记物品非常有用。  

## 设置
* 压印器可以设置为分面模式（如下所述），或允许从任何面输入到任何槽位，通过内部过滤器决定什么物品进入哪个槽位。在非分面模式下，物品不能从顶部和底部槽位中提取。
* 压印器可以设置为将物品推送到相邻的容器中。
* 输入缓冲区的大小可以调整，大缓冲区选项适用于手动供料的独立压印器，小缓冲区选项是为大型并行化装置提供更好的可行性。

## GUI 与分面

在分面模式下，压印器根据你插入或提取的面来过滤什么物品进入哪个槽位。  
![Inscriber GUI](../assets/diagrams/inscriber_gui.png) ![Inscriber Sides](../assets/diagrams/inscriber_sides.png)  
A. **顶部输入** 通过压印器的顶面访问（物品可以被推入和拉出此槽位）  
B. **中心输入** 通过压印器的左、右、前、后侧面插入（物品只能被推入此槽位，不能被拉出）  
C. **底部输入** 通过压印器的底面访问（物品可以被推入和拉出此槽位）  
D. **输出** 通过压印器的左、右、前、后侧面拉出（物品只能从此槽位拉出，不能被推入）  

## 简单自动化

作为一个例子，分面性和可旋转性意味着你可以像这样半自动化压印器：  
或者，在非分面模式下，只需将管道输入和输出压印器。  

## 升级

压印器支持以下[升级](upgrade_cards.md)：  
* 加速卡<ae2:speed_card>  

## 配方

<RecipeFor id="inscriber" />
