---
navigation:
  title: Getting Started (1.20+)
  position: 10
---

<div class="notification is-info">
  以下文章中的内容皆仅适用于 1.20 或更新版本的 AE2 模组。
</div>

# 新手上路

## 获取初始材料

要开始您的 应用能源2 征程，首先必须找到一颗[陨石](ae2-mechanics/astroperties.md)。这些是相当常见的，往往会在地形上留下巨大的洞，所以你可能在探索过程中遇到过。
如果你还没有，你可以创建一个[陨石罗盘]，它将指向最近的[陨石坑]。

一旦你发现了一颗陨石，就尝试向其中心挖掘。您会发现各种类型的赛特斯石英簇、赛特斯石英芽、[萌芽的赛特斯石英母岩](items blocks machines/budding_centrus.md)和陨石中心的神秘方块。

开采赛特斯石英簇和你找到的任何赛特斯石英块。你也可以捡起萌芽的赛特斯石英母岩，但如果没有精准采集的话，它们会损坏，并降级一等品质。

不要破坏任何无瑕的赛特斯石英母岩，因为即使有精准采集，它们也会损坏为有瑕的赛特斯石英母岩，而且不可能将其修复回无瑕状态。

同时也要挖掘陨石中心的神秘方块，以获得所有4个压印模板。

## 种植赛特斯石英

赛特斯石英芽将从[赛特斯石英母岩](items blocks machines/budding_centrus.md)中钻出，类似于紫水晶。如果你破坏了一个尚未成熟的芽簇时，
它将掉落一个[赛特斯石英粉]，且不受时运影响。如果你破坏一个完全生长的芽簇，它则会掉落四个
[赛特斯石英水晶]s，并且时运会增加掉落物数量。

根据不同的品质，赛特斯石英母岩共分四等: 无瑕的，有瑕的，开裂的，损坏的。

每当一个芽簇生长到另一个阶段，母岩就有可能降等一层，最终变成一块普通的赛特斯石英块。
通过将母岩（或无瑕的石英母岩）投入水中来修复（并生成新的母岩）。

一个或多个无瑕的石英母岩不会降解，并且会无限生成石英芽。然而，它们无法用镐开采或移动，即使使用精准采集也不行。(但他们 *可以* 通过 [spatial storage](ae2-mechanics/spatial-io.md) 所移动)

就其本身而言，石英芽的生长非常缓慢。幸运的是，当[催生器]大规模放置在母岩块附近时，会加速这一过程。你应该把上述内容的其中一些作为你的首要任务。


如果你没有足够的赛特斯石英来制作[能源接收器]或[谐振仓]，你可以制作一个[木制曲柄]并将其粘在催生器末端。

关于自动化收集赛特斯石英的内容，[已在此记载](example-setups/simple-certus-farm.md).

## A Quick Aside on Fluix

Another material you will need is Fluix, which you have already encountered in making growth accelerators. It is made by throwing charged certus, redstone, and nether quartz in water. Doing this automatically is "left as an exercise for the reader."

The <ItemLink id="charger" /> is required to produce <ItemLink id="charged_certus_quartz_crystal" />., if you haven't made one already.

## Inscribing Some Processors

In your looting of a meteorite, you will have found four "presses" from breaking the Mysterious Cube. These are used in the <ItemLink id="inscriber" /> to make the three types of processor.

<ItemGrid>
  <ItemIcon id="silicon_press" />

  <ItemIcon id="logic_processor_press" />

  <ItemIcon id="calculation_processor_press" />

  <ItemIcon id="engineering_processor_press" />
</ItemGrid>

The inscriber is a sided machine, much like the vanilla furnace. Inserting from the top or bottom places items in the top or bottom slots, and inserting from the side or back inserts into the center slot. Results can be pulled from the side or back.

To facilitate automation with hoppers (and possibly reduce pipe spaghetti), inscribers can be rotated with a <ItemLink id="certus_quartz_wrench" />.

Produce a few of each type of processor in preparation for the next step, making a very basic ME system. Automating processor production is "[left as an exercise for the reader](example-setups/processor-automation.md)".

