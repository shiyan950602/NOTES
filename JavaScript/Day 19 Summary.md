# Day 19 Summary

1. JavaScript 解析 Json

   - Eval()方法：解析 JSON 数据的最常用方法是使用 javascript 的 eval()方法，代码如下

   - ```javascript
     function toJson(str){
     var json = eval(‘(‘ + str + ‘)’);
     return json;
     }
     ```

   - 该方法存在性能和安全方面的问题，不建议使用

   - JSON.parse()方法

   - 这种方法只支持IE8/Firefox3.5+/Chrome4/Safari4/Opera10 以上版本，这些浏览器都已经接近 W3C 标准，默认实现了 toJSON 方法。代码如下

   - ```javascript
     function toJson(str){
     return JSON.parse(str);
     }
     ```

   - New Function 方法,代码如下

   - ```javascript
     function toJson(str){
     var json = (new Function(“return” + str))();
     return json;
     }
     ```

2. 局部数据刷新

   - 请求并显示静态 TXT 文件
   - 字符集编码（三个按钮分别读取三个不同的文件并存入 div 中）
   - 缓存、阻止缓存（?t=newDate().getTime()）
   - 动态数据：请求 json 文件
   - 分页

