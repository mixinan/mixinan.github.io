---
title: web第三阶段月考
date: 2019-07-01 20:05
---

JavaScript 阶段的月考题

<!-- more -->

---

　
1、【单选题】查看如下代码：

```
var a = 2;  
var b = 2<<4;  
console.log(b);

上述代码的输出结果是（）。
 
A.8  B.32  C.16  D.0
```
【正确答案】B

　
2、【单选题】现需要使用 jQuery 的方式实现 AJAX 调用：服务器资源为 server.php，使用 post 的方式发送数据“this is a ajax”到服务器端，并将服务器端返回的文本弹出显示。下列选项中，能实现上述需求的是（）。

```
A.
$.ajax({
    url: "server.php",
    type: "post",
    send: "this is ajax",
    success: function (data) {
        alert(data);
    }
});
 
B.
$.ajax({
    open: "server.php",
    type: "post",
    send: "this is ajax",
    success: function (data) {
        alert(data);
    }
});
 
C.
$.ajax({
    url: "server.php",
    type: "post",
    data: "this is ajax",
    success: function (data) {
        alert(data);
    }
});
 
D.
$.ajax({
    open: "server.php",
    type: "post",
    data: "this is ajax",
    success: function (data) {
        alert(data);
    }
});
```

【正确答案】C
　


3、【单选题】查看如下代码：

```
var a = "205.1";
var b = 2;
console.log(b + a);
console.log(isNaN(b + a));

上述代码的输出结果是（）。
 
A. 207.1   和 false 
B. 207.1   和 true 
C. 2205.1  和 false 
D. 2205.1  和 true
```

【正确答案】C

　

4、【单选题】下述HTTP响应状态码与其默认的原因短句的匹配中，错误的是（）。

```
A. 503 - Service Unavailable 
B. 404 - Internal Server Error 
C. 301 - Moved Permanently 
D. 200 - OK
```

【正确答案】B


5、【单选题】查看如下代码：

```
function testFunc(data) {
    data = data + "200";
}
var data = 100;
console.log(data);
testFunc(data);
console.log(data);

上述代码执行后，输出结果为（）。

A. 先输出100，再输出100 
B. 先输出100，再输出100200 
C. 程序错误 
D. 先输出100，再输出300
```

【正确答案】A
　


6、【单选题】有如下HTML代码：

```
<body>
    <form>
        <input id="count" type="number" step="2" min="0" max="20">
        <input type="submit" value="提交">
    </form>
</body>

有如下JavaScript代码：

<script type="text/javascript" language="javascript">
    var quantity = document.getElementById("count");
    quantity.onblur = function(){
        if(quantity.validity.空白处1    ){
            quantity.setCustomValidity("值无效，需要偶数值");
        }else if(quantity.validity.空白处2     ){
            quantity.setCustomValidity("最小值为2");
        }else if(quantity.validity.空白处3     ){
            quantity.setCustomValidity("最大值为20");
        }else if(quantity.validity.customError){
            quantity.setCustomValidity("");
        }
    }
</script>

现需要实现，用户单击“提交”按钮时，校验文本框中的录入，并按照js代码中的文本进行校验提示。
下列选项中，能按顺序分别填入横线空白处的正确代码是（）。
 
A. stepMismatch、 rangeUnderflow 和 rangeOverflow 
B. stepMismatch、 rangeOverflow 和 rangeUnderflow 
C. typeMismatch、 rangeUnderflow 和 rangeOverflow 
D. typeMismatch、 rangeOverflow 和 rangeUnderflow
```

【正确答案】A


7、【单选题】html 页面上有一个 id 为 b1 的按钮，现需要使用 JavaScript 代码为其定义单击事件：单击该按钮后，弹出“js”。下列选项中，错误的是（）。
 
```
A.
document.getElementById("b1").onclick = function() { 
    alert("js"); 
};
 
B. 
document.getElementById("b1").onclick = clickFunc;
function clickFunc() {
     alert("js");
}
 
C.
document.getElementById("b1").onclick = new function(){ 
    alert("js"); 
};
 
D.
document.getElementById("b1").onclick = new Function("alert(js); ");
```

【正确答案】C
　


8、【单选题】
查看如下代码：
```
var num = 10;
if (num > 20)
    console.log(num);
    console.log("num的值小于20");

上述代码执行后，输出结果为（）。
 
A.先输出10，再输出“num的值小于20” 
B.没有输出 
C.输出“num的值小于20” 
D.程序错误
```
【正确答案】C
　


