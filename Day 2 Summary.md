# Day 2 Summary

1. 实现选择结构的语句有哪些
   - ？：
   - if
   - switch
2. if（单分支选择语句）
   - 格式：if（表达式）{语句组}
   - 逻辑思想： 当程序执行到if时，先计算表达式的值，值为true时，执行后面的语句组。值为false时，跳出if语句，注： 当语句组只有一条语句时，可以省略大括号
3. if else（双分支选择语句）
   - 格式：if（表达式）{语句组}else{语句组}
   - 逻辑思想：当程序执行到if时，先计算表达式的值，值为true时，执行后面的语句组。值为false时，执行else后的语句组
4. if else if （多分支选择语句）
   - 格式：if（表达式）{语句组}else if（表达式）{语句组}else if {语句组}else{语句组}
5. switch(多分支选择语句，开关语句)
   - 格式：switch(表达式){case 表达式：语句组；[break；]case 表达式：语句组；[break；]case 表达式：语句组；[break；][default:语句组 }
   - 逻辑思想：当程序执行到switch时，计算表达式的值，当该值与下面某个case后表达式的值一致时，执行该case后的语句组。如果语句组有break,则直接跳出switch语句。否则继续执行该语句组后所有的语句组，直到遇到break或右大括号时，跳出switch语句
6. 算数运算中保留小数的方法
   - tofixed（2）：保留两位小数  
