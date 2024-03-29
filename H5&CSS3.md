## 面试题

面试题: 什么是web标签语义化

标签语义化的目的在于能够直观的认识标签和属性的用途和作用，好处：

1. 使页面的内容结构化：结构更清晰，便于不同的屏幕设备解析；

2. 有利于SEO：和搜索引擎建立良好的关系，有助于爬虫更多的有效信息；

3. 便于团队开发和维护；

## H5新增属性

`section`: 表示页面中的一个内容区块,比如章节、页眉、页脚或页面的其他部分。可以和h1、h2……等元素结合起来使用，表示文档结构。

`article`: 表示页面中一块与上下文不相关的独立内容。比如一篇文章。

`aside`: 表示一个页面的一部分，它的内容跟这个页面的其它内容的关联性不强，或者是没有关联，单独存在。aside元素通常显示成侧边栏(sidebar)或一些插入补充内容。通常用来在侧边栏显示一些定义，比如目录、索引、术语表等；也可以用来显示相关的广告宣传，作者的介绍，相关链接，当前页内容简介等。

`header`: 表示页面中一个内容区块或真个页面的标题。

`hgroup`: 表示对整个页面或页面中的一个内容区块的标题进行组合。

`footer`: 表示整个页面或页面中一个内容区块的脚注。一般来说，他会包含创作者的姓名、创作日期以及创作者的联系信息。

`nav`: 表示页面中导航链接的部分。

`figure`: 表示一段独立的流内容，一般表示文档主体流内容中的一个独立单元。

### 新增多媒体标签

+ `video` 视频标签
  1.  `autoplay` 自动播放(muted 开启静音  视频自动播放就可以生效)

  2.  `controls` 是否显示默认播放控件

  3.  `loop` 循环播放

  4.  `preload` 预加载，同时设置了autoplay，此属性将失效

  5.  `width` 设置播放窗口宽度

  6.  `height` 设置播放窗口的高度

### 表单新增

+ email 限制用户输入必须为Email类型

+ tel 手机号码

+ url 限制用户输入必须为URL类型

+ number 只能输入数字

+ search 具有搜索意义的表单属性

+ range 范围 滑动条

+ color 拾色器

+ time 时间

+ date 选取日、月、年

+ datetime 选取时间、日、月、年（UTC 时间）(移动支持)

+ datetime-local 选取时间、日、月、年（本地时间）

+ month 选取月、年

+ week 选取周和年


## CSS3新属性

### border-radius
 
1. 分为4个值 分别是左上 右上 右下 左下

2. 半圆是 左上;右上/左下右下;设置高度的一半

3. transform: rotate(90deg) 旋转xx度

### 属性选择器

#### a[href] (标签[属性])

1.  `  *  `可以选择包含某个字符的a标签 包含 n这个 字符 a[title*='n'] 

2.  ` ^  `可以选择以某个字符开头的a标签 如 以w开头 a[title^='w'] 

3. `  $   `可以选择以某个字符结束的a标签 如 以t结束 a[title$='t']

### 伪类选择器

1. a:link :active(点击时) :visited(访问过) :hover(鼠标放上去时)

#### 伪类结构选择器

+ 通过元素来确定此元素的父元素

        - E:first-child第一个子元素
 
        - E:last-child最后一个子元素

        - E:nth-child(n) 第n个子元素

        - E:nth-last-child(n) 同E:nth-child(n) 相似，只是倒着计算；

+ n支持简单的表达式

  - (2n)代表偶数

  - (2n+1)代表奇数

  - (3n) 所有三的倍数

  - (-1n+5)选中前5个

#### 目标伪类选择器

+ E:target 结合锚点进行使用，处于当前锚点的元素会被选中

#### 伪元素选择器

+ 语法为E::before、E::after
        
  - 这是一个行内元素需要转换成块元素

  - 需要写content:'内容'

### 颜色(hsl)

+ H 色调 取值范围0~360，0/360表示红色、120表示绿色、240表示蓝色

+ S 饱和度 取值范围0%~100%

+ L 亮度 取值范围0%~100%

+ A 透明度 取值范围0~1

