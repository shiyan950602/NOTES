



# Day 9 Summary

1. 什么是BOM

   - 浏览器对象模型

2. BOM中的顶级对象是什么

   - window

3. window下的子对象有哪些

   - document
   - history
   - location
   - frames
   - navigator
   - screen

4. 如何跳转页面

   -  window.location
   - location.href

5. 如何刷新页面

   - location.reload([true])
   - history.go(0)

6. 如何获取浏览器的名称.版本.操作系统信息

   - navigator.userAgent

7. window的方法有哪些

   - alert()  警告框
   - confirm()   确认框
   - prompt()   输入框
   - open() 打开新窗口
   - close()    退出当前页面

8. 计时器

   - setInterval(表达式,毫秒数) 间歇性计时器 clearInterval() : 清除计时器
   - setTimeout(表达式,毫秒数)  一次性计时器(定时器 clearTimeout() : 清除计时器

9. onscroll : 滚动事件

   - 滚动条到顶端的距离

     - ```javascript
       var scrollTop = document.documentElement.scrollTop ||
       document.body.scrollTop;
       ```

   - 滚动条到左边的距离

     - ```javascript
       var scrollLeft = document.documentElement.scrollLeft ||document.body.scrollLeft; 
       ```

10. 什么是DOM

    - 文档对象模型

11. 如何获取页面元素对象

    - document.getElementById('id')
    - document.getElementsByTagName('标签名')
    - document.getElementsByName('name名')
    - document.getElementsByClassName('class名')  兼容: IE9以下不支持
    - document.querySelector('选择器')   兼容:IE8以下不支持
    - document.querySelectorAll(选择器)  兼容:IE8以下不支持
    - document.documentElement     html
    - document.body      body

12. 创建对象

    - 创建元素节点对象: document.createElement(元素名)
    - 创建文本节点对象:document.createTextNode('文本内容')
    - 创建文档碎片 :document.createDocumentFragment()

13. 修改节点对象

    - 父对象.replaceChild(新节点对象,旧节点对象)

14. 删除节点对象

    - 父对象.removeChild(子节点对象)
    - 扩展: 节点对象.remove() : 删除当前节点对象

15. 追加到节点对象中子节点列表的末尾

    - 父对象.appendChild(子节点)

16. 常见节点对象有哪些及它们的nodeName,nodeType,nodeValue值分别是多少

    |            | 元素节点 | 属性节点 | 文本节点 |
    | :--------: | :------: | :------: | :------: |
    | node Name  |  元素名  |  属性名  |   text   |
    | node Type  |    1     |    2     |    3     |
    | node Value |   Null   |  属性值  | 文本内容 |

    