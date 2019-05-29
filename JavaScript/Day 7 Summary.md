# Day 7 Summary

1. 启用严格模式："use strict"

   - 只能加在作用域的开有部分，建议加在函数作用域的开头部分

2. 数组的扩展方法（都不改变原数组）

   - indexOf元素，start）

     - 作用：查找元素在数组中第一次出现时的下标位置，如果没有，则返回-1，返回值：下标

     - ```javascript
       var arr = [1,2,3,4,5,3,2,2,2,3,3,4,4,2,2,3];
       console.log(arr.indexOf(2,2));
       ```

   - lastIndexOf(元素，start）

     - 作用：查找元素在数组最后一次出现时的下标位置，如果没有，则返回-1，返回值：下标

   - foreach（function(value,index,array){});遍历数组

   - map（function(value,index,array){return 数组})映射（遍历数组）

     - ```javascript
       var = [1,2,3,4,5];console.log(arr.map(function(value){return value;}))console.log(arr);
       ```

   - filter(function(value,index,array){ return 新数组}) 过滤数组元素

     - ```javascript
       var arr = [80,28,43,90];
       var list = arr.filter(function(value){return value >= 80;})；
       console.log(list);
       ```

   - reduce(function(prev,next,index,array){return  返回运算后的值;}) 

   - ```javascript
     //归并 
     var arr = [80,28,43,90,99]; 
     var sum = arr.reduce(function(prev,next){return prev + next;});
     console.log(sum); //340     
     ```

3. String

   - 如何创建字符串
     - 字面量的创建方式  ''    ""
     - 构造函数的方式   new String()
   - 属性：length
   - 方法：（查、替、截、转）
     - 查：indexOf('字符串',start) : 查找字符串在指定父串中第一次出现的下标位置。如果没有，则返回-1
     -  lastIndexOf('字符串',start):查找字符串在指定父串中最后一次出现的下标 位置，如果没有，则返回-1
     - charAt(下标) : 通过下标返回指定位置的字符
     -  charCodeAt(下标) : 通过下标返回指定位置字符的编码值
     - 替：replace(旧串，新串) : 替换字符串有指定的字符串。一次只能替换一个
     - 截：substring(start,end) 总是从小的下标截取到大的下标位置（包含小的下标，不包含大的下标）  不支持负数
     - substr(start,length) 截取指定长度的字符串
     - . slice(start,end) 下标可以是负数，总是从左向右截（包含开始，不包含结束）
     - 转：toUpperCase()  小写字母转大写字母
     - toLowerCase()  大写字母转小写字母
     -  split('切割符',length) 字符串转数组
   - 静态方法
     - String.fromCharCode(编码) ：将编码转为字符

