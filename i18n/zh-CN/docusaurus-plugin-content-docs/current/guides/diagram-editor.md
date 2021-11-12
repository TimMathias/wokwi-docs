---
title: 交互式图表编辑器
sidebar_label: 图表编辑器
---

组件编辑器提供一种交互式的编辑你的模拟器连接图的方法：在模拟器中添加元器件进行模拟以及定义元器件之间的连接，这是替代直接编辑[diagram.json](../diagram-format)文件的一种非常方便的方法。

## 编辑组件

### 添加组件

点击图表编辑器顶部的紫色“+”按钮来添加一个新的组件。

你会看到一个组件列表，选择一个组件，它将被添加到图表中的(0, 0)位置，你可以拖动到你想要的位置。

不是所有的组件都会显示在列表中，例如MCU板和[Arduino Nano](../parts/wokwi-arduino-nano)、 [ATtiny85](../parts/wokwi-attiny85)之类的微控制器就不会显示，但你可以通过[编辑 diagram.json 文件](../diagram-format#parts)来添加它们。

### 移动组件

点击一个组件并拖动鼠标来移动它。

### 旋转组件

点击一个组件选中，然后按下R键旋转，组件会按顺时针旋转90°。如果你需要旋转别的角度（例如45°），可以通过[编辑 diagram.json 文件](../diagram-format#parts)来实现。

### 删除组件

点击一个组件选中，然后按下Delete键删除。

## Editing wires

### Creating a wire between two parts

To create a new wire between two parts, click on one of the pins that you'd like to connect. Then click on the second (target) pin. This will create the wire.

If you want the wire to go in a specific way, you can guide it by clicking where you want it to go after selecting the first pin.

To cancel a new wire (delete it without selecting a target pin) click the right mouse button or press Escape.

### Changing the color of a wire

The color of new wires is automatically determined by the function of the pin: wires starting from ground pins are black, 5&nbsp;V pins are red, and other wires are green.

The interactive editor does not support setting the color of wires. You can, however, change the color of any wire by editing [diagram.json](../diagram-format#connections)

### Deleting a wire

Delete a wire by clicking on it.

## Keyboard shortcuts

The following table summarizes the keyboard shortcuts:

| Key    | Function                                    |
| ------ | ------------------------------------------- |
| -      | Zoom out                                    |
| +      | Zoom in                                     |
| R      | Rotate the selected part                    |
| Delete | Delete the selected part                    |
| ?      | Open documentation for the selected part    |
| Escape | Cancel wire (in wiring mode)                |
| G      | Toggle the grid                             |
| Shift  | Toggle coarse grid snapping while dragging  |
| Alt    | Toggle fine grid snapping while dragging    |
| Ctrl   | Toggle fine grid snapping while dragging    |

Firefox users: if the keyboard shortcuts don't work for you, please make sure that the "Search for text when you start typing" setting is disabled.

## 撤销 / 重做

Any change that you make in the interactive editor is also reflected in [diagram.json](../diagram-format).

The interactive editor **does not** have an undo feature at the moment (there's an [open issue for that](https://github.com/wokwi/wokwi-features/issues/77)).

You can still get complete Undo history if you select the "diagram.json" tab in the code editor. Any changes made in the interactive diagram editor
will immediately reflect in the code editor, and you'll be able to undo them by clicking on the code editor and then pressing Ctrl+Z.

Note that this only works if the "diagram.json" tab is active while you make changes. This is a temporary solution until we implement Undo in the interactive diagram editor.

## Grid snapping

Activate the grid view by pressing "G" or by clicking the grid icon in the menu. This displays a grid and rulers. The coarse grid is 2.54&nbsp;mm or 0.1&nbsp;inches and the fine grid is 1.27&nbsp;mm or 0.05&nbsp;inches. Tick labels on the rulers show measurements in millimetres (the default), but you can switch to inches by clicking on the units in the top right corner.

The Shift key temporarily toggles the grid snapping mode between the coarse grid and free movement. If the grid is on, it toggles to free movement; if the grid is off, it toggles to coarse grid snapping.

The Alt key or the Ctrl key temporarily toggle to fine grid snapping whether the grid is visible or not.

This grid snapping behaviour is the same for both parts and new wires, and the modifier keys allow you to perform grid snapping whether the grid is on or off.