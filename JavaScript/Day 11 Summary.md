# Day 11 Summary

1. 什么是事件对象

   - (类似于飞机上的黑匣子)将绑定事件的对象在触发事件时,所发生的一切详细信息记录在一个地方,这个地方称为事件对象

2. 如何获取事件对象

   - 标准浏览器 :

     - 给事件处理程序传递的第一个参数

   - IE :

     - 内置的对象 window.event

   - 兼容：

     - ```javascript
       var e = evt || window.event;
       ```

3. 如何获取鼠标按键的编码值

   - 标准浏览器 : 左    0    中    1   右    2

   - IE :  左1   中 4    右 2

   - ```javascript
     兼容:
     function getButton(evt){
     		var e = evt || window.event;
     		if(evt){
     			return e.button;
     		}else if(window.event){
     			switch(e.button){
     				case 1 : return 0;
     				case 4 : return 1;
     				case 2 : return 2;
     		}
     	}
     }
     ```

4. 如何获取鼠标的坐标值

   -  相对坐标值: event.offsetX     event.offsetY 
     - 鼠标当前位置相对于所在对象的边的距离
   - 绝对坐标值:(页面坐标值) 
     - event.pageX    event.pageY
     - 鼠标当前位置到页面边的距离(相当于:鼠标当前位置到页面可视区的坐标值 + 滚动条到顶端的距离)
   - 可视区坐标值: event.clientX    event.clientY
     - 鼠标当前位置到页面可视区的边的距离

5. 通过键盘事件,获取键盘按键的编码值

   - (keyCode/charCode/which)
     - onkeydown/onkeyup    event.keyCode
     - 火狐: event.keyCode    event.which 
     - IE: event.keyCode 只能获取字母按键大写字母的编码值,不区分大小写且onkeydown和onkeyup监听整个键盘
     - onkeypress
     - 火狐: event.keyCode   event.charCode  event.which
     - 谷歌: event.keyCode   event.charCode  event.which 只监听操作键,不包含控制键和功能键,可能获取字母的大小写编码

6. 什么是事件冒泡

   - 事件流: 事件传递的流程

   - 事件流中包含三个阶段:事件捕获阶段/事件目标阶段/事件冒泡阶段

   - 事件冒泡: 事件由内向外,由子元素向祖先元素依次传递事件的过程叫事件冒泡.

   - 事件捕获: 事件由外向内,由祖先元素向子孙元素依次传递事件的过程叫事件捕获

   - 如何阻止事件冒泡

     - ```javascript
       //标准浏览器
       event.stopPropagation()
       ```

     - ```javascript
       //IE浏览器
       event.cancelBubble = true
       ```

     - ```javascript
       //兼容
       event.stopPropagation ? event.stopPropagation() : event.cancelBubble = true;
       ```

7. 扩展：鼠标事件 + event.which 

8. 获取到鼠标按键编码值,左:1  中:2  右:3

