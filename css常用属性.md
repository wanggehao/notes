# html和css常用属性

## html属性
`iframe`内联框架标签

## input属性
1. tybe
   + text  单行文本输入框
   + password 密码输入框
   + radio 单选按钮
   + checkbox  复选框
   + button 普通按钮
   + submit 提交按钮
   + reset  重置按钮
   + image  图像形式的提交按钮
   + file 文件域

2. name 值自定义 控件的名称

3. value 自定义input在空间中昂的默认文本值

4. size 正整数  input在页面中的显示宽度

5. checked 默认被选中的项

6. maxlength 值为正整数 文本框中最多可输入的字符

## 常用属性
`width`宽  `height`高值为px或em等  

`background-color`背景颜色 值为color

`color`字体颜色值为color

`font-size`字体大小值为px或em

`text-aligh` 字体位置 值为 left center right

`text-indent` 首行缩进 值为px em等

`font-family` 字体值为 微软雅黑 Microsoft YaHei、黑体 SimHei、Arial sans-serif

`font-weight` 字体加粗 值为 700到900

`font-style` 字体样式 值为Italic 斜体 / normal 正常 默认值为normal

`line-height` 行高 值为 单位： px /倍数 / 百分比 ;- 设置文字的行间距- 单行文字垂直居中 ：行高=父类盒子高度

`font`	字体缩写	`font:italic bolder 20px/1.2 'Arial','Microsoft YaHei'

`text-decoration:none` 去a元素的下划线

a标签填充盒子设置宽高为100%

`list-style:none`;去掉li前面的黑点

`display:none;` 隐藏元素，不再在文档中占据位置。

显示：可以将 display 设置为其他属性值，不为 none 即可。

`visibility:hidden;`(visible显示) 隐藏元素，隐藏后其在文档中所占的位置会依然保持，不会被其他元素覆盖。

 `border-radius`: 50% 变圆

 `active`激活位属性值

 `vertical-align` 属性设置元素的垂直对齐方式。

 `cursor: pointer` 鼠标放上去变成手形状

 `:focus `当鼠标聚焦时

 `outline: none;`去掉input鼠标聚焦时的蓝色边框

a元素 target表示跳转窗口位置。_self：在当前页面窗口中打开，默认值,_blank: 在新窗口中打开

## 图片

`background-color`	背景图片颜色    值为	color

`background-image`	背景图片 值为	url(图片引入路径);

`background-repeat` 平铺方式    值为repeat(平铺) 、 no-repeat(不平铺) 、 repeat-x(x轴水平平铺) 、 repeat-y(y轴垂直平铺)

`background-position`	图片位置    值为left、 right、 top、 bottom、 center

`background-attachment`	背景滚动	scroll(滚动)、fixed(固定的) (注意：基于 body 的定位）

缩写background:color url() repeat left scroll (顺序不能错)

## 盒模型

盒子模型四个属性:

内容区域、padding（内边距）、border（边框solid实线）、margin（盒子与盒子的距离）。

margin:0 auto 让块元素居中

float: 浮动

嵌套崩塌
给子类盒子 设置margin-top ,作用到了 父类盒子身上

 怎么解决?
1. 给父类盒子 添加 overflow: hidden;
2. 给父类添加极小的padding 或者border

 层级的概念 z-index(定位元素) 数值越大层级越高




## 标签的表现形式

1. 块级元素独占一行宽高有效 如div p元素 h元素

2. 行级元素同一行显示宽高有效 如 input img

3. 行内块元素 同一行显示宽高无效 如a元素 span

4. display可以修改元素性质

1). block：设置元素为块元素

2). inline：设置元素为行级元素

3). inline-block：设置元素为行内块元素

转换的必要性：比如可以把a标签转换为块状元素，设置宽高，使用户可点击的区域增大，进而实现一个按钮的样式。


## css3新属性

1. transform 位移旋转拉伸