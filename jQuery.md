## jQuery的使用

* 需要下载文件 然后引入

* jQuery  主要版本
  - 1.xx    1版本    支持ie5678.。。
  -	2.xx    2 版本	放弃了对ie5678的支持
  - 需要根据具体项目的需求来选择版本

## jQuery使用方法

1. 获取事件源
  - 事件源的区别:
```js
var box = document.querySelector('.box');
    console.dir(box);
    console.log($('.box'));
    // $('.box') jq对象  是 对  原生dom对象 进行了 包装之后的结果   
    // box  和  $('.box')[0]  是一样的  指的是 原生 dom元素对象
```

2. 绑定事件
  - 绑定事件的区别:
```js
1. //js中
    obj.onclick = function () {
            // 事件处理
    };
    // jQuery中
    $(obj).click(function () {
            // 事件处理
    });
        // 区别
        // obj.onclick 调用属性
        // obj.click() 调用方法
```

3. 写程序代码

## 获取事件源

`$(“#demo”)`选择id为demo的第一个元素 

`$(“.d1”)`选择所有类名（样式名）为dl的元素

`$("div")` 选择所有标签名为div的标签 

`$(“*”)`	选择所有元素

`$(“.arr.arr-l”)`	选择多个指定的元素，

还有CSS中的所有选择器都可以使用

`:eq(index)`	index是从0开始的一个数字，选择序号为index的元素。选择第一个匹配的元素。用法:`$('.box:eq(0)')`

`:gt(index)`	Index 是从0开始的一个数字，选择序号大于index的元素

`:lt(index)`	Index是从0开始的一个数字，选择小于index 的元素

`:odd`	选择所有序号为奇数行的元素

`:even`		选择所有序号为偶数的元素

`:first`	选择匹配第一个元素

`:last`	选择匹配的最后一个元素

`$(“a[href]”)`  title  type  …	选择所有包含href属性的元素

`$(“a[href=’baidu’]”)`	选择href属性值为baidu的所有a标签

`$(“a[href!=’baidu’]”)`	选择所有href属性不等baidu的所有元素，包括没有href的元素

`$(“a[href^=’web’]”)`	选择所有以web开头的元素

`$(“a[href$=’cn’]”)`	选择所有以cn结尾的元素

`$(“a[href*=’i’]”)`	选择所有包含i这个字符的元素，可以是中英文

`$(“a[href][title=’内容’]”)`	选择所有符合指定属性规则的元素，都符合才会被选中。

`find(selector)`	查找指定元素的所有后代元素（子子孙孙）

`children()`	查找指定元素的直接子元素（亲儿子元素）

`siblings()`	查找所有兄弟元素（不包括自己）

`parent()`	查找父元素（亲的）

`eq(index)`	查找指定元素的第index个元素，index是索引号，从0开始 用法:`$(“li”).eq(2).css(“color”, “red”);`
选择所有li元素中的第二个

## mouseover事件跟mouseenter事件的区别

* mouseover/mouseout事件，鼠标经过的时候会触发多次，每遇到一个子元素就会触发一次。

* mouseenter/mouseleave事件，鼠标经过的时候只会触发一次

## 样式 属性 类名 内容的操作

1. 样式:
```js
// jq对象修改样式  使用  css()
$box.css('color', 'red');
// 假如说 我想同时修改多个样式
$box.css({
    color: 'orange',
    'width': '100px',
    'height': '200px',
    'line-height': '200px',
    'background-color': 'green'
})
```

2. 属性:
```js
// 设置属性
 $box.attr('title', '不凡');
 $box.attr('id', 'd1');
 // 设置多个属性
 $box.attr({
     title: '天气',
     id: 'd2'
 })

 // 删除属性  removeAttr()
 $box.removeAttr('title');
```

3. 类名:
```js
$('button:eq(0)').click(function () {
     // 追加类名
      $('.box').addClass('danger');
 });
 $('button:eq(2)').click(function () {
    // 删除类名
     $('.box').removeClass('em');
 });
 $('button:eq(3)').click(function () {
     //判断被选元素是否存在类
    console.log($('.box').hasClass('em'));
});
$('button:eq(4)').click(function () {
    // 对被选元素进行添加/删除类的切换操作
    $('.box').toggleClass('em');
});
```

4. 内容:
* html()   $('p').html()   $("p").html('html 代码')

* text()   $('p').text()   $('p').text('内容')

* value()   $('input').value()   $('input').value('姓名')

* prop()   $('input').prop('checked')   $('input').prop('checked',false)

## DOM对象和jQuery的转换

* jQuery 对象转换为 DOM 对象: `$('#btn')[0]`  `$('#btn').get(0)`

* DOM 对象转换成 jQuery 对象: `var btn = document.getElementById('btn');    $(btn) ====> 把 DOM 对象转成了 jQuery 对象`

## jQ动画

