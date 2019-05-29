# Day 17 Summary

1. 什么是Cookie

   - 存储在客户端浏览器中的一段文本
   - 好处：提高前后端交互的效率

2. Cookie的特点

   - 一个cookie限制在4KB
   - 一个网站的cookie数量在50条左右
   - 使用cookie存入一定的风险
   - 可以设置有效期,默认的有效期是会话结束时
   - 可以设置路径,一般设置根路径,当前项目中所有的页面皆可访问
   - 可以设置域名
   - 可以设置secure,通过https访问

3. Cookie的缺点

   - 一个cookie限制在4KB
   - 一个网站的cookie数量在50条左右
   - 使用cookie存入一定的风险

4. 创建Cookie的完整格式

   - ```javascript
     document.cookie = 'name=vlaue[;expires=日期对象][;path=/][;domain=域名];[secure;]'
     ```

5. 封装 Cookie

   - ```javascript
     function createCookie(key,value,expires){
     		var cookieText = encodeURIComponent(key) + '=' + encodeURIComponent(value) + ';path=/';
     		if(!isNaN(expires)){
     			var date = new Date();
     			date.setDate(date.getDate() + expires);
     			cookieText += ';expires=' + date;
     		}
     		document.cookie = cookieText;
     	}
     	function getCookie(key){
     		var arr = document.cookie.split('; ');
     		for(var i = 0,len = arr.length;i < len;i ++){
     			var list = arr[i].split('=');
     			if(encodeURIComponent(key) === list[0]){
     				return decodeURIComponent(list[1]);
     			}
     		}
     	}
     	function removeCookie(key){
     		document.cookie = encodeURIComponent(key) + '=;path=/;expires=' + new Date(0);
     }
     ```

6. 购物车
   - 获取购物车按钮---添加点击事件----跳转到购物车页
   - 获取所有的购买按钮 --- 添加点击事件---获取购物车页所需的信息---设计成json字符串
   - 利用本地存储或者cookie进行存储
7. 首先从本地存储中或者cookie中读取到数据(字符串)
8. 筛选出商品,并将json字符串转为json对象
9. 在表格中插入行和单元格-将数据放到单元格中.