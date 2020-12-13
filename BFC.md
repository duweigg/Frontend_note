# Block Formatting Context
---

触发条件:
* 根元素  
* position: absolute/fixed  
* display: inline-block / table   
* float 元素  
* ovevflow !== visible  

规则:  
* 属于同一个 BFC 的两个相邻 Box 垂直排列  
* 属于同一个 BFC 的两个相邻 Box 的 margin 会发生重叠  
* BFC 的区域不会与 float 的元素区域重叠  
* 计算 BFC 的高度时，浮动子元素也参与计算  
* 文字层不会被浮动层覆盖，环绕于周围  
* 每个元素的margin box的左边， 与包含块border box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。
* BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。反之也如此。
* 计算BFC的高度时，浮动元素也参与计算

## Declare

我们可以用CSS为container容器附加上述条件,如overflow: scroll, overflow: hidden, display: flex, float: left, or display: table.尽管这些条件都能形成一个BFC，但是它们各自却有着不一样的表现：

display: table : 在响应式布局中会有问题

overflow: scroll : 可能会出现你不想要的滚动条

float: left: 使元素左浮动，并且其他元素对其环绕

overflow: hidden: 消除溢出部分

这么看来，建立BFC的最好方式莫过于overflow:hidden了：

## Usage
---
* 自适应两栏布局  
会根据包含块（父div）的宽度，和aside的宽度，自适应宽度。

* 可以阻止元素被浮动元素覆盖

* 可以包含浮动元素——清除内部浮动

* 分属于不同的BFC时可以阻止margin重叠


## Examples

[A good illustration of BFC](https://juejin.im/post/6844903504545316877)