# 百度前端技术学院课程练习
## Day-5-6
### 任务：一个简历 + 三个样式表
- [resume.html](https://whuhzx.github.io/FrontEndCollege2018/Day-05-06/resume.html)
- style_1.css
- style_2.css
- style_3.css

## Day-7-8
### 任务一
#### 实现一个两栏布局，左侧占30%宽度，右侧占70%宽度
- [1-1](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/1-1.html)：float + float
- [1-2](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/1-2.html)：float + margin-left
- [1-3](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/1-3.html)：inline-block + inline-block
- [1-4](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/1-4.html)：float + absolute
- [1-5](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/1-5.html)：absolute + margin-left
- [1-6](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/1-6.html)：float + BFC
- [1-7](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/1-7.html)：flex

#### 实现一个两栏布局，左侧固定宽度，右侧根据浏览器宽度进行自适应变化
- [2-1](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/2-1.html)：float + float
- [2-2](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/2-2.html)：float + margin-left
- [2-3](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/2-3.html)：inline-block + inline-block
- [2-4](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/2-4.html)：float + absolute【absolute 定位后元素会 inline-block 化】
- [2-5](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/2-5.html)：absolute + margin-left
- [2-6](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/2-6.html)：float + BFC
- [2-7](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/2-7.html)：flex

#### 实现一个两栏布局，右侧固定宽度，左侧根据浏览器宽度进行自适应变化
- [3-1](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/3-1.html)：float + float
- [3-2](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/3-2.html)：margin-right + float
- [3-3](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/3-3.html)：inline-block + inline-block
- [3-4](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/3-4.html)：float + absolute【absolute 定位后元素会 inline-block 化】
- [3-5](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/3-5.html)：absolute + margin-right
- [3-6](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/3-6.html)：float + BFC
- [3-7](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/3-7.html)：flex

#### 实现一个三栏布局，左侧固定宽度，右侧固定宽度，中间部分宽度随浏览器宽度变化而自适应变化
- [4-1](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/4-1.html)：float + float + float;
- [4-2](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/4-2.html)：inline-block + inline-block + inline-block
- [4-3](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/4-3.html)：absolute + (margin-left、margin-right) + absolute
- [4-4](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/4-4.html)：圣杯布局
- [4-5](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/4-5.html)：双飞翼布局
- [4-6](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/4-6.html)：flex

笔记:float + (margin-left、margin-right) + float 方案不行。block（center）元素会忽视浮动元素（left），但是浮动元素（right）不会忽视 block 元素。即，block 元素即使设置了 margin 仍然占据一行，后面的浮动元素（right）无法填补上其空隙。

#### 实现一个三栏布局，左侧固定宽度，中间固定宽度，右侧根据浏览器宽度变化而自适应变化
- [5-1](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/5-1)：float + float + float;
- [5-2](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/5-2)：inline-block + inline-block + inline-block
- [5-3](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/5-3)：absolute + absolute + margin-left
- [5-4](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/5-4)：float + float + margin-left
- [5-5](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/5-5)：float + float + BFC
- [5-6](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/5-6)：flex

### 任务二
按设计稿实现HTML页面及CSS样式
- [task2.html](https://whuhzx.github.io/FrontEndCollege2018/Day-07-08/task/task2.html)
- task2_style.css

## Day-9-11
### 任务：按照设计稿完成页面设计
- [index.html](https://whuhzx.github.io/FrontEndCollege2018/Day-09-11/index.html)
- style.css
- /image/

## Day-12-15
### 任务：按照设计稿完成复杂页面的设计
- [index.html](https://whuhzx.github.io/FrontEndCollege2018/Day-12-15/index.html)
- style.css
- /image/

## Day-16
### 任务一：加减乘除计算
- [calculate.html](https://whuhzx.github.io/FrontEndCollege2018/Day-16/calculate.html)

### 任务二：简历隐藏/显示内容
- [resume.html](https://whuhzx.github.io/FrontEndCollege2018/Day-16/resume.html)
- style_3.css

## Day-17-18
- [task1.html](https://whuhzx.github.io/FrontEndCollege2018/Day-17-18/task1.html)：除数为0的时候，在 console 进行提示
- [task2.html](https://whuhzx.github.io/FrontEndCollege2018/Day-17-18/task2.html)：把十进制整数转化为二进制
- [task3.html](https://whuhzx.github.io/FrontEndCollege2018/Day-17-18/task3.html)：在 console 中输出从 1 到 100 各数字，当数字为 3 的倍数的时候，输出"PA"
- [task4.html](https://whuhzx.github.io/FrontEndCollege2018/Day-17-18/task4.html)：在网页中，使用 table 来实现一个九九乘法表
- [task5.html](https://whuhzx.github.io/FrontEndCollege2018/Day-17-18/task5.html)：当用户访问页面的时候，根据当前时间，输出不同的问候语

## Day-19
- [task1.html](https://whuhzx.github.io/FrontEndCollege2018/Day-19/task1.html)：利用 getElementById()、getElementsByTagName()、childNodes 和 parentNode 实现任务中的函数
- [task2.html](https://whuhzx.github.io/FrontEndCollege2018/Day-19/task2.html)：利用 querySelector 和 querySelectorAll 实现任务中的函数

## Day-20-21
- [task1.html](https://whuhzx.github.io/FrontEndCollege2018/Day-20-21/task1.html)：点击按钮或者按下键盘按键，执行相关操作
- [task2.html](https://whuhzx.github.io/FrontEndCollege2018/Day-20-21/task2.html)：当用户选择单选框时，显示其中一个下拉选项，隐藏另一个的下拉选项
- [task3.html](https://whuhzx.github.io/FrontEndCollege2018/Day-20-21/task3.html)：点击某一个 li 元素时，将 li 的背景色显示在 p 标签内， 同时将 p 标签的文字颜色设置成 li 的背景色
- [task4.html](https://whuhzx.github.io/FrontEndCollege2018/Day-20-21/task4.html)：使用 setTimeout 或 setInterval 实现元素的淡入淡出等功能
- [task5.html](https://whuhzx.github.io/FrontEndCollege2018/Day-20-21/task5.html)：用 CSS Sprite 实现一个帧动画

## Day-22-24

## Day-25-27
- 课程页面：[倒数开始 滴答滴 滴答滴](http://ife.baidu.com/course/detail/id/51)
- [task1.html](https://whuhzx.github.io/FrontEndCollege2018/Day-25-27/task1.html)：封装函数
- [task2.html](https://whuhzx.github.io/FrontEndCollege2018/Day-25-27/task2.html)：设计一个简单的时钟，实时更新当前时间
- [task3.html](https://whuhzx.github.io/FrontEndCollege2018/Day-25-27/task3.html)：设计一个稍微复杂的时钟。根据要求，html 内有一堆 Select 用于选择日期和时间，在选择后，实时在 id 为 result-wrapper 的 p 标签中显示所选时间和当前时间的差值。

## Day-28-30
- 课程页面：[给爱的人发个邮件吧](http://ife.baidu.com/course/detail/id/52)
- [index.html](https://whuhzx.github.io/FrontEndCollege2018/Day-28-30/index.html)：输入框输入邮箱地址自动提示

## Day-31-33
- 课程页面：[我是精明的小卖家（一）](http://ife.baidu.com/course/detail/id/53)
- [index.html](https://whuhzx.github.io/FrontEndCollege2018/Day-31-33/index.html)：根据地区和产品筛选出数据，并将其以表格的形式呈现在网站上


