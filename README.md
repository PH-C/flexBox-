## 什么是 Flexbox ？

> Flexbox 是 flexible box 的简称（愚人码头注：意思是“灵活的盒子容器”），是 CSS3 引入的新的布局模式。它决定了元素如何在页面上排列，使它们能在不同的屏幕尺寸和设备下可预测地展现出来。

> 它之所以被称为 Flexbox ，是因为它能够扩展和收缩 flex 容器内的元素，以最大限度地填充可用空间。与以前布局方式（如 table 布局和浮动元素内嵌块元素）相比，

Flexbox 是一个更强大的方式：

- 在不同方向排列元素
- 重新排列元素的显示顺序
- 更改元素的对齐方式
- 动态地将元素装入容器
#### 什么情况下不建议使用 Flexbox ？

> 虽然 Flexbox 非常适合缩放，对齐和重新排序元素，但以下情况应该尽量避免使用 Flexbox 布局：

- 整体页面布局
- 完全支持旧浏览器的网站
> 旧版浏览器，如IE 11或更低版本，不支持或仅部分支持 Flexbox 。如果你想安全的使用页面正常呈现，你应该退回到其他的 CSS 布局方式，比如结合float 的 display: inline-block 或者 display: table 等。但是，如果您只针对现代浏览器，那么 Flexbox 绝对值得一试。

#### 总结
###### 如何确定主轴交叉轴的方向？
> 在flex布局中最重要的是首先确定主轴和交叉轴的方向，默认情况下主轴方向向右，
交叉轴向下，我们要记着这个定律交叉轴始终在主轴逆时针90度方向；我们可以通过设置

flex-direction:
- row(主轴向右)|
- row-reverse(主轴向左)|
- column(主轴向下)|
- column-reverse(主轴向上)
来设置主轴方向。
###### 子项目如何在主轴上排列呢？
> 我们可以通过设置justify-content设置子项目在主轴上的排列方式

justify-content:
- flex-start(向主轴起始位置对齐)|
- flex-end(向主轴终点位置对齐) |
- center(向主轴中心位置对齐) |
- space-between(两端对齐) | 
- space-around;
###### 子项目如何在交叉轴上排列呢？
> 我们可以通过设置align-item设置子项目在交叉轴上的排列方式

align-item:
- flex-start(向交叉轴起始位置对齐)| 
- flex-end(向交叉轴终点位置对齐) | 
- center(交叉轴中心位置对齐) |  
- baseline(基线对齐) | 
- stretch;
###### 子项目在一行(列)上放不下想换行该怎么办？
> 这个时候我们可以设置flex-wrap属性给容器
默认情况下，项目都排在一条线（又称"轴线"）上。flex-wrap属性定义，如果一条轴线排不下，如何换行。

flex-wrap:
 - nowrap(不换行) | 
 - wrap(换行) | 
 - wrap-reverse(换行，第一行在下方);
###### 换行之后行与行之间该如何排列？
> 此时采用align-content属性就可以解决问题了，align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

align-content:
- flex-start：与交叉轴的起点对齐。
- flex-end：与交叉轴的终点对齐。
- center：与交叉轴的中点对齐。
- space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
- space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
- stretch（默认值）：轴线占满整个交叉轴。

###### 那个子项目可以设置哪些属性呢？
> 以下6个属性设置在项目上。

  - order
  - flex-grow
  - flex-shrink
  - flex-basis
  - flex
  - align-self
>  order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0,order属性针对单个项目或者一类项目设置即可修改他所在的位置

>  flex属性 flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。 

>  align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。

 align-self:
 - auto | 
 - flex-start | 
 - flex-end | 
 - center | 
 - baseline |
 - stretch;
> 其它几个不太常用（flex-grow, flex-shrink 和 flex-basis）这里暂时不做研究