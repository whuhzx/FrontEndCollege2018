# CSS布局学习笔记
## 布局要考虑的问题
宽度固定？宽度自适应？内容高度？不同列高度相同？

采用什么样的 CSS 特性？

## 布局可能会使用到的 CSS 特性
### 定位（relative、absolute、fix）
定位能够改变基本的文档流

static：处在正常文档流中

relative：处在正常文档流中。元素相对于自己原先的位置移动，但是占据文档流的仍然是原先的位置。

absolute：脱离文档流。元素相对于最近的设置了 relative 特性的祖先元素的位置移动（如果没有元素设置了 relative，则相对于<html>位置进行移动）。
注意：绝对定位会使得元素 inline-block 化，见[CSS 相对/绝对定位系列](http://www.zhangxinxu.com/wordpress/2010/12/css-%E7%9B%B8%E5%AF%B9%E7%BB%9D%E5%AF%B9%E5%AE%9A%E4%BD%8D%E7%B3%BB%E5%88%97%EF%BC%88%E4%B8%80%EF%BC%89/)

fix：脱离文档流。元素固定在浏览器的相对位置。

注意：定位时要考虑 z-index。且 z-index 只适用于定位元素。z-index 值越大该元素在浏览器视觉中处于越上层。如果父元素 z-index 有效，那么子元素无论是否设置 z-index 都和父元素一致，会在父元素上方。

参考资料：
- [MDN：定位](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/%E5%AE%9A%E4%BD%8D)
- [定位实例练习](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Practical_positioning_examples)

#### 块级元素格式化上下文（BFC）
BFC 元素可以看作是隔离了的独立容器，容器里面的元素不会在布局上影响到外面的元素，并且 BFC 具有普通容器没有的一些特性。

特性：1、阻止外边距折叠；2、BFC 作为父元素可以包含浮动元素，使得容器不会塌陷（给父元素设置`{overflow: hidden}`就是触发其 BFC）；3、BFC 可以阻止元素被浮动元素覆盖【正常情况下，浮动元素的块级兄弟元素会无视浮动元素的位置，尽量占满一整行，这样重叠的部分就会被浮动元素覆盖，若该兄弟元素触发 BFC ，就可以阻止这种情况的发生。】

触发 BFC 的条件

[详说 Block Formatting Contexts](http://kayosite.com/block-formatting-contexts-in-detail.html)

[CSS深入理解流体特性和BFC特性下多栏自适应布局](http://www.zhangxinxu.com/wordpress/2015/02/css-deep-understand-flow-bfc-column-two-auto-layout/)

### box-sizing
`box-sizing:border-box`【width 和 height 的内容包含 padding 及 border】

### display:inline-block
block：块级元素，可设置长宽，占据单独一行（根据此特性，元素可实现宽度自适应）。另外，块级元素会认为浮动不存在（未清除浮动的情况下）

inline: 内联元素，无法设置长宽，盒子大小由里面的文字撑起。设置的 margin, border 也不会对其它盒模型产生效果

inline-block：可设置长宽，但是不会单独占据一行。
根据这个特性，若把元素的 display 从 block 改成 inline-block， 可以让元素产生类似浮动的效果（多个 inline-block 可以不设置浮动就共同占据同一行）。

这里需要注意的是，将块级元素转设成`inline-block`后，inline-block 之间会产生空格（几个并列的行内元素也会产生空格），在布局的时候需要给父容器添加`{font-size: 0;}`或者`{letter-spacing: -?px}`才能消除空格。但是这两个属性值会被所有子元素所继承，因此又需要另外给每个子元素设定固定的`fontsize`和`letter-spacing:0`。
因此这种布局方法不适合大型布局，只适用于小型布局。

`inline-block`的另一个好处是：同一行的inline-block元素如果高度不一致，行盒子会以最高的盒子为基准；而同一行的浮动盒子如果高度不一致，会造成浮动的犬牙交错，因此必须要给盒子设立定高

[张鑫旭：拜拜了,浮动布局](http://www.zhangxinxu.com/wordpress/2010/11/%E6%8B%9C%E6%8B%9C%E4%BA%86%E6%B5%AE%E5%8A%A8%E5%B8%83%E5%B1%80-%E5%9F%BA%E4%BA%8Edisplayinline-block%E7%9A%84%E5%88%97%E8%A1%A8%E5%B8%83%E5%B1%80/)

### margin 负边距
文档流只能向左向上流动

在一般文档流中元素的负边距和浮动元素的负边距有什么区别？
浮动元素会被顶到上一行（根据浮动的特性），一般文档流中的元素不会被顶到上一行

margin-left 和 margin-right 负边距的区别又在哪里？
margin-left 的参考线是元素盒子左边的盒子；margin-right 负值是以元素盒子本身的右边 border 为参考线。此外，margin-left 负值可以覆盖左边的元素；margin-right 负值不能覆盖左边的元素。

例子：圣杯布局和双飞翼布局

[负边距详解](https://segmentfault.com/a/1190000003942591)
[浅谈margin负值](https://zhuanlan.zhihu.com/p/25892372)

### 百分比宽度

### float 浮动
#### 浮动的特性
1、破坏性（导致父元素塌陷）
2、包裹性（盒子宽度为内容宽度，而非占满一行，即元素的 inline-block 化）
3、块级元素忽略浮动元素的存在，而行内元素会环绕浮动元素
4、清除空格

#### 清除浮动的方法
1、after 伪类


2、父元素设置`{overflow: auto}`或者`{overflow: hidden}`

3、兄弟元素 `{clear:both}`

[kayo：详说清除浮动](http://kayosite.com/remove-floating-style-in-detail.html)
[kayo：详说 Block Formatting Contexts](http://kayosite.com/block-formatting-contexts-in-detail.html)

### calc()方法
CSS3 新特性，calc() 相当于一个计算函数，计算出元素的宽，可以用于宽度自适应布局

用法`width: calc()`，括号内用`%、+、-、*、/`

[CSS3的calc()使用](https://www.w3cplus.com/css3/how-to-use-css3-calc-function.html)

### flex 布局
最灵活的布局，易于实现垂直居中。

#### 基本概念
采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称"项目"。设为 Flex 布局以后，子元素的 float、clear 和 vertical-align 属性将失效。

容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做 main start，结束位置叫做 main end；交叉轴的开始位置叫做cross start，结束位置叫做cross end。

项目默认沿主轴排列。单个项目占据的主轴空间叫做 main size，占据的交叉轴空间叫做 cross size。

#### 容器的属性
- flex-direction 属性决定主轴的方向（即项目的排列方向）
- 默认情况下，项目都排在一条线（又称"轴线"）上。flex-wrap  属性定义，如果一条轴线排不下，如何换行。
- flex-flow属性是 flex-direction 属性和flex-wrap属性的简写形式，默认值为row nowrap。
- justify-content 属性定义了项目在主轴上的对齐方式。
- align-items 属性定义项目在交叉轴上如何对齐

[MDN：弹性盒子](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox)
[Flex 布局教程：语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)
[Flex 布局教程：实例篇](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)

### grid 布局 

### 使用特定框架
如 Boostrap

## 不同的布局种类及其实现
### 单列居中布局
`#main{margin: 0 auto;}`

### 两列布局实现的七种方法(一列定宽+一列自适应)
[七种实现左侧固定，右侧自适应两栏布局的方法](https://segmentfault.com/a/1190000010698609)
1、inline-block + inline-block
自适应栏使用 calc()

2、float + float
自适应栏使用 calc()

3、float + margin-left
需要计算 margin 值

4、absolute + margin-left
需要计算 margin 值

5、float + BFC
左边盒子浮动，右边盒子`{overflow: auto;}` 触发BFC

6、flex

7、grid

### 三列布局（两边固定宽度+中间自适应）
#### 绝对定位 + margin

#### margin 负值法
[圣杯布局](http://alistapart.com/article/holygrail)
[圣杯布局和双飞翼布局](https://theqwang.github.io/2016/01/08/%E6%B5%85%E6%9E%90%E5%9C%A3%E6%9D%AF%E5%B8%83%E5%B1%80%E5%92%8C%E5%8F%8C%E9%A3%9E%E7%BF%BC%E5%B8%83%E5%B1%80/)

笔记：圣杯布局中，left 元素和 center 元素之间有间隔【wrap 设置了 padding】，也就是说 left 和 center 虽然都设置了浮动，但是没有贴合在一起。但是双飞翼布局中，left 元素和 center 元素之间没有间隔，两者虽然不在一行，但确是贴合在一起的。

圣杯布局和双飞翼布局的特性：兼容性好，中间的主体内容先加载（center 标签在最前面）
圣杯布局和双飞翼布局的差别：圣杯布局 center 部分需要相对定位；双飞翼布局在 center 上多加一个嵌套标签，不需要相对定位。

#### 左右浮动 + margin
这里三个div标签的顺序的关键是要把主体div放在最后，左右两栏div顺序任意。
不足在于：中间主体存在克星，clear:both属性。如果要使用此方法，需避免明显的clear样式。
[张鑫旭：三种三栏网页宽度自适应布局方法](http://www.zhangxinxu.com/wordpress/2009/11/%E6%88%91%E7%86%9F%E7%9F%A5%E7%9A%84%E4%B8%89%E7%A7%8D%E4%B8%89%E6%A0%8F%E7%BD%91%E9%A1%B5%E5%AE%BD%E5%BA%A6%E8%87%AA%E9%80%82%E5%BA%94%E5%B8%83%E5%B1%80%E6%96%B9%E6%B3%95/)

### 实现宽度自适应的方法
block 宽度随着父元素流动
CSS calc()
flex

### 实现居中
[CSS对齐方式](http://www.cnblogs.com/chaixiaozhi/p/8490725.html)
#### 水平居中
1、行内元素的水平居中

父元素设置`{text-align: center}`

2、块状元素水平居中（定宽）

块状元素设置`{margin: xx auto;}`

3、块状元素的水平居中（不定宽）

子元素设置`{display: inline-block;}`
父元素设置`{text-align: center}`

#### 垂直居中（父元素高度固定）
父元素设置`{height: ?px; line-height: ?px}`

1、行内元素的垂直居中
父元素的`height`和`inline-height`高度数值相等

2、块级元素的垂直居中（子元素高度不固定）
父元素设置`{display:table-cell; vertical-align:middle}`

3、块级元素的垂直居中（子元素高度固定）
计算子元素的 margin-top 或 margin-bottom，计算方法为(父元素高度-子元素高度)/2

#### 垂直居中（Flex 布局）


## 其它
名词辨析：固定布局、流体布局、自适应布局

什么是流体特性：块状水平元素，如div元素，在默认情况下（非浮动、绝对定位等），水平方向会自动填满外部的容器；

媒体查询特性（多屏使用）

CSS column（适用于文字分成多列）