+ 关于透明度：
  - opacity只能针对整个盒子设置透明度，子盒子及内容会继承父盒子的透明度；

  - transparent 不可调节透明度，始终完全透明

### 文本阴影

`text-shadow`{水平方向 垂直方向 模糊度 颜色}

+ 浮雕文字凸 text-shadow: -1px -1px 1px #fff, 1px 1px 1px #000;

+ 浮雕文字凹 text-shadow: -1px -1px 1px #000, 1px 1px 1px #fff;


### 盒子阴影

`box-shadow`{水平方向 垂直方向 模糊度 扩展值 颜色}

### 盒模型

+ CSS2盒模型:内容+ padding +border box-sizing:content-box

+ css3盒模型:padding和border会挤压内容 设置的宽高就是在实际页面中的宽高   box-sizing: border-box

### 边框图片

+ 语法:

  * `border-image-source: url('border.png')`;引入图片,

  * `border-image-slice`	图片边框向内偏移量
       
  * `border-image-width`	边框宽度

  * `border-image-outset`      边框图像区域超出边框的量

  * `border-image-repeat`图像边框是否应平铺(repeated)、铺满(rounded)或拉伸(stretched)

### 线性渐变

+ 语法: `background:linear-gradient(to方向, 颜色, 颜色)`

+ 添加私有化前缀时 方向不带to 而且正好相反

`background: linear-gradient(to right, red 20%, yellow 60%)`

        中间颜色产生渐变

        20%以前用红色填充 60%以后用黄色填充

### 径向渐变

+ 语法 `radial-gradient(center(圆形或者椭圆默认为圆), shape size(指定渐变开始的方向), start-color, ..., last-color)`

### 背景

* 语法 `background-size:cover/contain`

  * cover不保证图片完整性,但会填充满盒子
  * contain 保证图片完整性,但是会留白

### 背景增强属性

1. 裁剪背景

  * 语法 `background-clip` (padding-box从padding开始裁剪)(border-box从border开始裁剪 默认)(content-box从内容开始裁剪)

2. 设置背景从/ /为起点

  * 语法 `background-origin`(padding-box以padding为起点 默认)(border-box以border为起点)(content-box以内容为起点)

### 过渡

1. ` transition-property` 添加过渡的值 

2. `transition-duration` 过渡完成的时间

3. `transition-delay` 过渡延迟开始的时间

4. `transition-timing-function`过渡运动的函数 

  * linear
  * ease
  * ease-in
  * ease-out
  * ease-in-out
  * cubic- bezier(n, n, n, n)

5. `transition: all .4s ease 1s;`简写,注:延迟时间要写到最后.

### 2d变换

1. transform 可以实现  2d变换  旋转  平移(translate)   拉伸  缩放

  * `transform: translate(20px, 10px)` 平移

  * `transform: rotate(45deg)` 旋转
        
        * 旋转特定位置 `transform-origin: 值可以位数值也可以为top bottom left right;`

  * `transform: scale(0.8);` 缩放

  * `transform: skew(45deg, 30deg);`拉伸

  * 可以简写 `transform:translate() rotate() scale() skew()`

### 3d变换

1. transform的平移和旋转有x,y,z轴 可以实现x,y,z轴的旋转/平移

2. 3D变换需要设置景深 `perspective`
  
  * 作为一个属性，设置给父元素，作用于所有3D转换的子元素	
  * 作为transform属性的一个值，做用于元素自身

3. 3D的呈现`transform-style`
  
  * `flat`：所有子元素在 2D 平面呈现 默认值
  * `preserve-3d` 开启3D舞台 

4.  `backface-visibility` 设置背面是否可见visible(默认值可见)/hidden(不可见)

### BFC

1. 什么是BFC?

   BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。反之也如此。包括浮动，和外边距合并等等，
   因此，有了这个特性，我们布局的时候就不会出现意外情况了。
   

2. 什么情况下可以触发BFC?

   - float属性不为none

   - position为absolute或fixed

   - display为inline-block, table-cell, table-caption, flex, inline-flex

   - overflow不为visible

3. BFC能用来做什么？

  - 清除元素内部浮动

  - 解决外边距合并问题

  - 制作右侧自适应的盒子问题










