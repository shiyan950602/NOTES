# Day 3 Summary

1. 程序控制三大结构
   - 顺序结构 ： 从上到下，依次执行每一条语句，不允许跳过任何语句
   - 选择结构 ： 根据条件判断，是否执行哪一条语句
   - 循环结构 ： 满足一定条件，重复执行一段代码
2. 循环思想（三要素）
   - 从哪里开始（循环初值）即：表达式1
   - 到哪里结束（循环的结束条件） 即：表达式2
   - 步进（步长） （促使循环结束）即：表达式3
3. 实现循环的语句
   - 三目运算符（？：）
   - if （单分支选择语句）
     - 逻辑思想：当程序执行到if时，先计算表达式的值，值为true时，执行后面的语句组，值为false时，执行else后的语句组
   - if else if 语句
     - 当程序执行到if时，先计算表达式的值，值为true时，执行后面的语句组，值为false时，执行else后的语句组，为true时执行下面的if语句组
4. Switch语句
   - 当型循环while
     - 格式 ： 表达式1;while(表达式2){语句组;表达式3;}
       逻辑思想：先计算表达式1，再计算表达式2，如果表达式2的值为true,则执行循环体中的内容（语句组，表达式3），继承判断表达式2的值，值为true，继续执行循环体，否则，退出循环
   - 直到型循环do while
     - 格式：表达式1;do{语句组;表达式3;}while(表达式2);
       逻辑思想，先计算表达式1，执行循环体，再判断表达式2，值为true，继承循环体，值为false,退出循环
   - while与dowhile的区别
     - while是当型循环，先判断条件，后执行语句
     - do while 是直到型循环，先执行语句，后判断条件当第一次条件为假时，while一次都不执行，do while 至少执行一次
   - 多功能循环 for
     - 格式：for(表达式1;表达式2;表达式3){语句组;}
       逻辑思想：先计算表达式1，再计算表达式2，如果表达式2的值为true,则执行循环体中的内容（语句组，表达式3），继承判断表达式2的值，值为true，继续执行循环体，否则，退出循环，表达式1;for(;表达式2;表达式3){}表达式1;for(;表达式2;){语句组;表达式3;}
5. 无线循环（死循环）：条件永远为真
   -  while（1）{ }
   - do { } while（1）
   - for（；1；）
6. Break 和 Continue
   - Break：
     - 用于switch语句中，退出switch语句
     - 用于循环语句中，退出当前（一层）循环
   - Continue：
     - 用于循环语句中，退出一次循环，直接进入下一次循环
7. for in（循环的第四种方法）
   - for（变量 in 数组/对象）{语句组； }
