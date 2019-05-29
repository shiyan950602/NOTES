# Day 14 Summary

1. SessionStorage（会话储存）

   - 大小4K
   - 在重启浏览器、关闭页面或新开页面时失效
   - 储存内容：数组、json、图片、脚本、样式等可以序列化为字符串的内容
     - 使用方法
     - setItem(key,value)：添加本地存储数据 
     - getItem(key):通过key获取相应的Value
     - removeItem(key):通过key删除本地数据
     - clear():清空数据

2. localStorage（本地储存）

   - 大小在5M左右，不同浏览器大小有所差别

   - 永久存储，不过期，除非手动删除

   - 储存内容：数组、json、图片、脚本、样式等可以序列化为字符串的内容

     - 使用方法
     - setItem(key,value)：添加本地存储数据 
     - getItem(key):通过key获取相应的Value
     - removeItem(key):通过key删除本地数据
     - clear():清空数据

   - 如何创建localStorage

     - ```javascript
       var storage = window.localStorage;
       
       //写入数据
       
       storage.key = value
       storage['key'] = value
       storage.setItem('key','value')
       
       //读取数据
       
       storage.key
       storage['key']
       storage.getItem('key')
       
       //删除指定的key
       
       storage.removeItem('key')
       
       //清空storage
       
       storage.clear()
       	
       //获取所有的key
       
       for(var i = 0,len = storage.length;i < len;i ++){
       		console.log(storage.key(i));
       }
       ```

   - 购物车

     - ```javascript
       window.onload = function(){
       
       //1. 获取页面元素对象
       
       //获取查看购物车按钮
           
       let cartBtn = document.getElementsByTagName('button')[0];
       
       //获取所有的按钮按钮
       
       let buyBtns = document.querySelectorAll('table .buy');
       
       //2. 添加事件
       
       cartBtn.onclick = function(){
       
       window.location = 'cart.html';
       
       }
           
       //遍历添加事件
       
       for(let i = 0,len = buyBtns.length;i < len;i ++){
       			buyBtns[i].count = 0;
       			buyBtns[i].onclick = function(){
       
       //获取商品ID
                       
       let goodId =
       this.parentNode.parentNode.firstElementChild.firstElementChild.value;
                       
       //获取商品名称
                       
       let goodName = this.parentNode.parentNode.firstElementChild.lastChild.nodeValue;
                       
       //获取商品价格
                       
       let goodPrice = this.parentNode.previousElementSibling.innerHTML;
                       
       //获取商品数量
                       
       let goodNum = ++ this.count;
                       
       //添加到本地存储
                       
       if(!window.localStorage){
       alert('浏览器不支持!');
       }else{
       let storage = window.localStorage;
       storage['product_' + goodId] = 
       '{"id" : ' + goodId + ',"name" : "' + goodName + '","price" :
       ' + goodPrice + ',"num" : ' + goodNum + '}';
       			}
       		}
       	}
       }
       ```

       
