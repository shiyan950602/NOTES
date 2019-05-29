# Day 10 Summary

1. 元素对象中的属性设置或获取

   - 元素中本身支持的属性可以通过  对象.属性    对象['属性'] 来设置或获取
   - 不支持的属性（自定义属性）
     - 设置属性：  对象.setAttribute('属性名','属性值')
     - 获取属性：  对象.getAttribute('属性名')
     - 删除属性：  对象.removeAttribute('属性名')

2. outerHTML   innerHTML    innerText的作用和区别

   - outerHTML : 获取当前对象及所有内容
   - innerHTML : 设置或获取当前对象中的超文本（即可以解析标签）
   - innerText : 设置或获取当前对象中的纯文本（即不可以解析标签）

3. 如何获取当前节点对象中的所有子节点

   - childNodes ： 获取当前对象中所有的子节点（包含文本节点与元素节点）

   - ```javascript
     //删除空白文本子节点
     function removeSpace(node){
         var childs = node.childNodes;
     //遍历所有子节点
     for(var i = 0;i <
     childs.length;i ++){
     //遍历是否为文本节点，且该文本是空白
     if(childs[i].nodeType === 3&&/^\s+$/.test(childs[i].nodeValue)){                           
     node.removeChild(childs[i]);
     //删除空白文本子节点
                          }
             }
                   return node;
     }
     ```

   -  children ： 获取当前对象中所有的元素子节点

4. 高级选取

   - firstChild : 获取第一个子节点
   - firstElementChild ： 获取第一个元素子节点
   - lastChild ： 获取最后一个子节点
   - lastElementChild ： 获取最后一个元素子节点
   - previousSibling ： 获取前一个兄弟节点
   - previousElementSibling ： 获取前一个元素兄弟节点
   - nextSibling ：获取后一个兄弟节点
   - nextElementSibling ： 获取后一个元素兄弟节点
   - parentNode ： 获取父节点

5. offsetWidth  offsetHeight

   - offstWidth  获取当前对象的实际宽度（width + border + padding）
   - offsetHeight  获取当前对象的实际高度（height + border + padding）

6. offsetLeft   offsetTop 

   - offsetLeft : 当前对象相对于其父对象的left值
   - offsetTop : 当前对象相对于其父对象的top值
   - clientWidth : 可视宽度
   - clientHeight : 可视高度
   - document.documentElement.clientHeight : 页面的可视高度

7. TCP : 可靠的连接
8. UDP : 不可靠的连接
9. HTTP: 无状态协议
10. Cookie: 存储在用户浏览器端的一段文本信息
11. 编码:encodeURIComponent()
12. 解码:decodeURIComponent()
