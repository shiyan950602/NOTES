# Day 12 Summary

1. 什么正则表达式

   - 匹配字符串的一组规则

2. 作用：常用于表达式验证

3. 如何创建正则表达式

   - 字面量的方式: /正则表达式/ 标志位
   - 构造函数的方式: new RegExp('正则表达式','标志位')

4. 正则表达式的方法

   - 正则表达式对象.test(字符串) : 判断字符串中是否包含正则的内容,如果包含,返回true,否则,返回false
   - 正则表达式对象.exec(字符串) : 返回伪数组,如果没有匹配到正则表达式,返回null

5. 检测正则表达式的字符串方法

   - 字符串对象.match(正则表达式) : 返回伪数组,如果没有匹配到正则表达式,返回null

   - 字符串对象.replace(正则表达式,新串) : 替换字符串

     - ```javascript
       var str = 'how do you do';
       var re = /do/;
       console.log(str.replace(re,'de'));
       ```

   - 字符串对象.search(正则表达式) : 查找正则匹配到在字符串在父串中第一次出现的下标 位置. 没有匹配到,返回-1

     - ```javascript
       var str = 'how do you do';
       var re = /do/;
       console.log(str.search(re));
       ```

   - 标志位

     - g：全区匹配
     - i：不区分大小写

6. exec与match的区别

   - 无组无标志位g

     - ```javascript
       var re = /o/;
       var str = 'how do you do';
       console.log(re.exec(str)); //['o']
       console.log(str.match(re)); //['o']
       ```

   - 无组有标志位g

     - ```javascript
       var re = /o/g;
       var str = 'how do you do';
       console.log(re.exec(str)); //['o']
       console.log(str.match(re)); //[ "o", "o", "o", "o"]
       ```

   - 有组无标志位g

     - ```javascript
       var re = /([a-z]+),(\d+)/i;
       var str = 'abc,123';
       console.log(re.exec(str)); //[ "abc,123", "abc", "123" ]
       console.log(str.match(re)); //[ "abc,123", "abc", "123" ]
       ```

   - 有组有标志位g

     - ```javascript
       var re = /([a-z]+),(\d+)/ig;
       var str = 'abc,123';
       console.log(re.exec(str)); //[ "abc,123", "abc", "123" ]
       console.log(str.match(re)); //[ "abc,123" ]
       ```

7. 元字符

   - ｛｝[ ] （）
     - ｛｝：表示｛｝前面的一个或一组字符连续出现的次数
     - ｛m｝：表示｛｝前面的一个或一组字符连续出现m次
     - ｛m,｝：表示｛｝前面的一个或一组字符连续出现至少m次
     - ｛m,n｝：表示｛｝前面的一个或一组字符连续出现m至n次
     -   '' [ ] ''  表示范围
     -   '' ( ) ''   表示组
   - '*' '+' '?'
     - '*' 表示星号前面的一个或一组字符连续出现 0 ~ 无限次   相当于{0,}
     - '+' 表示加号前面的一个或一组字符连续出现 1 ~ 无限次  相当于{1,}
     - '?'表示问号前面的一个或一组字符连续出现 0 ~ 1次  相当于{0,1}
   - ^ $
     - ^ : 写在正则表达式的开头 ,表示限制字符串必须是指定的字符开头
     - ^ : 写在[]中的开头,表示取反
     - $ : 表示限制字符串必须是指定的字符结尾
   - . | \
     - . : 表示模糊匹配任意一个字符
     - | : 表示或
     - \ : 转义符
     - \d : 表示数字
     - \D : 表示非数字 
     - \s : 表示空白符
     - \S : 表示非空白符
     - \w : 表示字母数字下划线
     - \W : 表示非字母数字下划线
     - \b : 表示边界(单词边界)

