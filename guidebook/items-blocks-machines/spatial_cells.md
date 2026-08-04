---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Spatial Cells
  icon: spatial_storage_cell_128
  position: 410
categories:
- tools
item_ids:
- ae2:spatial_storage_cell_2
- ae2:spatial_storage_cell_16
- ae2:spatial_storage_cell_128
- ae2:spatial_cell_component_2
- ae2:spatial_cell_component_16
- ae2:spatial_cell_component_128
---

# 空间存储元件

空间存储元件用于[存储物理空间体积](../ae2-mechanics/spatial-io.md)。  

它们用于空间 IO 端口<ae2:spatial_io_port>。  

与[存储元件](../items-blocks-machines/storage_cells.md)不同，空间元件无法重新格式化。  

再次强调，**空间元件一旦使用后，你不能重置、重新格式化或调整其大小。** 如果你想使用不同的尺寸，请制作一个新的元件。  

## 配方

  <Row>
    <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />

    <Recipe id="network/cells/spatial_storage_cell_16_cubed_storage" />

    <Recipe id="network/cells/spatial_storage_cell_128_cubed_storage" />
  </Row>

# 外壳

元件可以用一个空间组件和一个外壳制作，或者用外壳配方围绕一个空间组件制作：  

外壳本身是这样合成的：  

  <RecipeFor id="item_cell_housing" />

# 空间组件

空间组件是空间存储元件的核心。  

每升一级，可存储的体积尺寸就会增加8倍。  

  <Row>
    <RecipeFor id="spatial_cell_component_2" />

    <RecipeFor id="spatial_cell_component_16" />

    <RecipeFor id="spatial_cell_component_128" />
  </Row>