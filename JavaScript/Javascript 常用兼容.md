# Javascript 常用兼容

1. scrollTop (谷歌低版本与其它浏览器)

   - ```javascript
     var scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
     ```

2. scrollLeft(谷歌低版本与其它浏览器)

   - ```javascript
     var scrollLeft = document.documentElement.scrollLeft || document.body.scrollLeft;
     ```

3. getElementsByClassName的兼容（IE9以下）

   - ```javascript
     function byClassName(obj,className){
     	if(obj.getElementsByClassName){
     		return obj.getElementsByClassName(className);
     	}else{
     		var eles = document.getElementsByTagName('*');
     		var arr = [];
     		for(var i = 0,len = eles.length;i < len;i ++){
     			if(eles[i].className === className){
     				arr.push(eles[i]);
     			}
     		}
     		return arr;
     	}
     }
     ```

4. 获取非行内样式的兼容

   - ```javascript
     function getStyle(obj,attr){
     return window.getComputedStyle ? getComputedStyle(obj,true)[attr] : obj.currentStyle[attr];
     }
     ```

5. 获取事件对象的兼容

   - ```javascript
     var e = evt || window.event;
     ```

6. 获取鼠标按键编码值的兼容

   - ```javascript
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

7. 通过onkeypress获取键盘按键编码值的兼容

   - ```javascript
     var code = e.keyCode || e.charCode || e.which;
     ```

8. 阻止事件冒泡的兼容

   - ```javascript
     event.stopPropagation ? event.stopPropagation() : event.cancelBubble = true;
     ```

9.  获取class属性值的兼容

   - ```javascript
     function getClassValue(obj){return obj.getAttribute('class')? obj.getAttribute('class') :obj.getAttribute('className');}
     ```

10. 阻止超链接的默认行为的兼容

    - ```javascript
      e.preventDefault ? e.preventDefault() : e.returnValue = false;
      ```

11. 添加事件监听器的兼容

    - ```javascript
      function addEventListener(obj,event,fn,boo){if(obj.addEventListener){obj.addEventListener(event,fn,boo);}else if(obj.attachEvent){obj.attachEvent('on' + event,fn);}}
      ```

12. 移除事件监听 器的兼容

    - ```javascript
      function removeEventListener(obj,event,fn,boo){if(obj.removeEventListener){obj.removeEventListener(event,fn,boo);}else if(obj.detachEvent){obj.detachEvent('on' + event,fn);}}
      ```

13. 获取事件源的兼容

    - ```javascript
      var target = e.target || e.srcElement;
      ```

      

    