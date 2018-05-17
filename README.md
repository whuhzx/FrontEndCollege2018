# 百度前端技术学院课程练习
## Day-5-6
### 任务：一个简历 + 三个样式表
- resume.html
- style_1.css
- style_2.css
- style_3.css

## Day-7-8
### 任务一
#### 实现一个两栏布局，左侧占30%宽度，右侧占70%宽度
- 1-1：float + float
- 1-2：float + margin-left
- 1-3：inline-block + inline-block
- 1-4：float + absolute
- 1-5：absolute + margin-left
- 1-6：float + BFC
- 1-7：flex

#### 实现一个两栏布局，左侧固定宽度，右侧根据浏览器宽度进行自适应变化
- 2-1：float + float
- 2-2：float + margin-left
- 2-3：inline-block + inline-block
- 2-4：float + absolute【absolute 定位后元素会 inline-block 化】
- 2-5：absolute + margin-left
- 2-6：float + BFC
- 2-7：flex

#### 实现一个两栏布局，右侧固定宽度，左侧根据浏览器宽度进行自适应变化
- 3-1：float + float
- 3-2：margin-right + float
- 3-3：inline-block + inline-block
- 3-4：float + absolute【absolute 定位后元素会 inline-block 化】
- 3-5：absolute + margin-right
- 3-6：float + BFC
- 3-7：flex

#### 实现一个三栏布局，左侧固定宽度，右侧固定宽度，中间部分宽度随浏览器宽度变化而自适应变化
- 4-1：float + float + float;
- 4-2：inline-block + inline-block + inline-block
- 4-3：absolute + (margin-left、margin-right) + absolute
- 4-4：圣杯布局
- 4-5：双飞翼布局
- 4-6：flex

笔记:float + (margin-left、margin-right) + float 方案不行。block（center）元素会忽视浮动元素（left），但是浮动元素（right）不会忽视 block 元素。即，block 元素即使设置了 margin 仍然占据一行，后面的浮动元素（right）无法填补上其空隙。

#### 实现一个三栏布局，左侧固定宽度，中间固定宽度，右侧根据浏览器宽度变化而自适应变化
- 5-1：float + float + float;
- 5-2：inline-block + inline-block + inline-block
- 5-3：absolute + absolute + margin-left
- 5-4：float + float + margin-left
- 5-5：float + float + BFC
- 5-6：flex

### 任务二
按设计稿实现HTML页面及CSS样式

## Day-9-11
### 任务：按照设计稿完成页面设计
- index.html
- style.css
- image