## Matter Energy Tech: ME Networks and Storage

### What is ME Storage?

Its pronounced Emm-Eee, and stands for Matter Energy.

Matter Energy is the main component of Applied Energistics 2, it's like a mad scientist version of a Multi-Block chest,
and it can revolutionize your storage situation. ME is extremely different than other storage systems in Minecraft, and
it might take a little out of the box thinking to get used to; but once you get started vast amounts of storage in tiny
space, and multiple access terminals are just the tip of the iceberg of what becomes possible.

### What do I need to know to get started?

First, ME Stores items inside of other items, called [Storage cells](items-blocks-machines/storage_cells.md); there are 5 tiers with ever increasing amounts of
storage. In order to use a Storage Cell it must be placed inside either an <ItemLink id="chest" />,
or an <ItemLink id="drive" />.

The <ItemLink id="chest" /> shows you the contents of the Cell as soon as its placed inside, and you
can add and remove items from it as if it were a <ItemLink id="minecraft:chest" />, with the exception that the items are
actually stored in the Storage cells, and not the <ItemLink id="chest" /> itself.

The <ItemLink id="chest" /> is quite situational and limited in utility. To really
take advantage of AE2, you need to set up an [ME Network](ae2-mechanics/me-network-connections.md).

## Your Very First ME System

Now that you have all of the basic materials and machines for Applied Energistics 2, you can make your first ME (Matter Energy) system. This will be a very basic one, no autocrafting, no logistics, just nice, simple, searchable storage.

<GameScene zoom="6" interactive={true}>
<ImportStructure src="assets/assemblies/tiny_me_system.snbt" />

</GameScene>

*   Your ingredients list:
    * 1x <ItemLink id="drive" />
    * 1x <ItemLink id="terminal" /> or <ItemLink id="crafting_terminal" />
    * 1x <ItemLink id="energy_acceptor" />
    * A few [cables](items-blocks-machines/cables.md), either glass, covered, or smart, but not dense
    * A few [storage cells](items-blocks-machines/storage_cells.md), recommended of the 4k variety for a good mix of
    capacity and types (it would be more efficient to [partition](items-blocks-machines/cell_workbench.md) a mix of 4k and 1k but that's a complexity we won't go into now)
---
1.  Place the drive down.
2.  The energy acceptor (and several other AE2 [devices](ae2-mechanics/devices.md)) comes in 2 modes, cube and flat. They can be switched between in a crafting grid. If your energy acceptor is a cube, place it down next to the drive. If it's a flat square, place a cable on the drive and place the acceptor on that.
3.  Run energy into the energy acceptor with a cable/pipe/conduit from your favorite energy-generation mod.
4.  Place a cable on top of the drive (or otherwise at eye level) and place your terminal or crafting terminal on it.
5.  Put your storage cells into the drive
6.  Profit
7.  Fiddle with the terminal's settings
8.  Bask in your ultimate power and ability
9.  Realize that this network is, in the grand scheme, rather small

### Expanding your Network

So you have some basic storage, and access to that storage, it's a good start, but you'll likely be looking to maybe
automate some processing.

A great example of this is to place a <ItemLink id="export_bus" /> on the top of a furnace to
dump in ores, and a <ItemLink id="import_bus" />
on the bottom of the furnace to extract furnaced ores.

The <ItemLink id="export_bus" /> lets you export items from the network, into the attached
inventory, while the <ItemLink id="import_bus" /> imports items from the attached inventory into
the network.

### Overcoming Limits

At this point you probably getting close to 8 or so [devices](ae2-mechanics/devices.md), once you hit 9 devices you'll have to start
managing [channels](ae2-mechanics/channels.md). Many devices but not all, require a channel to
function.

By default a network can support 8 channels, once you break this limit, you'll have to add
an <ItemLink id="controller" /> to your network. this allows you to expand your network greatly.
[Smart cables](items-blocks-machines/cables.md) will allow you to see how channels are routed through your network. Use them extensively when starting out to learn how channels act, or if you have a lot of redstone and glowstone.