9、【单选题】
查看如下代码：
```
var a = 20;
var b = "2";
var c = (a+1)/b;
document.write(c);

上述代码的输出结果是（）。
 
A. 10 
B. (20+1)/2 
C. 11 
D. 10.5
```
【正确答案】D
　


10、【单选题】
有 html 代码如下：
```
<p id="msg">通知：<span>消息</span></p>

还有 JavaScript 代码如下：

var p = document.getElementById('msg');
console.log( p.nodeValue );
console.log( p.textContent ); 

上述代码的输出结果是（）。
 
A.先输出“通知：”，再输出“通知：消息” 
B.先输出“通知：”，再输出“<span>消息</span>” 
C.先输出null，再输出“消息” 
D.先输出 null，再输出“通知：消息”
```
【正确答案】D
　


11、【单选题】
在处理应答过程中，如果我们要处理XML文档，我们需要在参数列表中放置XMLHttpRequest对象的什么属性（）。
```
A.xhr.requestXML 
B.xhr.requestText 
C.xhr.responseXML 
D.xhr.responseText
```
【正确答案】C
　


12、【单选题】
有 html 代码如下：
```
<body>
    <a>login</a>
    <div id="news">
        <a>新闻标题1</a>
        <a class="current">新闻标题2</a>
        <a>新闻标题3</a>
    </div>
</body>

还有 JavaScript 代码如下：

var div = document.querySelector('#news');
var aNodes = div.querySelectorAll('a');
console.log(aNodes.length);
var node = div.querySelector('a.current');
console.log(node.innerHTML);

上述代码的输出结果是（）。
 
A.先输出 4，再输出 null 
B.先输出 3，再输出 null 
C.先输出 3，再输出“新闻标题2” 
D.先输出 4，再输出“新闻标题2”
```
【正确答案】C
　

13、【单选题】
假设今天是2006年4月1日星期六,请问以下javascript代码输出结果是(   )
```
var time = new Date( );
document.write(time.getDate( ));
 
A.6 
B.2006 
C.4 
D.1
```
【正确答案】D
　


14、【单选题】
Web项目中，服务器页面为了实现国际化，必需客户端浏览器提交下列哪个请求头（）。
```
A.Accept-Language 
B.Content-Type 
C.Content-Language 
D.Accept-Charset
```
【正确答案】A
　


15、【单选题】
查看如下代码：
```
var x = 200;
var y = "100";
var a = x + y + true;
console.log(a);

上述代码执行后，变量 a 的值是（）。

A.200100true 
B.Undefined 
C.301 
D.300true
```
【正确答案】A
　

16、【单选题】
查看如下代码：
```
var datas = [10,20,30];
datas.unshift(40,50);
datas.pop();
datas.push(60,70);
datas.shift();
console.log(datas.toString());

执行后的结果是（）。

A.50,10,20,60,70 
B.40,10,20,60,70 
C.10,20,30 
D.50,10,20,60
```
【正确答案】A
　


17、【单选题】
查看如下代码：
```
var arr = [97, 85, 79, 90];
for (var i = 0; i < arr.length-1; i++) {
    if (arr[i] > arr[i+1]) {
        var temp = arr[i];
        arr[i] = arr[i+1];
        arr[i+1] = temp;
    }
}

console.log(arr);

上述代码执行后，输出结果为（）。
 
A.[97, 85, 79, 90] 
B.[79, 85, 90, 97] 
C.[85, 79, 90, 97] 
D.以上都不对
```
【正确答案】C
　


18、【单选题】
下列关于C/S与B/S应用的描述中，错误的是（）。
```
A. 一般来说，C/S应用的部署实施和维护比B/S应用更加方便，费用更低。 
B. 历史上C/S应用比B/S应用出现的更早；但B/S相较于C/S的优势正在日益凸显。 
C. C/S指Client-Server，这样的应用程序服务器和客户端一般都需要安装一个专用的程序。 
D. B/S指Browser-Server，这样的应用程序服务器需要一款专用的程序，而客户端只需要使用浏览器即可。
```
【正确答案】A
　


19、【单选题】
查看如下代码：
```
var x = "10";
function f1( x ){
    x = x+2;
    return x;
}
console.log(x);
x = f1(x);
console.log(x);

执行后的结果是（）。

A.10 和 102 
B.10 和 10 
C.undefined 和 102 
D.10 和 12
```
【正确答案】A
　


