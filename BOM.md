# 事件对象 Event

事件触发会生成事件对象`event`，`event` 对象代表事件的状态，比如事件在其中发生的元素、键盘按键的状态、鼠标的位置、鼠标按钮的状态

`event.target` 触发事件的目标元素	获得target兼容型写法  `event.target || event.srcElement`
`event.currentTarget`  绑定事件的目标元素

`e.pageX/Y`		获取鼠标点击的相对于页面的位置
`e.clientX/Y`	获取鼠标点击的相对于可视区域的位置
`e.screenX/Y`	获取鼠标点击的相对于屏幕的位置
`e.offsetX/Y`	表示鼠标指针位置相对于触发事件的对象的位置
获取鼠标相对于绑定事件的元素的位置 `e.pageX/Y - 绑定事件的元素距离页面的左/上边距(offsetLeft/Top)`

`event.type`	事件的类型

`event.key`  键盘按键码	

`event.button` 鼠标点击的按键(只认识三个键) 可在 `onmousedown` 事件中测试

+ === 0 您点击了鼠标左键
+ === 1 您点击了鼠标中键
+ === 2 您点击了鼠标右键



-------------------------------------



## 阻止冒泡

> `event.stopPropagation();`		存在兼容问题	(面试题)
> IE <= 10 专用 `event.cancelBubble = true`
> 兼容写法 `event.stopPropagation?event.stopPropagation():event.cancelBubble = true;`

> 阻止默认事件: `event.preventDefault?event.preventDefault():event.returnValue = false`



--------------------------

## 事件委托

> 通过监听一个父元素，来给不同的子元素绑定事件，减少监听次数，从而提升速度。
> 由于事件的冒泡机制,可以使用事件委托的方式给元素添加事件,多用于ul监听事件更改li的情景





### closest

 `Element.closest()` 方法用来获取：匹配特定选择器且离当前元素最近的祖先元素（也可以是当前元素本身）。如果匹配不到，则返回 `null`。 换句话说，方法 closest 在元素中检查每个父类。如果与选择器匹配，则停止搜索并返回祖先。IE不支持此方法

语法：`var ele = element.closest(selectors); `

例如：
```html
<article>
  <div id="div-01">Here is div-01
    <div id="div-02">Here is div-02
      <div id="div-03">Here is div-03</div>
    </div>
  </div>
</article>

<script>
  	var el = document.getElementById('div-03');
    
	var r1 = el.closest("#div-02");  
	// 返回 id 为 div-02 的那个元素

    var r2 = el.closest("div div");  
	// 返回最近的拥有 div 祖先元素的 div 祖先元素，这里的话就是 div-03 元素本身

	var r3 = el.closest("article > div");  
	// 返回最近的拥有父元素 article 的 div 祖先元素，这里的话就是 div-01

	var r4 = el.closest(":not(div)"); 
	// 返回最近的非 div 的祖先元素，这里的话就是最外层的 article
</script>
```



### “行为型”模式

我们还可以使用事件委托**声明式**地通过特定属性和类为元素添加“行为”。

模式分为两步：

1. 我们向元素添加一个特殊属性。
2. 用文档范围级的处理器追踪事件，如果事件发生在具有特定属性的元素上 —— 则执行该操作。



```html
add: <input type="button" value="1" data-counter>
add1: <input type="button" value="2" data-counter>

<script>
  document.addEventListener('click', function(event) {

    if (event.target.dataset.counter != undefined) { // if the attribute exists...
      event.target.value++;
    }

  });
</script>
```