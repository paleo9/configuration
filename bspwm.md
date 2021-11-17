# BSPWM

bspwm is a tiling window manager that represents windows as the leaves of a full binary tree.

It is controlled and configured via bspc.

A binary tree is a data structure that consists of a 
  * root (a node with no parent)
  * each node can have zero or two child nodes
  * in bspwm, each node may contain a window to display a view of an app.

## Node

  * Each leaf node holds zero or one windows, which contains a view of an app.
  * Each node has zero or two children.
  * Each internal node is responsilble for splitting a rectangle in half.
  * A split is defined by two parameters: the type (horizontal or vertical) and the ratio (a real number r ::  0 < r < 1).

## Tree

  * A tree contains zero or more nodes.
  * The tree is a partition of a monitor's rectangle into smaller rectangular regions.

## Window

  * A window is a rectangle that contains a view of an app.
  * It can be tiled, pseudo_tiled, floating, fullscreen


## Desktop

  * A pointer to a tree.
  * Represents /  displays a set of windows

## Monitor

  * A rectangle that contains desktops. 
  * It only shows the tree of one desktop at a time (its focused desktop).