20、【单选题】
有如下JavaScript 和 Html代码：

```
<script>
    function saveData(){
        sessionStorage.setItem('naruto','Uzumaki Naruto');
        sessionStorage.setItem('kakashi','Hatake Kakashi');
    }

    function getAllData(){
        var len=sessionStorage.length;
        for(var i=0;i<len;i++){
            var key=sessionStorage.key(i);
            alert(sessionStorage.getItem(key));
        }
    }

    function clearData(){
        sessionStorage.removeItem('uname');
        sessionStorage.clear();
        alert(sessionStorage.length);
    }
</script>
</head>
<body>
    <input type="button" value="Click" onclick="saveData()" />
    <input type="button" value="Get Data" onclick="getAllData()" />
    <input type="button" value="Clear Data" onclick="clearData()" />
</body>

页面加载完成直接点击Get Data按钮，弹出的结果是（）。

A. 不弹出任何东西 
B. 弹出null 
C. 先弹出 Hatake Kakashi ， 然后弹出 Uzumaki Naruto 
D. 只弹出Hatake Kakashi
```

【正确答案】A
　


21、【单选题】查看如下代码：

```
function f1( ){
	console.log(x);
	var x = 10;
	++x;
	console.log(x);
}

f1();

执行后的结果是（）。
 
A.程序错误 
B.undefined 和 10 
C.10 和 11 
D.undefined 和 11
```

【正确答案】D
　


22、【单选题】
下列JSON格式的数据中，哪些是语法正确的（）。

```
A. '{ename:"Tom", salary:5000}' 
B. '["ename":"Tom", "salary":5000]' 
C. '{"ename":"Tom", "salary":5000}' 
D. '{ename="Tom", salary=5000}'
```

【正确答案】C
　


23、【单选题】查看如下代码：

```
var index = 0;
var arr = [97, 85, 97, 90, 85];

for (var i = 0; i < arr.length; i++) {
    if (arr[i] == 85) {
        index = i;
    }
}

console.log(index);

上述代码执行后，输出结果为（）。

A. 4 
B. 以上都不对 
C. 1 
D. 0
```

【正确答案】A
　


24、【单选题】
查看如下代码：

```
var arr = [ [ 11, 12, 13 ], [ 21 ], [ 31, 32] ];
console.log( arr[1][1] );
console.log( arr[2][1] );

执行后的结果是（）:
 
A. 11 和 21 
B. undefined 和 32 
C. 程序错误 
D. 21 和 31
```

【正确答案】B
　

25、【单选题】查看如下代码：

```
function triangle(num) {
    var result = [[1], [1, 1]];
    for (var i = 2; i < num; i++) {
        result.push([1]);
        for (var j = 1; j < i; j++) {
            result[i][j] = result[i - 1][j - 1] + result[i - 1][j];
        }
        result[i][i] = 1;
    }
    return result;
}

var arr = triangle(5);
console.log(arr[4].toString());

上述代码运行后，输出结果是（）。
 
A. 1,3,3,1 
B. 以上都不对 
C. 1,4,6,4,1 
D. 1,5,10,10,5,1
```

【正确答案】C
　


26、【单选题】查看如下代码：

```
function A() {
    this.name = "a";
    this.introduce = function () { 
        console.log("My name is " + this.name) 
    };
}
    
function B() {
    this.name = "b";
}
    
var a1 = new A();
var b1 = new B();
a1.introduce.call(b1);

上述代码运行后，输出结果为（）。

A. 输出 My name is b 
B. 输出 My name is a 
C. 程序错误 
D. 输出 My name is undefined
```

【正确答案】A

　

27、【单选题】有下述JS代码：

```
var i = 0;
var sum = 0;

do{
    i++;
    if( i%2 === 0){
        continue;
    }
    if( i%5 === 0){
        break;
    }
    sum += i;
}while( i<10 );

console.log( 'sum=' + sum );

其运行结果应该是下列哪项（）。
 
A. sum=0 
B. sum=4 
C. sum=Infinity 
D. 死循环
```

【正确答案】B


28、【单选题】页面上有 id 为 c1 的 `<canvas>` 元素，现需要实现，在 `<canvas>` 元素区域，绘制一个线性渐变的矩形。该矩形为边长100的正方形，最左侧为红色，最右侧为蓝色，颜色从左向右横向线性渐变。有JavaScript 代码如下：

