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

