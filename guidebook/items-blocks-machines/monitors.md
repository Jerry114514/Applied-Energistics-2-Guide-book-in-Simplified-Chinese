---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Monitors
  icon: storage_monitor
  position: 210
categories:
- devices
item_ids:
- ae2:storage_monitor
- ae2:conversion_monitor
---

# 监控器

监控器允许可视化和交互单个物品或流体类型，而无需打开 GUI。  
监控器会继承它们所安装的[线缆](cables.md)的颜色。  
如果监控器在地板或天花板上，你可以使用赛特斯石英扳手<ae2:certus_quartz_wrench>进行旋转。  
它们属于一种[线缆子部件](../ae2-mechanics/cable-subparts.md)。  

# 存储监控器

将显示一个物品或流体及其数量。把它们放在你的农场旁边之类的...  
*不*需要[频道](../ae2-mechanics/channels.md)。  
按键绑定：  
* 用物品右键点击或用流体容器双击右键点击来将监控器设置为该物品/流体。
* 用空手右键点击来清除监控器。
* 用空手 Shift 右键点击来锁定监控器。

## 配方

<RecipeFor id="storage_monitor" />

# 交换监控器

交换监控器类似于存储监控器，但允许你插入或提取其配置的物品。  
如果配置的物品可以[自动合成](../ae2-mechanics/autocrafting.md)且存储中没有，尝试取出物品将改为打开一个 UI 以指定要合成的数量。  
*确实*需要[频道](../ae2-mechanics/channels.md)。  

额外的按键绑定：  
* 左键点击以提取一组配置的物品，或者如果存储中没有该物品则请求合成该物品。
* 用任意物品右键点击以插入该物品。
* 用空手右键点击以从你的物品栏中插入所有配置的物品。

## 配方

<RecipeFor id="conversion_monitor" />