```
var canvas = document.getElementById("c1").getContext("2d");
var grad=canvas.空白处1;
grad.addColorStop(0,'red');
grad.addColorStop(1,'blue');
canvas.fillStyle = grad;
canvas.空白处2;

为实现所需效果，下列选项中，能按顺序分别填入横线空白处的正确代码是（）。

A. createLinearGradient(0,0,0,100)和 strokeRect(0,0,100,100); 
B. createLinearGradient(0,0,100,0)和 fillRect(0,0,100,100); 
C. createLinearGradient(0,0,100,100)和 fillRect(0,0,100,100); 
D. createLinearGradient(0,0,100,100)和 strokeRect(0,0,100,100);
```

【正确答案】B
　


29、【单选题】查看如下代码：

```
function f1( ){
	console.log(x);
	x=x+1;
	var x = 10;
	console.log(x);
}

f1();

上述代码执行后，输出结果为（）。
 
A. 程序错误 
B. 10和11 
C. undefined 和 10 
D. null 和 10
```

【正确答案】C
　


30、【单选题】
下述脚本代码，需要在页面实现了一个数字时钟，空白处脚本依次填写（）。

```
<script type="text/javascript">
    var vID;
    window.onload = function () {
        空白处
    };       
    window.onunload = function () {
        空白处
    };
    function addFunc() {
        var v = new Date();
        document.getElementById("mySpan").innerHTML = v.toLocaleTimeString();
    }
</script>
 
A.
vID = window.setDateTime(addFunc, 1000);
window.clearDateTime(vID);
 
B.
vID = window.setTimer(addFunc, 1000);
window.clearTimer(vID);
 
C.
vID = window.setInterval(addFunc, 1000);
window.clearInterval(vID);
 
D.
vID = window. setTimeout(addFunc, 1000);
window.clearTimeout(vID);
```

【正确答案】C
　


31、【多选题】下列有关JavaScript和PHP的表述中正确的是（）。
```
A. JavaScript和PHP中的数据类型是相同的。
 
B. 一个Web项目中，JavaScript一般用作客户端脚本，控制HTML页面的行为；PHP一般用作服务器端脚本，用于动态的创建网页内容。
 
C. JavaScript和PHP都是弱类型语言，声明变量时都无需指定类型，一个变量也可以先后赋值为不同类型的值。
 
D. JavaScript和PHP中都有“函数”和“对象”概念，都可以使用“面向过程”和“面向对象”的方式编程。
```
【正确答案】B,C,D
　


32、【多选题】下列变量名中，哪些是非法的（）。
```
A. class 
B. $_myVar 
C. 2myVar 
D. myVar2_
```
【正确答案】A,C
　


33、【多选题】假设使用mysqli_query() 函数若执行了一条 SELECT 语句，对于其返回值的下述说法中，错误的有（）。
```
A. mysqli_fetch_array() 函数可以试着向数据库申请结果集中的下一行记录，若不存在更多可读数据了，则返回 NULL；所以若结果集中可能存在多行记录，可以使用形如 while( $row=mysqli_fetch_array($result) ){ }的循环操作读取所有记录行。
 
B. 若 SELECT 语句执行失败，则返回 false。
 
C. 若 SELECT 语句执行成功，则立即返回查询到的所有记录行。
 
D. 返回值中初始是不包含任何记录行的，必须调用 mysqli_fetch_array() 等类似的函数向数据库申请读取查得的记录行；正如函数名所示，调用该函数一次即可以读取到所有的记录行。
```
【正确答案】C,D
　

34、【多选题】
PHP可以如何处理JSON字符串数据（）。
```
A.PHP中可以使用JSON.parse()方法把JSON字符串解析为PHP对象或数组。 
B.PHP中可以使用json_decode()函数把JSON字符串解析为PHP对象或数组。 
C.PHP中可以使用json_encode()函数把PHP数组或对象格式化为JSON字符串。 
D.PHP中可以使用JSON.stringify()方法把PHP数组或对象格式化为JSON字符串。
```
【正确答案】B,C
　


