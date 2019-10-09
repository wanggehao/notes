## 事件

* JS是以事件驱动为核心的一门语言

### 事件的三要素

#### 事件的三要素:事件源 事件 事件驱动程序

* 事件源:引发后续事件的html标签

* 事件: JS定义好的

* 事件驱动程序:对样式和HTML的操作也就是DOM

#### 代码书写步骤如下：（重要）

（1）获取事件源：document.getElementById(“box”);

（2）绑定事件： 事件源 box.事件 onclick = function(){ 事件驱动程序 };

（3）书写事件驱动程序：关于 DOM 的操作。

### 常见的事件

`onabort`图像加载中断
`onblur`元素失去焦点
`onchange`用户改变域的内容
`onclick`用户点击某个对象
`ondblclick`用户双击某个对象
`onerror`当加载文档或图像时发生某个错误
`onfocus`元素获得焦点
`onkeydown`某个键盘的键按下
`onkeypress`某个键被按下或者按住
`onkeyup`某个键松开
`onload`图像加载完成
`onmousedown`某个鼠标键被按下
`onmousemove`鼠标被移动
`onmouseout`鼠标从某元素移开
`onmouseover`鼠标被移到某元素之上
`onmouseup`	某个鼠标按键被松开
`onreset`	重置按钮被点击
`onresize`	窗口或框架被调整尺寸
`onselect`	文本被选定
`onsubmit`	提交按钮被点击
`onunload`	用户退出页面
`onmouseenter/leave`鼠标放上去/移开

### 获取事件源

* 获取事件源通过 id  class  标签名

* 通过类名标签名获取到的是`类数组`具备length 下标 但是不具备 数组的方法 需要通过下标获取到具体的DOM对象 可以使用for循环

### 绑定事件的方式

* 第一种方式:  给dom 对象  增加相应的 事件属性
```js
 pEl.onclick = function () {
     // 要做的事情
    }
```

* 第二种方式:  直接在标签元素 上 添加 事件 属性

### 样式的修改

* 通过修改 dom对象的 style(行内样式)  属性  来 改变样式

* 通常不会再 js 当中这样过多的 修改样式  会造成耦合

* 通常通过修改类名的方式来达到想要的效果

### 通过关系获取事件源

* 获取父级元素:节点.parentNode;
* 获取兄弟节点:
* 下一个节点:
  - nextSibling：
    火狐、谷歌、IE9+版本：都指的是下一个节点（包括标签、空文档和换行节点）。
    IE678 版本：指下一个元素节点（标签）。
  - nextElementSibling：
    火狐、谷歌、IE9+版本：都指的是下一个元素节点（标签）。

  - 总结：为了获取下一个元素节点，我们可以这样做：在 IE678 中用 nextSibling，在火狐谷歌 IE9+以后用 nextElementSibling，于是，综合这两个属性，可以这样写：
    下一个兄弟节点 = 节点.nextElementSibling || 节点.nextSibling;

* 上一个节点:
   - previousSibling：
   - previousElementSibling：

* 获取子节点:
`firstChild firstElementChild`第一个
`lastChild  lastElementChild`最后一个
`childNodes`    获取所有子节点
`children`      获取所有元素子节点
   - 怎么判断是一个 元素节点  nodeType  
       - 1 === 元素节点
       - 3 === = 换行节点
       - 8=== 注释节点
       - nodeType == 2 表示是属性节点

### 节点的增删改查

* 创建节点: 新的标签(元素节点) = document.createElement("标签名");

* 插入节点:
   - 父节点.appendChild(新的子节点);从后添加
   - 父节点.insertBefore(新的子节点, 作为参考的子节点)

* 删除节点:父节点.removeChild(子节点);

* 复制节点:要复制的节点.cloneNode(); 括号里不带参数和带参数false，效果是一样的。
          要复制的节点.cloneNode(true); 深复制

### 节点属性操作

*  getAttribute('属性名') 获取属性

*  元素节点.setAttribute(属性名, 新的属性值);修改增加属性

*  元素节点.removeAttribute(属性名);删除属性

### 类名操作

* 追加active类名
```js
 box.classList.add('active');
```
*  删除active 类名
```js
box.classList.remove('active');
```

* `toggle` 有则删除  无则添加
```js
 pEl.classList.toggle('red');
```

### 节点内容操作

* `innerText` 会被当做内容解析
```js
pEl.innerText = '<p>今天天气很好</p>';//显示在页面上 <p>今天天气很好</p>
```

* `innerHTML`会被当做标签解析
```js
div.innerHTML = '<p>今天天气很好</p>'//显示在页面上 今天天气很好
```
### 获取事件源
```js
 var box = document.querySelector('.box'); // 拿到了  实际的 对象  不是伪数组
  var lis = document.querySelectorAll('li'); // 类数组
```

### 自定义属性值

* 在HTML标签里边可以添加自定义属性值`data-***`

* 在js中通过 `Node.dataset['info']` 我们便可以获取到自定义的属性值

### addEventListener

* addEventListener 使用
  - 语法：target.addEventListener(type,listener,useCapture]);
  - target： 文档节点、document、window 或 XMLHttpRequest。 (事件源)
  - type： 字符串，事件名称，不含“on”，比如“click”、“mouseover”、“keydown”等。
  - listener ：实现了 EventListener 接口或者是 JavaScript 中的函数
  - useCapture ：是否使用捕获，一般用 false。true 代表捕获，false 代表冒泡
    - 冒泡  就是  从里到外 触发  false
    - 捕获  就是   从外到里 触发  true

* addEventListener移除
  - 移除时，必须和绑定时一一对应
```js
w2.addEventListener('click', foo, false)
w2.removeEventListener('click', foo, false);
function foo() {
  alert('不凡');
}
```

### 定时器

* setTimeout(); 延迟执行

* setInterval(); 循环执行

* clearTimeout(); 清除延迟执行的定时器

* clearInterval(); 清除循环执行的定时器