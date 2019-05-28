# Day 8 Summary

1. Math : 数学

   - Math.PI : 圆周率

   - Math.abs() : 绝对值

   - 求近似值

     - Math.round() : 四舍五入

     - 负数大于0.5时进一 小于等于0.5时舍去

     - ```javascript
       console.log(Math.round(4.5));//5
       console.log(Math.round(4.4));//4
       console.log(Math.round(-4.5));//-4
       console.log(Math.round(-4.500001));//-5
       console.log(Math.round(-4.4));//-4
       ```

   - Math.ceil() : 向上取整

     - ```javascript
       console.log(Math.ceil(4.5));//5
       console.log(Math.ceil(4.4));//5
       console.log(Math.ceil(-4.5));//-4
       console.log(Math.ceil(-4.500001));//-4
       console.log(Math.ceil(-4.4));//-4
       ```

   - Math.floor() : 向下取整

     - ```javascript
       console.log(Math.floor(4.5));//4
       console.log(Math.floor(4.4));//4
       console.log(Math.floor(-4.5));//-5
       console.log(Math.floor(-4.500001));//-5
       console.log(Math.floor(-4.4));//-5
       ```

   - 求最值

     -  Math.max() :求最大值

     - 扩展: Math.max.apply(null,数组)

     - ```javascript
       var arr = [4,2,2,1,2,3,1,5];
       console.log(Math.max.apply(null,arr));
       ```

     - Math.min() : 求最小值

     - Math.min.apply(null,数组)

     - ```javascript
       var arr = [4,2,2,1,2,3,1,5];
       console.log(Math.max.apply(null,arr));
       console.log(Math.min.apply(null,arr));
       ```

   - 求随机数

     - Math.random() 取到>= 0 && < 1的数

     - 万能随机公式:Math.floor(Math.random() * (max - min + 1) + min)

     - ```javascript
       function randomInt(min,max){
       if(min > max){
       var t = min;
       min = max;
       max = t;//15   5
       return
       Math.floor(Math.random() * (max - min + 1) + min);//              
       Math.random() * 11   0 ~
       10    5
       }
       console.log(randomInt(5,15))
       ```

     - 求m的n次方：Math.pow(m,n)

     - 求开方：Math.sqrt(n)

2. 日期对象

   - 如何创建日期对象:new Date()
   - 如何获取日期时间:
     - 年: date.getFullYear()
     - 月: date.getMonth()
     - 星期: date.getDay()
     - 小时: date.getHours()
     - 分钟: date.getMinutes()
     - 秒钟: date.getSeconds()
     - 毫秒:date.getMilliseconds()
     - 时间戳:date.getTime()
     - 日: date.getDate()
   - 以本地字符串的格式 显示日期/时间/日期时间
     - date.toLocaleDateString()
     - date.toLocaleTimeString()
     - date.toLocaleString()
   - 扩展:如何设置日期时间
     - 年: setFullYear()
     - 月: setMonth()
     - 日: setDate()
     - 时: setHours()
     - 分: setMinutes()
     - 秒: setSeconds()
     - 毫秒:setMilliseconds()
     - 时间戳: setTime()