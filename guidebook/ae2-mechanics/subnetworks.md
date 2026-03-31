---
navigation:
    parent: ae2-mechanics/ae2-mechanics-index.md
    title: 子网络
---

# 子网络

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/subnet_demonstration.snbt" />

<DiamondAnnotation pos="6.5 2.5 0.5" color="#00ff00">
        物品管道子网络
    </DiamondAnnotation>

<DiamondAnnotation pos="5.5 2.5 0.5" color="#00ff00">
        流体管道子网络
    </DiamondAnnotation>

<DiamondAnnotation pos="4.5 2.5 0.5" color="#00ff00">
        过滤湮灭面
    </DiamondAnnotation>

<DiamondAnnotation pos="3.5 2.5 0.5" color="#00ff00">
        形成面子网络
    </DiamondAnnotation>

<DiamondAnnotation pos="2.5 2.5 0.5" color="#00ff00">
        使用接口-存储总线交互的子网络，作为主网络可访问的本地子存储
    </DiamondAnnotation>

<DiamondAnnotation pos="1.5 1.5 0.5" color="#00ff00">
        另一个物品管道子网络，用于将充能物品返回到样板供应器
    </DiamondAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

"子网络"是一个相当松散定义的术语，但可以说子网络是支持你主网络或执行某些小任务的任何网络。它们通常很小，不需要控制器。它们的两个主要用途往往是：

* 限制哪些[设备](../ae2-mechanics/devices.md)可以访问哪些存储（你不希望"管道"子网络上的导入总线访问你的主网络存储，否则它会把物品放入你的存储元件而不是目标库存中）
* 节省主网络上的频道，例如让样板供应器输出到连接到多个机器上多个存储总线的接口，使用1个频道，而不是在每个机器上放置样板供应器，使用多个频道

不同颜色的线缆与创建子网络无关（只是它们不会互相连接）

子网络可以包括：

* 设置为像物品或流体管道一样在容器之间传输物品或流体的导入总线和存储总线
* 湮灭面和存储总线，这样湮灭面只能将分解的物品放入存储总线，允许你过滤湮灭面
* 接口和形成面，这样任何插入接口的东西都会被推送到形成面并在世界中放置/掉落
* 自动制造赛特斯石英的设置，由主网络上的<ItemLink id="level_emitter" />调节和控制
* 通过特殊的存储总线-接口交互从主网络访问的专业存储系统，以便存储农场输出而不会无限溢出你的主存储
* 等等

制作子网络非常有用的是<ItemLink id="quartz_fiber" />。它在网络之间传输能量而不连接它们，允许你为子网络供电而不需要到处放置能源接收器和动力线缆。
