# Day 13 Summary

1. bind,apply,call的区别

   - 都是函数对象的方法，只能由函数调用，作用都是用于改变上下文的this指向
   - bind()返回的是函数，不调用不运行，apply()  call()  返回的是对象

2. JSON.parse（）

   - JSON.stringify() : 将json对象转为json字符串
   - 注: IE8以下不兼容

3. let : 用于替代var

   - let声明的变量不再做变量提升

     - ```javascript
       alert(a); //undefined
       var a = 3;
       alert(b); //报错
       let b = 4;
       ```

   - 在同一个作用域中不能利用let重复声明一个变量

     - ```javascript
       var a = 3;
       var a = 4;
       var a = 5;
       alert(a);
       let b = 3;
       let b = 4; //报错
       b = 5;
       alert(b);
       ```

   - let声明的全局变量不再是window对象的属性

     - ```javascript
       var a = 3;
       let b = 3;
       alert(window.a); //3
       alert(window.b); //undefined
       ```

   - let声明变量，会产生块级作用域

     - ```javascript
       //只能在所在块级作用域使用
       {
       	var a = 3;
       	let b = 4;
       }
       
       //for循环包含两个作用域。for本身是一个块级作用域，for的循环体又是for中的一个子级作用域
       
       for(var i = 0;i < 5;i ++){
       	setTimeout(function(){
       	console.log(i);
       		},0);
       }
       
       ```

   - 好处：一改全改

   - 简单数据类型，不可改变值

   - 复合数据类型，不可改变指向

4. const：用于声明常量,一个常量，只能声明一次，声明后，后面不能再对该常量进行重复赋值

   - ```
     const PI = 3.14;
     const G = 9.8;
     console.log(PI + G);
     			
     const ARR = [1,2,3,4];
     ARR[0] = 10;
     console.log(ARR);
     ```

5. 解构赋值

   - 数组的解构赋值    [] = []
   - 对象的解构赋值  {} = {}
   - 好处：交换数据；函数传参：给参数设置默认值   不按顺序传参；返回值   可以返回多个值

6. 字符串扩展方法

   - includes(字符串,start) 判断父串中是否包含子串的内容,返回布尔值
   - startsWith(字符串,start) 判断父串中是否以指定的子串开头,返回布尔值
   - endsWith(字符串,start) 判断父串中是否以指定的子串结尾,返回布尔值
   -  repeat() : 重复指定的字符串,返回串
   - repeat中的参数:大于-1的数,如果是小数,自动取整；如果非数字的值,则自动转为数字,如果无法转数字,则转为NaN,而NaN按0重复；小于等于-1的数,报错

7. Symbol 

   - 是ES6中新增的第七种数据类型,且是基本数据类型
   - 作用：保证变量中的值一定是唯一的

8. set

   -  构造函数 集合(自动去重)

   - 如何创建set对象

     - ```javascript
       var set = new Set();
       var set1 = new Set([value,value]);
       ```

   - 属性：size 返回set对象的长度

   - 方法：add() : 添加元素

     - delete() : 删除指定的元素,返回布尔值
     - has() : 判断set中是否有指定的元素,返回布尔值
     - clear() : 清空整个set对象

   - 遍历set对象

     - ```javascript
       forEach(function(value,key,set){
       
       })	
       
       for(变量  of set){}	
       keys() :获取所有的key
       values() : 获取所有的value
       entries() : 获取所有的key和value
       ```

9. 扩展数组去重

   - ...   : 扩展运算符
   - [...new Set(arr)]

10. for in  和  for  of的区别

    - for in中的循环变量表示  下标(key)
    - for of 中的循环变量表示 元素(value)

11. Map

    - 如何创建map对象

      - ```javascript
        var map = new Map()；
        var map1 = new Map([[key,value],[key,value]])；
        ```

    - 属性: size 返回map对象的长度

    - 方法: set() : 添加元素

      - get() : 获取元素
      - delete() : 删除指定的元素,返回布尔值
      - has() : 判断map中是否有指定的元素,返回布尔值
      - clear() : 清空整个set对象

    - 遍历set对象

      - ```javascript
        forEach(function(value,key,set){
        			
        })
        		
        for(变量  of set){}		
        keys() :获取所有的key
        values() : 获取所有的value
        entries() : 获取所有的key和value
        ```

12. 生成器函数

    - ES6中提出解决异步问题的方案
    - 异步(非阻塞): 同步进行
    - 同步(阻塞): 一步一步进行