`show()` 显示动画 支持参数:slow：600ms、normal：400ms、fast：200ms 和任意数字(单位:毫秒)和回调函数

`hide()` 隐藏动画 用法参数同显示

`slideUp()` 滑出动画 用法参数同显示

`slideDown()` 滑入动画

`slideToggle()` 滑入/滑出动画 

`fadeIn()` 淡入动画

`fadeOut()` 淡出动画

`fadeToggle()` 淡入/淡出动画

`fadeTo()` 改变透明度到某个值

## jQ自定义动画

`$(selector).animate(styles,speed,easing,callback)`
第一个参数:要修改的css属性(必填);
第二个参数:动画执行所需要的时间(可选);
第四个参数:动画执行完以后立即执行的回调参数;

## 停止动画

1. `stop()`作用：停止当前正在执行的动画

2. `stop(stopAll,goToEnd)`
  1. stopAll: 是否全部停止动画(停止队列中所有动画), 默认 false
  2. goToEnd: goToEnd: 是否将停止的动画, 停在当前动画的最后一个状态

## jQ节点操作

1. 插入节点:`append()`
  - 参数 jq对象 标签字符串 或者DOM对象;
  - 在被选中的标签内部从后面插入
  - 如果是页面中存在的元素， 那么调用 append() 后， 会把这个元素放到相应的目标元素里面去但是， 原来的这个元素， 就不存在了。(剪切)
  - 如果是给多个目标追加元素， 那么方法的内部会复制多份这个元素， 然后追加到多个目标里面

2. `prepend()` 作用： 在被选元素内部从前面追加内容或节点。

3. `after()`作用： 在被选元素之后， 作为兄弟元素插入内容或节点

4. `before()`作用： 在被选元素之前， 作为兄弟元素插入内容或节点

5. 删除节点:
 `$(selector).empty();`
 `$(selector).html(“”);`
 `$(selector).remove();`  //会把对象也干掉

6. 复制节点:`$(selector).clone();`

## bom相关
height()
height(200)
width()
width(100)
取值类型为 num 可以直接参与运算

offset() 作用： 获取或设置元素相对于文档的位置

position() 作用： 获取相对于其最近的具有定位的父元素的位置。

scrollTop() 作用： 获取或者设置元素垂直方向滚动的位置   网页卷进去的 高度
原生兼容写法
     ```js
        var scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
     ```

## on方式绑定事件

语法:
```js
$('.box').on('click', function () {
            console.log('你好')
//off()解绑所有绑定的事件
$('button').click(function () {
    // $('.box').off();//解绑所有
    // $('.box').off('click');//解绑所有点击事件
    $('.box').off('click', 'p');//解绑p标签的点击事件
})
```

## 事件委托

语法:
```js

  // 对于后来生成的元素 没有绑定上 点击事件
  // $('li').click(function () {
  //     console.log($(this).text());
  // })

  // 事件委托  
  $('ul').on('click', 'li', function () {
      console.log($(this).text());
  })//事件委托给目标元素的父元素 可以给后来添加的新元素绑定事件
```

## 事件对象

```js
$('ul').click(function (event) {
      // console.log(event);
      // event  事件对象   提供了事件触发时 的  相关信息
      console.log(event.currentTarget);
      console.log(this);
      console.log(event.target);

      console.log(event.pageX);
  })
```
`event.data` 传递给事件处理程序的额外数据

`event.currentTarget` 事件绑定的对象(事件源), 和 this 相同

`event.pageX` 鼠标相对于文档左部边缘的位置

`event.target` 实际触发事件的对象， 不一定 === this

`event.stopPropagation()；` 阻止事件冒泡

`event.preventDefault();`阻止默认行为

`event.type` 事件类型： click， mouseover…

`event.which` 鼠标的按键类型： 左 1 中 2 右 3

`event.keyCode` 键盘按键代码

## 链式编程

链式编程原理：return this;  调用”任何”一个方法都是返回了对象本身

通常情况下，只有设置操作才能把链式编程延续下去。因为获取操作的时候，会返回获取到的相应的值，无法返回 this

## 隐式迭代

隐式迭代的意思是：在方法的内部会为匹配到的所有元素进行循环遍历，执行相应的方法；而不用我们再进行循环，简化我们的操作，方便我们调用。

如果获取的是多元素的值，大部分情况下返回的是第一个元素的值。

## each()方法

大部分情况下是不需要使用each方法的，因为jQuery的隐式迭代特性。
如果要对每个元素做不同的处理，这时候就用到了each方法

作用：遍历jQuery对象集合，为每个匹配的元素执行一个函数
	$(selector).each(function(index,element){});
Element是一个js对象，需要转换成jquery对象
```js
 $('li').each(function (index, ele) {
    console.log('ele=====>', ele); // dom 对象
    console.log('index===>', index);//下标
 }

 //区别forEach  forEach第一个值是下标 第二个值是数组具体值
```
