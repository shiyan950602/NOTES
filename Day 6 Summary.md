# Day 6 Summary

1. ==什么是数组==

   储存一组或一系列相关数据的容器

2. ==使用数组的好处==

   可以集中管理，提高性能

3. ==什么是数组下标==

   标识数组元素的唯一索引号

   最小下标为 0 最大下标为 Length - 1

4. ==什么是数组元素==

   存放数组中的数据

5. ==如何声明数组==

   字面量的方式： var 数组名 = [] 

   构造函数的方式： var 数组名 = new Arry （）；

   > 构造函数方式创建数组，如果有且仅有一个正整数作为参数时，表示数组的长度，负数或小数时，报错，其他的情况表示数组中的元素 

6. ==数组的属性==

   Length返回数组的长度

7. ==数组的数据类型==

   Object

8. ==如何给数组赋值==

   初始化数组

   先声明后赋值

9. ==遍历数组的方法==

   - 前增  **unshift**
     - 作用：在数组的首部增加新的元素
     - 返回值：新增后数组的长度                          
     - 是否影响原数组：是

   - 后增  **push**
     - 作用：在数组的尾部增加新的元素                   
     - 返回值：新增后数组的长度                    
     - 是否影响原数组：是

   - 前删  **shift**
     - 作用：删除数组首部的元素，一次只能删除一个元素                   
     - 返回值：返回被删除的元素                
     - 是否影响原数组：是

   - 后删  **pop**
     - 作用：删除数组首部的元素，一次只能删除一个元素                 
     - 返回值：返回被删除的元素                     
     - 是否影响原数组：是

   - 改  **splice**（从哪个下标开始，删除的长度，新增的元素）
     - 作用：在数组的任意位置可以实现增、删、改             
     - 返回值：被删除的元素数组              
     - 是否影响原数组：是

   - 截 **slice**（start，end）
     - 作用：截取指定范围的数组元素              
     - 返回值：被截取到的新数组              
     - 是否影响原数组：否

   - 拼  **concat** （拼接的元素）

     - 作用：将新的元素拼接到指定的数组后面，形成新的数组（注：新数组中有数组，则将最外层数组拆开进行拼接）              
     - 返回值：拼接后的新数组              
     - 是否影响原数组：否

   - ==复 复制一个数组的方法==

     - ```javascript
       var arr =[5,6,7,8,9];
       var list = [];
       function fnCopyArr(arr){
       	return arr.slice(0);
       }
       
       list = fnCopyArr(arr);
       	arr[0] = 4;
       console.log(arr,list);
       ```

     - ```javascript
       var arr = [5,6,7,8,9];
       var list = [];
       function fnCopyArr1(arr){
           return arr.concat();
       }
       
       list = fnCopyArr1(arr);
            arr[0] = 4;
       console.log(arr,list);
       ```

     - ```javascript
       var arr = [5,6,7,8,9];
       var list = [];
       function fnCopyArr2(arr){
       	var list = [];
       	for(var i = 0,len = arr.length;i < len;i ++){
             	list[i] = arr[i];
       	}
       	return list;
       }
       list = fnCopyArr2(arr);
           arr[0] = 4;
       console.log(arr,list);
       ```

     - ```javascript
       var arr = [5,6,7,8,9];
       var list = [];
       function fnCopyArr3(arr){
             var list = [];
       for(var i = 0,len = arr.length;i < len;i ++){
                list.push(arr[i]);
        		} 
           return list;
       }
       list = fnCopyArr3(arr);
           arr[0] = 4;
       console.log(arr,list);
       ```

   - 排  **reverse**

     - 作用：将数组元素逆序             
     - 返回值：逆序后的数组              
     - 是否影响原数组：是

   - 扩展  **sort** 

     - 作用：将数组元素按字符串的编码进行从小到大的排列            
     - 返回值：排序后的数组            
     - 是否影响原数组：是

   - 转  **toString**

     - 将数组转为字符串	                                          
     - 返回值：返回转后的字符串（以逗号分隔）                                          
     - 是否影响原数组：否

   - 连接符  **join**

     - 作用：将数组转为以指定连接符连接的字符串。            
     - 返回值：返回转后的字符串            
     - 是否影响原数组：否

10. ==for in==

    作用：只能遍历数组或对象

    格式：for（变量 in 数组/对象）{语句组}

11. ==排序算法==

    冒泡排序：相邻

    选择排序：取一个数与剩下所有的数

12. ==堆栈（值传递和引用传递）==

    基本数据类型值属于值传递

    复合数据类型属于引用传递

13. ==Json:用于网络数据传递的一种数据格式     undefined NaN function(){}==

    [] 如果有字符串，必须是

    {}

    原生：{name：'张三'}

    Json：{"name":"张三"}