35、【多选题】
现需要创建一个普通按钮，其文本为“new button”，单击该按钮时，弹出文本“Hello”。下列选项中，正确的是（）。
```
A.
var obj = document.createElement("input");
obj.setAttribute("type", "button");
obj.setAttribute("value","new button");
obj.setAttribute("onclick", "alert('Hello');");
 
B.
var obj = document.createElement("input");
obj.setAttribute("type", "button");
obj.innerHTML = "new button";
obj.setAttribute("onclick", "alert('Hello');");
 
C.
var obj = document.createElement("input");
obj.setAttribute("type", "button");
obj.innerHTML = "new button";
obj.onclick = function () { alert("Hello"); };
 
D.
var obj = document.createElement("input");
obj.setAttribute("type", "button");
obj.setAttribute("value","new button");
obj.onclick = function () { alert("Hello"); };
```

【正确答案】A,D
　


36、【多选题】
下列有关HTTPS协议的描述中正确的是（）。
```
A. HTTPS协议是在应用层和传输层之间添加一个消息加密层（SSL或TLS层），负责请求和响应消息的加密和解密。
 
B. 使用HTTPS协议通信的服务器和客户端，在建立连接后，双方必须先初识化消息加密层，交换秘钥，之后才能开始普通消息传递。
 
C. HTTPS协议默认端口为443。
 
D. HTTPS协议在实际应用中，服务器必须向客户端出示可信的数字证书，否则客户端会认为此次连接是不安全的；同时，客户端也必须向服务器出示自己的数字证书。
```
【正确答案】A,B,C
　

37、【多选题】
有 JavaScript 代码如下：

```
function createXmlDoc(xmlFile) {
    var xmlDoc = null;
    if (window.DOMParser) {
        var parser = new DOMParser();
        xmlDoc = parser.parseFromString(xmlFile, "application/xml");
    }
    else {
        xmlDoc = new ActiveXObject("Microsoft.XMLDOM");
        xmlDoc.async = "false";
        xmlDoc.load(xmlFile);
    }
    return xmlDoc;
}

function testFunc() {
    var xmlDoc = createXmlDoc("<bookstore><name age='18'>King</name></bookstore>");
    var value = xmlDoc.getElementsByTagName("name")[0].空白处1;
    var age = xmlDoc.getElementsByTagName("name")[0].空白处2;
    alert(value + ":" + age);
}

现需要读取代码中 XML 数据中的 king 和 18，并弹出显示。
下面选项中，能够按照顺序分别填入横线空白处的代码是（）:
 
A. nodeValue 和 attributes["age"].value 
B. nodeValue 和 attributes[0].value 
C. firstChild.nodeValue 和 attributes["age"].value 
D. childNodes[0].nodeValue 和 attributes[0].value
```

【正确答案】C,D


38、【多选题】
有如下JS代码：
```
var empAge = 20;
var empName;

则下列选项中哪些不会发生执行错误（）。
 
A. if( empAge > 20 && empName.length > 0 ) console.log(); 
B. if( empAge >= 20 || empName.length > 0 ) console.log(); 
C. if( empAge >= 20 && empName.length > 0 ) console.log(); 
D. if( empAge > 20 || empName.length > 0 ) console.log();
```
【正确答案】A,B

　

39、【多选题】
关于SQL和MySQL的说法正确的有哪些（）。
```
A. SQL全称Structured Query Language，是MySQL数据库专用的操作语言，其它RDBMS无法使用。 
B. SQL语句分为四类：DDL、DML、DQL、DCL。 
C. MySQL脚本文件中，可以使用//和/**/两种注释。 
D. MySQL命令行环境中，可以使用source命令执行一个脚本文件中的所有SQL语句。
```
【正确答案】B,D

　

40、【多选题】
下列有关for(;;)循环和for(in)循环的表述中，错误的有（）。
```
A. for(in)循环可以遍历对象中的每个成员; 
B. for(;;)循环可以遍历对象中的每个成员; 
C. for(in)循环可以遍历关联数组（如下标为字符串的数组）中的每个元素; 
D. for(;;)循环可以遍历关联数组（如下标为字符串的数组）中的每个元素;
```
【正确答案】B,D
　

41、【多选题】
有服务器端的 1.php 页面的代码如下所示:

```
<?php
    echo 'aaa({"name":19});';
?>

同时有 html 页面,和 1.php 页面位于不同的域。有 JavaScript 代码如下所示:

function showFunc(data) { 
    alert(data.name); 
}

$.ajax({
    url: "http://localhost:8888/1.php",
    type: "get",
         空白处1     ,
    jsonCallback:     空白处2     
 });

现需要实现跨域调用服务器端的 1.php 页面,使用方法 showFunc 作为回调函数,并弹出显示服务器端的返回结果。
下列选项中,可以按顺序分别填入横线空白处的正确代码是（）。
 
A. data: "jsonp" 和 'showFunc' 
B. dataType: "jsonp" 和 'showFunc' 
C. dataType: "jsonp" 和 showFunc 
D. data: "jsonp" 和 showFunc'
```

【正确答案】B,C
　

42、【多选题】
下列消息头中哪些是请求专用头（即不能用于响应消息）（）。
```
A. Cache-Control  
B. User-Agent   
C. Host   
D. Referer
```
【正确答案】B,C,D
　

43、【多选题】
项目中的数据的保存可以采用哪些方式（）。
```
A. 使用自定义文件，永久保存在应用程序服务器所在的文件系统中; 
B. 使用格式化的文件（如Excel），永久保存在文件系统中;
C. 临时数据，可以保存在内存中; 
D. 使用数据库，永久保存在数据库管理系统中;
```
【正确答案】A,B,C,D
　


44、【多选题】
下列选项中，用于实现文本绘制的属性的是（）。

```
A. font 
B. fontStyle 
C. textAlign 
D. textBaseline
```
【正确答案】A,C,D
　


45、【多选题】
下列哪些选项中的语句可以查找出一个数组中的最大值（）。
 
```
A.
var max = arr[0] ; 
for( var i=0; i<arr.length; i++ ){ 
    max = arr[i] > max ?  arr[i] : max;
}
 
B.
var max = arr[0] ; 
for( var i in arr ){ 
    max = arr[i] > max ?  arr[i] : max;
}
 
C.
var max = arr[0] ; 
var i = 0;
while( i < arr.length ){
max = arr[i] > max ?  arr[i] : max;
    		   i++;
}
 
D.
var max = arr[0] ; 
for( var i in arr ){ 
    max = i > max ? i : max;
}
```

【正确答案】A,B,C
　


46、【多选题】
有变量 obj 表示页面上的某个元素。现需要设置该元素在页面上不可见。  
下列选项中，正确的是（）。

```
A. obj.style.display = "none"; 
B. obj.style.width = 0; 
C. obj.style.opacity = 0; 
D. obj.style.visibility = "hidden";
```

【正确答案】A,C,D
　


47、【多选题】
有代码如下：

```
<html lang="en">
<head>
    <script src="jquery-1.11.1.js"></script>
    <script>
        $(function(){
            $("ul li").each(function(i){
                if(i % 2 == 0){
                    $(this).css("background-color","red");
                }else{
                    $(this).css("border","1px solid blue");
                }
            });
        });
    </script>
</head>

<body>
    <ul>
        <li>Java企业级开发</li>
        <li>Web前端</li>
        <li>Php研发工程师</li>
        <li>网络工程师</li>
        <li>Android开发工程师</li>
    </ul>
</body>
</html>

下列选项中，能实现和上述代码相同效果的是（）。
 
A.
$("li:odd").css("background-color","red");
$("li:even").css("border","1px solid blue");
 
B.
$("li:even").css("background-color","red"); 
$("li:odd").css("border","1px solid blue");
 
C.
$("ul").children().each(function(){
    if($("ul").children().index(this) % 2 == 0){
        $(this).css("background-color","red");
    }else{
        $(this).css("border","1px solid blue");
    }
}
 
D.
$(ul li:odd).css("background-color","red");
$(ul li:even).css("border","1px solid blue");
```

【正确答案】B,C
　


48、【多选题】
关于函数下列说法正确的是（）
```
A. 函数其实是保存代码段的引用类型的对象； 
B. 函数名其实仅是一个普通的变量； 
C. 函数名通过函数对象的地址引用着函数对象； 
D. 函数不能同时被多个对象引用；
```
【正确答案】A,B,C
　


49、【多选题】
下列选项中，属于 `<video>` 元素的事件的是（）。
```
A.error 
B.ended 
C.pauseed
D.play
```

【正确答案】A,B,D
　

50、【多选题】
下列哪些选项中的ECMAScript对象不能实例化（即不能使用new关键字创建新的实例）（）。

```
A. Math 
B. Error 
C. Global 
D. Object
```

【正确答案】A,C