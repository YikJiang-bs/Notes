## PHP开发环境配置

###   一、开发环境

1、XAMPP或LNMP、WNMP，先安装widows版本的XMAPP-5.6版本（PHP 5.6）

2、VSCode：微软开发的集成开发环境（IDE）

### 二、安装教程

#### 1、安装步骤

https://url.cy/YC70L3

#### 2、部署文件主目录

```
xampp/htdocs/learn 为文件的主目录，在此创建的文件都可在http://localhost:8081/learn/下看到
```

#### 3、测试安装是否成功

- 编写HTML代码

  ```html
  <font color="red">Yang</font>
  ```

  ![image-20220501175109211](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241535153.png)

- 编写PHP代码

  ```php
  <?php
  
  echo "煎蛋杨粑粑";
  
  ?>
  ```

  <img src="https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241535154.png" alt="image-20220501175051335" style="zoom:80%;" />

## Web前端页面基本元素

### 一、HTML页面的构成要素

####  1、HTML（标记语言）

- 文本：字体、颜色、大小
- 图片：边框、大小、位置
- 超链接：图片、文本等均可以添加超链接
- 表格：用于展示行列构成的结构化数据，可以用表格展示，大小、背景，表格里可以放所有元素
- 表单
  - 文本框
  - 下拉框
  - 单选框/复选框
  - 按钮
  - 文本域
  - ………………

#### 2、CSS

- 层叠样式表，用于对页面元素进行布局和美化

#### 3、JavaScript

- 在浏览器中运行的解释型编程语言，用于进行页面的交互
  - 前后端交互
  - 用户之间的交互

### 二、HTML的基本元素的使用

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>这是一个Demo页面！</title>
</head>
<body>
    <!-- 常规情况，标记都是成对出现的 -->
    <!-- 在HTML中，文本内容不再建议使用 font 标签 -->
    <!-- 通常，文本、图片等元素都会放在容器中 -->
    <!-- </br> 强制换行 -->
    <font color = "#99CC33">Hello World!</font></br>
    <font color = "#0099CC" size = '5'>Yang~</font>

    <!-- div里可以放任意元素，默认换行 -->
    <!-- 使用DIV来包裹一段文本，并设置字体大小和颜色 -->
    <!-- 被style属性指定或包裹的，是css样式 -->
    <div style="color: aqua;font-size: 30px;">Hello World!</div>
    <div style="font-family: 幼圆;font-size: 20px; color: cadetblue;">Hello World!</div>

    <!-- 图片 -->
    <img  src="image/可爱女孩马尾辫 绿色眼睛 脸 好看4k动漫人物壁纸_彼岸图网.jpg" width="500px"></br>

    <!-- 超链接 -->
    <!-- 使用target='_blank可以打开新的标签页 -->
    <a href="http://www.baidu.com"  target='_blank'>Go!</a></br>

    <!-- 表格 -->
    <!-- 有行和列构成，主要使用三个标签
        <table> 定义表格整体属性
        <tr>  定义一行
        <td>  指定一列
    -->
    <table width="500" height= "300" border="1" >
        <tr>
            <td width='50%' bgcolor="#008080">Name</td>
            <td width='30%'>Snumber</td>
            <td width='20%'>Phone</td>
        </tr>
        <tr>
            <td>杨宇波</td>
            <td>2150511032</td>
            <td>18222362661</td>
        </tr>
        <tr>
            <td>4</td>
            <td>5</td>
            <td>6</td>
        </tr>
    </table>

    <!-- 表单 -->
    <input type="text" value="Hello"/></br>
    <input type="text" placeholder="请输入账户名"></br>
    <input type="password" placeholder="请输入密码"/>
    <input type="button" value="提交">
    <!-- 直接的button标签也可以使用 -->
    <button>登录</button>
    <select>
        <option>Lebron</option>
        <option>Curry</option>
        <!-- selected 默认显示的选项 -->
        <option selected>Young</option>
    </select>

</body>
</html>
```

### 三、设计计算器

#### 1、代码

- border-radius

  <img src="https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241535155.png" alt="image-20220501230613264" style="zoom:50%;" />

#### 2、实例

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">     <!--设置字符集-->  
    <meta http-equiv="X-UA-Compatialbe" content="IE=dege">      <!--配置IE和Edge的兼容性-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">      <!--设置在手机上显示的效果-->
    <title>计算器</title>

    <!-- 定义样式表 -->
    <style>
        /* 类选择器 ，以 . 开头+类名*/
        .button{
            background-color:#928a97 ;    /*设置背景色*/
            margin: auto;           /* 设置容器水平居中*/ 
            border-radius:8px ;
        }

        /* 层次选择器,选择 button 类下面的所有标签为td的元素 */
        .button tr td{
            background-color:#99CCFF;
            border-radius: 10px;
            width: 25%;
            text-align: center;
            font-size: 30px;
            color: rgba(255, 255, 255);
        }

        .point-red{
            width: 20px;
            height: 20px;
            background-color: rgb(238, 91, 84);
            float: left;      /*  靠左浮动，不独自占用一行 */
            margin-left: 10px;      /* 左边间隔10px */
            border-radius: 50%;        /* 边框的半径 */
        }   
        .point-yellow{
            width: 20px;
            height: 20px;
            background-color:rgb(248, 189, 50);
            float: left;
            margin-left: 10px;
            border-radius: 50%;
        }
        .point-green{
            width: 20px;
            height: 20px;
            background-color:rgb(97, 202, 66);
            float: left;
            margin-left: 10px;
            border-radius: 50%;
        }
        .title{
            color:white;        /*文字颜色*/
            font-size: 20px;
            float: right;
            margin-right:10px;
        }
        .xianshiqi{
            border-radius:10px ;
        }

    </style>
    

</head>
<body>
    <!-- border常设置三个属性：
        solid：实线
        dashed: 虚线
        大小
        颜色
    -->
    <!-- 
    bgcolor:背景颜色
    cellspacing: 单元格之间的间隔
    align='center'  居中显示
     -->
    <table width='450' height='120' border="0" bgcolor=#928a97 cellspacing='4' align="center" class="xianshiqi">
        <!-- 两行一列 -->
        <tr bgcolor='#FBE8D3' ">
            <td bgcolor="#FBE8D3" height='40'>

                <!-- 设计小圆点 -->

                <div class="point-red"></div>
                <div class="point-yellow"></div>
                <div class="point-green"></div>
                <div class="title">YikJiang</div>
            
            </td>
        </tr>
        <tr bgcolor='white'">
            <td bgcolor="white" style="border: solid 2px #6699CC;"</td>
        </tr>
    </table>

    <!-- 五行四列，绘制计算机按钮 -->
    <!-- shift + alt + ↓ 复制代码到下一行 -->
    <!-- class :定义类 -->
    <table width='450' height ='400' border="0"  cellspacing='4'   class="button">
        <tr>
            <td>AC</td>
            <td>+/-</td>
            <td>%</td>
            <td>÷</td>

        </tr>
        <tr>
            <td>7</td>
            <td>8</td> 
            <td>9</td>
            <td>*</td>
        </tr>
        <tr>
            <td>4</td>
            <td>5</td>
            <td>6</td>
            <td>-</td>
        </tr>
        <tr>
            <td>1</td>
            <td>2</td>
            <td>3</td>
            <td>+</td>
        </tr>
        <tr>
            <td>0</td>
            <td>删除</td>
            <td >.</td>
            <td>=</td>
        </tr>
    </table>
    
</body>
</html>
```

## 使用DIV+CSS重构计算器

### 一、CSS的使用方式

- 要为HTML元素设定样式，有以下三种方式来使用CSS：

##### 1、在元素中指定style属性

```css
<td style="border: solid 2px #6699CC;"</td>
```

> 也称为内嵌样式，只针对对应的这个标签生效

##### 2、在页面中嵌入style样式块

```css
<style>
td{
    background-color:#6699CC
    width:25%
    text-align:center
}
</style>
```

> 通常建议将style标签放置于head标签中，可以针对当前页面的所有元素生效

##### 3、在页面中引入外部CSS文件

```css
<link rel="stylesheet" type="text/css" href="/page/css/bootstrap.css"/>
```

> 外部CSS文件，可以针对全站的引入这个CSS的多个页面生效，放置于head中

### 二、CSS选择器

选择器是指CSS如何与元素及样式建立关联关系的一种手段。

##### 1、标签选择器

使用类型选择器，可以向这种元素类型的每个实例上应用的声明

```css
/* 为当前页面中所有的单元格设计统计的样式 */
td{
    background-color:#99CCFF;
    border-radius: 10px;
    width: 25%;
    text-align: center;
    font-size: 30px;
    color: rgba(255, 255, 255);
}
```

##### 2、类选择器

通过设置元素的class属性定位元素，在同一个页面中，多个元素可以归为同一个类

```css
/*类选择器，以.开头，对元素中指定 class="title" 的元素设计样式*/
.button{
    background-color:#928a97 ;    /*设置背景色*/
    margin: auto;           /* 设置容器水平居中*/ 
    border-radius:8px ;
}
```

##### 3、ID选择器

HTML页面的任何一个元素，即任何一个标签，都拥有ID这个属性，我们可以通过为元素设置一个唯一的ID标识符，进而利用CSS的ID选择器对其使用样式。

```css
/*ID选择器，以#开头，对元素中指定 id='title' 的元素设计样式 */
#title{
    color:white;
    font-size:22px;
    float:right;
    margin-right:10px;
}
```

##### 4、组合选择器

可以将标签选择器、ID选择器、类选择器和属性选择器等，组合成不同的选择器类型来构成更复杂的选择器，可以更加精确的处理希望赋予某种表示的元素，我们也可以通过指定父子关系来对元素进行选择

```css
/* 组合使用ID和标签选择器，并实现了层次关系*/
#button tr td{
    background-color:#99CCFF;
    border-radius: 10px;
    width: 25%;
    text-align: center;
    font-size: 30px;
    color: rgba(255, 255, 255);
}
```

##### 5、属性选择器

```css
/*为DIV元素下拥有 type="button" 属性的元素设计样式*/
div [type="button"]{
    clolor:white;
    font-size:22px;
}
```

##### 6、伪类选择器

设计伪类和伪元素可以实现其中的一些效果，使用伪类可以根据一些情况改变文档中链接的样式，如根据链接是否被访问，何时被访问以及用户和文档的交互方式来应用改变。借助于伪元素，可以更改元素的第一个字母和第一行的样式，或者添加源文档中没有出现过的元素

```css
/*使用 hover 伪类设置鼠标滑过时的变换效果 */
#button td:hover{
    background-color:red;	
}
```

### 三、DIV盒模型

##### 1、内容（content）就是盒子里装的东西，可多可少，可以是任意类型

##### 2、填充（padding）就是怕盒子里装的东西损坏而添加的泡沫或者其他抗震的材料

##### 3、边框（border）就是盒子本身

##### 4、边界（margin）则说明盒子摆放的时候不能全部堆放在一起

<img src="https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241535156.png" alt="image-20220502111018968" style="zoom:50%;" />

### 四、DIV实例

```html
<!-- 盒模型及CSS基础样式 -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /* 标签选择器 */
        .inner{
            width: 450px;
            /* height: 300px; */
            border: solid 2px #0099FF;
            /* border也是自动设置4条边框 */

            /* background:#0099FF; */
            /* margin: auto; */
            /*
            margin: auto 包括
                margin-top: auto;
                margin-bottom: auto;
                margin-left: auto;
                margin-right: auto; */

            margin-top: 100px;
            /* margin-right: 300px; */

            /* 会扩大容器总高度 
            文字默认情况下为16px
            */
            /* padding-top: 50px;       */
            
            /* 设置当前这一行的文本高度为300px2 ,实现单行的垂直居中*/
            /* line-height: 300px; */
            
            /* 设计水平居中 */
            text-align:center;

            /* 通过设置 padding-top和padding-bottom实现垂直居中 
            padding 后两个值：上下 左右
            padding 后四个值：上 右 下 左  (顺时针)
            
            
            */
            padding: 150px 0px;   
            float: left;


            /* 设置文本样式 */
            font-size: 16px;
            color: #003366;
            /* 
            设置字体 
                设置多个字体时，会逐一匹配
                font-style: italic  :设置为斜体
                font-weight: bold   :文本加粗
                text-decoration: underline  :设置下划线
            */
            font-family: 楷体,宋体,黑体;
            font-style: italic;
            font-weight: bold;
            text-decoration: underline;
    
        
        }

        /* ID选择器 */
        #outer{
            width: 908px; 
            height:445px;
            margin: auto;
            border: solid 0px #0099FF;
;
            
        }

        
    </style>
</head>
<body>
    <!-- 当存在两个DIV的情况，要想实现两个DIV全部居中，可以在创建一个父DIV，包裹两个DIV -->
    <div id="outer">
        <div class="inner"> Hello<br/>YikJiang</div>
        <div class="inner">青史如镜，鉴照峥嵘岁月；<br/>初心如炬，辉映复兴之路。</div>
    </div>

    
</body>
</html>
```

### 五、重构计算器

#### 1、分析页面结构

<img src="https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241535157.png" alt="image-20220502160440049" style="zoom:67%;" />

#### 2、布局实现

- **顶部DIV**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Div版计算器</title>
    <style>
        #top{
            width: 450px;
            height: 50px;
            margin: auto;
            background-color: #FBE8D3;
            border-radius:10px;
        }

        #top .point{
            width: 20px;
            height: 20px;
            float: left;
            margin-left: 10px;
            margin-top: 15px;
            border-radius: 50%;
        }
        #top .red{
            background-color: rgb(238, 91, 84);
        }
        #top .yellow{
            background-color: rgb(248, 189, 50);
        }
        #top .green{
            background-color: rgb(97, 202, 66);
        }
        #top .calc-title{
            font-size: 22px;
            color: rgb(255, 255, 255);
            float: right;
            margin-right: 8px;
            margin-top: 10px;
        }



    </style>
</head>
<body>
    <div id="top">
        <!-- class="point red" : 表示归属于两个类 -->
        <div class="point red"></div>
        <div class="point yellow"></div>
        <div class="point green"></div>
        <div class="calc-title">YikJiang</div>
    </div>
    
</body>
</html>
```

- **屏幕显示**

```css
#result{
    width: 444px;
    height: 50px;
    margin: auto;
    background-color: white;
    border-radius:10px;
    border:solid 2px #6699CC;
}

<div id="result"></div>
```

## JavaScript

### 一、DOM操作

JavaScript直接操作页面的元素的方法集合，称为DOM，是一套JS代码的接口，还有一套BOM，用于通过JS直接操作浏览，比如前进、后退、历史、导航等~

### 二、JS定位元素

#### 1、JS代码的执行顺序

```html
    <!-- 下面时JS的代码 -->
    <script type="text/javascript">
        // 获取一个元素(定位、选择)
        //document表示当前文件  .innerHTML表示找这个元素夹着的内容,JS中定义变量通常在前面添加var
        var calTitle = document.getElementById("calc-title").innerHTML;
        // 弹窗输入变量名
        window.alert(calTitle);

    </script>
</head>
<body>

    <div class="outer">
        <div id="top">
            <!-- class="point red" : 表示归属于两个类 -->
            <div class="point red"></div>
            <div class="point yellow"></div>
            <div class="point green"></div>
            <div class="calc-title">YikJiang</div>
        </div>
```

> 上述代码无法正常弹出提示框 YikJiang ,JS代码会先于元素加载而执行,此时页面当中无此元素"calc-title"

**解决方案**

- 将JS代码放置于元素渲染之后

  ```html
  <div id="top">
      <!-- class="point red" : 表示归属于两个类 -->
      <div class="point red"></div>
      <div class="point yellow"></div>
      <div class="point green"></div>
      <div class="calc-title">YikJiang</div>
  </div>
  
  <!-- 下面时JS的代码 -->
  <script type="text/javascript">
      // 获取一个元素(定位、选择)
      //document表示当前文件  .innerHTML表示找这个元素夹着的内容,JS中定义变量通常在前面添加var
      var calTitle = document.getElementById("calc-title").innerHTML;
      // 弹窗输入变量名
      window.alert(calTitle);
  
  </script>
  ```

- 将JS代码包裹在函数块中,在特定时刻调用执行

  ```html
      <!-- 下面时JS的代码 -->
      <script type="text/javascript">
          // 获取一个元素(定位、选择)
          //document表示当前文件  .innerHTML表示找这个元素夹着的内容,JS中定义变量通常在前面添加var
          //function 定义一个函数，被函数包裹的代码，如果没有触发条件或调用代码，代码就不会执行
          function alertTitle(){
              // 在函数体中，变量之前加var，表示是当前函数内部的局部变量，否则则视为全局变量，建议添加
              var calTitle = document.getElementById("calc-title").innerHTML;
              // 弹窗输入变量名
              window.alert(calTitle);
          }
  
      </script>
  </head>
  <!-- onload元素事件表示页面加载完成后，自动执行()中的事件 -->
  <body onload="alertTitle()">
  
      <div class="outer">
          <div id="top">
              <!-- class="point red" : 表示归属于两个类 -->
              <div class="point red"></div>
              <div class="point yellow"></div>
              <div class="point green"></div>
              <!-- YikJiang -->
              <div id="calc-title">煎蛋杨粑粑</div>
          </div>
      
          <div id="result"></div>
  
          <div id="button"> 
              <!-- onclick：单击触发 -->
              <div onclick="alertTitle()">AC</div>
              <div>+/-</div>
              <div>%</div>
              <div>÷</div>
              <div>7</div>
              <div>8</div>
              <div>9</div>
              <div>*</div>
              <div>4</div>
              <div>5</div>
              <div>6</div>
              <div>-</div>
              <div>1</div>
              <div>2</div>
              <div>3</div>
              <div>+</div>
              <div>0</div>
              <!-- ondblclick：双击触发 -->
              <div ondblclick="alertTitle()">Del</div>
              <div>.</div>
              <div>=</div>
          </div>
      </div>
  ```

#### 2、JS的元素定位

```js
// 通过ID定位到对应的元素，是单数形式，返回的就是元素本身
document.getElementById("calc-title");

document.getElementsByClassName("point");        // 得到三个class = point的元素，返回一个包含这三个元素的数组
document.getElementsByName("result");            //  获取到name = result 的一个元素，返回一个包含这一个元素的数组
document.getElementsByTagName("div");           // 获取当前文档中所以的DIV

// 获取到的数组不可以使用.innerHTML，需要先获取到下标
var result = document.getElementsByName("result")[0].innerHTML;
window.alert(result);

// JS中也可以通过Xpath来定义
XML：可扩展标记语言，用于描述一组数据，标记可以任意定义，类似于数据库中的行和列。
HTML：超文本标记语言，用于描述页面元素，所以标记都是事先约定，浏览器厂商统一支持。
```

- 例如下面描述了两本书

```xml
<bookstore>
    <book id="book_01">		 <!--对应第一行-->
      <title>Harry Potter</title>		<!--对应第一列  title可以任意写-->
      <author>J K. Rowling</author>			<!--对应第二列-->
      <year>2005</year>
      <price>29.99</price>
    </book>
    
    <book id="book_02">		<!-- 对应第二行-->
      <title>Harry Potter</title>
      <author>J K. Rowling</author>
      <year>2005</year>
      <price>29.99</price>
    </book>

</bookstore>
```

- 以下XPATH的实例说明

```js
// a[@href] 表示当前页面中所有的 超链接 中有 href 属性的元素
var result = document.evaluate("//a[@href]", document, null, XPathResult.ANY_TYPE, null);

//div[@id='xxx'] 表示当前页面中所有的 DIV 元素中，id='xxx'的元素
nodes=document.evaluate("//div[@id='xxx']", document).iterateNext();
```

### 三、利用Js实现计算器

#### 1、基本操作

- 当单击每个按钮的时候，需要相应单击事件，并输入相应的值在result元素中显示出来
- 避免连续输入运算符

#### 2、响应单击事件输入数字

```js
<script type="text/javascript">
    // 需要给函数传递一个参数，用于输入那一个数字
    function clickNumber(number){
        var result = document.getElementById("result");
        result.innerHTML += number;
    }
</script>

<div onclick="clickNumber(7)">7</div>
<div onclick="clickNumber(8)">8</div>
<div onclick="clickNumber(9)">9</div>
```

#### 3、响应单击事件输入运算符

```js
function clickOperator(operator){
    var result = document.getElementById("result")
    result.innerHTML += operator
}

<div onclick="clickOperator('%')">%</div>
<div onclick="clickOperator('/')">÷</div>
```

#### 4、如何运算result中表达式的结果

- 在JS中，有一个函数叫做：`eval`
- 容易造成安全隐患

```js
var a = "200";
var b = 100;
window.alert("a+b")	// 因为 "" 内的是字符串，所以输入的为a+b 
window.alert(eval("a+b"))		// 使用eval函数，会将a+b当做代码来执行，输出200100
```

```js
function doCalc(){
    var result = document.getElementById("result")
    var expression = result.innerHTML;
    // 此时因为获取到的值为字符串，所以不可以直接进行运算
    result.innerHTML = eval(expression);
}
```

####  5、解决运算符连续输入的问题

- 设置一个开关`True 或 False`

  > 本方案需要定义全局变量，同时需要在`clickNumber`和`clickOperator`等函数中重置开关，会导致多个函数之间的耦合度提高，耦合度越高，互相之间的影响也就越大，任何一个函数体出问题，可能会直接影响到其他函数。

  ```js
  在<script>级定义一个全局变量，在function级别操作
  
  // 定义一个开关变量，用于判断最后一次输入的是否为运算符
  // 变量名通常使用is开头
  var isOperatorClicked = false;      // 与function同级的变量，可以称为全局变量，可以在当前范围内的任意function中使用
  
  // 需要给函数传递一个参数，用于输入那一个数字
      
  function clickNumber(number){
              var result = document.getElementById("result");
              // 字符串相连
              result.innerHTML += number;
              isOperatorClicked = false;   // 当用户再次点击了数字后又重置开关为可点击运算符
          }
  
          // 运算符
  function clickOperator(operator){
      var result = document.getElementById("result")
      if (isOperatorClicked == false){
      result.innerHTML += operator
      isOperatorClicked = true    // 表示运算符被点击
  
      }
  
  }
  ```

- 判断最后一个字符是否是运算符，如果是 `+ - * / %`五个运算中的一个则再出入运算符时作替换而不是连接

  > 本方案没有与其他函数或全局变量进行耦合，而是在同一函数快里解决问题（高内聚，底耦合）
  
  ```js
function clickOperator(operator){
      var result = document.getElementById("result")
      var String = result.innerHTML;
      var len = String.length;
      var last = String.charAt(len-1);
      if(last == "+" || last == "-" || last == "/" || last == "%"|| last == "*"){
          var tmp = String.substr(0,len-1) + operator;    //代替最后一个运算符为新输入的运算符
          result.innerHTML = tmp; // 将替换后的新表达式赋值给result
      }   
      else{
      	result.innerHTML += operator;
      }
  }
  ```

#### 6、解决小数点连续输入的问题

> 小数点不能直接调用`clickNumber()`和`clickOperator()`函数，会导致耦合增加，应该另起一个新的函数

```js
function clickDrop(drop){
    var result = document.getElementById("result");
    result.innerHTML += drop;
}
```

## PHP基础语法与字符串

### 一、基本结构

#### 1、代码块

PHP是运行于Web服务中，主要用于网页的处理。

PHP 是一种创建动态交互性站点的强有力的服务器端脚本语言，由C语言编写

```php
<?php
    // 必须使用<?php   ? >进行包裹
?>
```

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
    <?php
        // 可以在PHP的源文件中，直接写HTML的代码，但是在HTML里不可以写PHP代码
    ?>
</body>
</html>
```

#### 2、注释

```php
<?php
    // 必须使用<?php   ? >进行包裹
    /*
    用于注释一个段落
    */
?>
```

#### 3、内容输出

```php
<?php
    // 必须使用<?php   ? >进行包裹
    /*
    在PHP中，可以通过两个甘薯往页面中输出注释
        1、echo:支持用逗号分隔多个字符进行拼接输出
        2、print：不支持用逗号分隔多个字符进行拼接输出
    注意：在PHP中，换行符\n无法被浏览器解析
        <br>才能被浏览器解析
    */
    echo "YikJiang~ <br/>";
    print"Lebron!<br>";

    echo "123","456","789<br>";
    // print "123"."456"."789";        // print不能跟逗号分隔多个字符串

    // 在PHP中，.表示字符串连接符
    echo "123"."456"."789<br>";
    print "123"."456"."789<br>";

    echo "您好，您的余额为: " . 20000 . "元";


?>
```

- **换行符**

  - 页面

    ![image-20220514091858538](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241535158.png)

  - 源代码

    ![image-20220514091912635](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241535159.png)

#### 4、引号

```php
/**
* 引号的问题：
*  1、双引号：可以包裹字符串和变量
*  2、单引号：只能表示字符串，不能引用变量
*  3、反引号：用于执行操作系统命令并返回结果
*/
$addr = "天津市大学软件学院";
echo "您当前所在的位置为：$addr<br>";
echo '您当前所在的位置为：$addr<br>';
echo `ipconfig`;
```

#### 5、通信过程

- 因为是PHP脚本引擎在执行，所以说网页端看不到源代码
- 脚本引擎处理后，才会发给服务器端
- 而HTML是服务器交给浏览器进行处理，所以可以看到网页的源代码

<img src="https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241535160.png" alt="image-20220514091509097" style="zoom:67%;" />

### 二、变量

#### 1、数据类型

```php
String(字符型)："YikJiang","天津"
Integer(整型)： 12345 -200
Float(浮点型)：123.123  -123.23
Boolean(布尔型)：true  false
Array(数组)：一组数据的集合
Object(对象)
NULL(空值)
```

#### 2、命名规范

```c
变量以$符号开始，后面跟着变量的名称
变量名必须以字母或者下划线字符开始
变量名只能包含字母，数字以及下划线(A-z,0-9,_)
变量名不能包含空格
变量名是区分大小写
函数名必须使用动词或动名词形式
```

### 三、运算符

#### 1、算数运算符

| 运算符 | 名称             | 描述            | 实例                        | 结果  |
| :----- | :--------------- | :-------------- | :-------------------------- | :---- |
| x + y  | 加               | x 和 y 的和     | 2 + 2                       | 4     |
| x - y  | 减               | x 和 y 的差     | 5 - 2                       | 3     |
| x * y  | 乘               | x 和 y 的积     | 5 * 2                       | 10    |
| x / y  | 除               | x 和 y 的商     | 15 / 5                      | 3     |
| x % y  | 模（除法的余数） | x 除以 y 的余数 | 5 % 2 10 % 8 10 % 2         | 1 2 0 |
| - x    | 取反             | x 取反          | `<?php $x =2; echo -$x; ?>` | -2    |
| a . b  | 并置             | 连接两个字符串  | "Hi" . "Ha"                 | HiHa  |

#### 2、赋值运算符

| 运算符 | 等同于    | 描述                           |
| :----- | :-------- | :----------------------------- |
| x = y  | x = y     | 左操作数被设置为右侧表达式的值 |
| x += y | x = x + y | 加                             |
| x -= y | x = x - y | 减                             |
| x *= y | x = x * y | 乘                             |
| x /= y | x = x / y | 除                             |
| x %= y | x = x % y | 模（除法的余数）               |
| a .= b | a = a . b | 连接两个字符串                 |

#### 3、递增/递减运算符

| 运算符 | 名称   | 描述                |
| :----- | :----- | :------------------ |
| ++ x   | 预递增 | x 加 1，然后返回 x  |
| x ++   | 后递增 | 返回 x，然后 x 加 1 |
| -- x   | 预递减 | x 减 1，然后返回 x  |
| x --   | 后递减 | 返回 x，然后 x 减 1 |

#### 4、比较运算符

| 运算符  | 名称       | 描述                                           | 实例               |
| :------ | :--------- | :--------------------------------------------- | :----------------- |
| x == y  | 等于       | 如果 x 等于 y，则返回 true                     | 5==8 返回 false    |
| x === y | 绝对等于   | 如果 x 等于 y，且它们类型相同，则返回 true     | 5==="5" 返回 false |
| x != y  | 不等于     | 如果 x 不等于 y，则返回 true                   | 5!=8 返回 true     |
| x <> y  | 不等于     | 如果 x 不等于 y，则返回 true                   | 5<>8 返回 true     |
| x !== y | 绝对不等于 | 如果 x 不等于 y，或它们类型不相同，则返回 true | 5!=="5" 返回 true  |
| x > y   | 大于       | 如果 x 大于 y，则返回 true                     | 5>8 返回 false     |
| x < y   | 小于       | 如果 x 小于 y，则返回 true                     | 5<8 返回 true      |
| x >= y  | 大于等于   | 如果 x 大于或者等于 y，则返回 true             | 5>=8 返回 false    |
| x <= y  | 小于等于   | 如果 x 小于或者等于 y，则返回 true             | 5<=8 返回 true     |

#### 5、逻辑运算符

| 运算符   | 名称 | 描述                                         | 实例                                 |
| :------- | :--- | :------------------------------------------- | :----------------------------------- |
| x and y  | 与   | 如果 x 和 y 都为 true，则返回 true           | x=6 y=3 (x < 10 and y > 1) 返回 true |
| x or y   | 或   | 如果 x 和 y 至少有一个为 true，则返回 true   | x=6 y=3 (x\==6 or y==5) 返回 true    |
| x xor y  | 异或 | 如果 x 和 y 有且仅有一个为 true，则返回 true | x=6 y=3 (x\==6 xor y==3) 返回 false  |
| x && y   | 与   | 如果 x 和 y 都为 true，则返回 true           | x=6 y=3 (x < 10 && y > 1) 返回 true  |
| x \|\| y | 或   | 如果 x 和 y 至少有一个为 true，则返回 true   | x=6 y=3 (x\==5 \|\| y==5) 返回 false |
| ! x      | 非   | 如果 x 不为 true，则返回 true                | x=6 y=3 !(x==y) 返回 true            |

### 四、分支语句

#### 1、if…else…

- 语法

```php
if (条件){
条件成立时执行的代码;
}
else{
条件不成立时执行的代码;
}
```

- 实例

```php
<?php
$t=date("H");
if ($t<"20"){
    echo "Have a good day!";
}
else{
    echo "Have a good night!";
}
?>
```

#### 2、if...elseif....else 

- 语法

```php
if (条件){
    if 条件成立时执行的代码;
}
elseif (条件){
    elseif 条件成立时执行的代码;
}
else{
    条件不成立时执行的代码;
}
```

- 实例

```php
<?php
$t=date("H");
if ($t<"10"){
    echo "Have a good morning!";
}
elseif ($t<"20"){
    echo "Have a good day!";
}
else{
    echo "Have a good night!";
}
?>
```

#### 3、 switch 

- 语法

```php
<?php
switch (n){
case label1:
    如果 n=label1，此处代码将执行;
    break;
case label2:
    如果 n=label2，此处代码将执行;
    break;
default:
    如果 n 既不等于 label1 也不等于 label2，此处代码将执行;
}
?>
```

- 实例

```php
<?php
$favcolor="red";
switch ($favcolor){
case "red":
    echo "你喜欢的颜色是红色!";
    break;
case "blue":
    echo "你喜欢的颜色是蓝色!";
    break;
case "green":
    echo "你喜欢的颜色是绿色!";
    break;
default:
    echo "你喜欢的颜色不是 红, 蓝, 或绿色!";
}
?>
```

### 五、循环语句

- **while** - 只要指定的条件成立，则循环执行代码块
- **do...while** - 首先执行一次代码块，然后在指定的条件成立时重复这个循环
- **for** - 循环执行代码块指定的次数
- **foreach** - 根据数组中每个元素来循环代码块

```php
//当秒数小于30s时，循环执行
$i = date('s');
while($i < 30){
	echo date( "Y-m-d H:i:s");
    sleep(1);
}
/*
问题一：上述代码如果从00s开始执行，不会按照既定的每一秒输入到屏幕上，而是等循环结束后一次性输出
*/
//当 $i 自增到11时，循环结束
$i = 1;
while($i <= 10){
    echo $i . '<br/>';
    $i++;
}

//当 $i 自增到11时，循环结束
for ($i=1;$i<=10;$i++){
    echo $i . '<br/>';
}

// while比较适用于有条件，无次数的情况，比如按行读取文件，文件读取结束后会有一个结束标志
// for比较适用于有明确循环次数的情况，比如各类运算或者遍历
```

- 问题

```php
//当秒数小于30s时，循环执行
$i = date('s');
while($i < 30){
	echo date( "Y-m-d H:i:s");
    sleep(1);
}

问题一：上述代码如果从00s开始执行，不会按照既定的每一秒输入到屏幕上，而是等循环结束后一次性输出
		$i = date('s');
        while($i < 30){
            ob_flush();         //清空缓冲区，直接输出
            flush();
            echo date( "Y-m-d H:i:s") . "<br/>";
            $i = date("s");
            sleep(1);
        }
解决方法：在代码存在sleep的时间，使用ob_flush()和fulsh()两个函数进行处理，让缓冲区不再被sleep阻塞
问题二：PHP代码执行时间超过30s会报错

问题三：默认情况下，PHP输出的时间跟系统的不一致，差6小时，这是因为时区设置的不同导致的
```

### 六、手机号码

**不适用正则表达式的情况下，只使用字符串处理的方式，判断一个手机号码是否有效**

- 必须为11位：如何计算字符串的位数
- 第1位必须是1：如何取得第1位
- 第2位只能在3-9：同上，并且如何与3-9的范围做比较
- 所有位(后9位)必须是数字：对每一位进行判断
- 不同号段的第3位是有要求的，此处不专门考虑

### 七、函数

#### 1、基本的构成

- 函数名：函数名不能重复，名称必须可读性强，最好是动词或者动名词形式
- 函数可以有参数：形参和实参
- 函数有处理过程：函数体
- 函数可以有返回值，也可以没有
- 函数只有定义，不调用，代码不会执行

#### 2、函数的三要素(函数规范，接口类型)

- 函数名
- 参数(参数个数、顺序、类型)
- 返回值

### 八、正则表达式

| 字符   | 描述                                                         |
| :----- | :----------------------------------------------------------- |
| \      | 将下一个字符标记为一个特殊字符、或一个原义字符、或一个 向后引用、或一个八进制转义符。例如，'n' 匹配字符 "n"。'\n' 匹配一个换行符。序列 '\\' 匹配 "\" 而 "\(" 则匹配 "("。 |
| ^      | 匹配输入字符串的开始位置。如果设置了 RegExp 对象的 Multiline 属性，^ 也匹配 '\n' 或 '\r' 之后的位置。 |
| $      | 匹配输入字符串的结束位置。如果设置了RegExp 对象的 Multiline 属性，$ 也匹配 '\n' 或 '\r' 之前的位置。 |
| *      | 匹配前面的子表达式零次或多次。例如，zo* 能匹配 "z" 以及 "zoo"。* 等价于{0,}。 |
| +      | 匹配前面的子表达式一次或多次。例如，'zo+' 能匹配 "zo" 以及 "zoo"，但不能匹配 "z"。+ 等价于 {1,}。 |
| ?      | 匹配前面的子表达式零次或一次。例如，"do(es)?" 可以匹配 "do" 或 "does" 。? 等价于 {0,1}。 |
| {n}    | n 是一个非负整数。匹配确定的 n 次。例如，'o{2}' 不能匹配 "Bob" 中的 'o'，但是能匹配 "food" 中的两个 o。 |
| {n,}   | n 是一个非负整数。至少匹配n 次。例如，'o{2,}' 不能匹配 "Bob" 中的 'o'，但能匹配 "foooood" 中的所有 o。'o{1,}' 等价于 'o+'。'o{0,}' 则等价于 'o*'。 |
| {n,m}  | m 和 n 均为非负整数，其中n <= m。最少匹配 n 次且最多匹配 m 次。例如，"o{1,3}" 将匹配 "fooooood" 中的前三个 o。'o{0,1}' 等价于 'o?'。请注意在逗号和两个数之间不能有空格。 |
| ?      | 当该字符紧跟在任何一个其他限制符 (*, +, ?, {n}, {n,}, {n,m}) 后面时，匹配模式是非贪婪的。非贪婪模式尽可能少的匹配所搜索的字符串，而默认的贪婪模式则尽可能多的匹配所搜索的字符串。例如，对于字符串 "oooo"，'o+?' 将匹配单个 "o"，而 'o+' 将匹配所有 'o'。 |
| .      | 匹配除换行符（\n、\r）之外的任何单个字符。要匹配包括 '\n' 在内的任何字符，请使用像"**(.\|\n)**"的模式。 |
| x\|y   | 匹配 x 或 y。例如，'z\|food' 能匹配 "z" 或 "food"。'(z\|f)ood' 则匹配 "zood" 或 "food"。 |
| [xyz]  | 字符集合。匹配所包含的任意一个字符。例如， '[abc]' 可以匹配 "plain" 中的 'a'。 |
| [^xyz] | 负值字符集合。匹配未包含的任意字符。例如， '\[^abc]' 可以匹配 "plain" 中的'p'、'l'、'i'、'n'。 |
| [a-z]  | 字符范围。匹配指定范围内的任意字符。例如，'[a-z]' 可以匹配 'a' 到 'z' 范围内的任意小写字母字符。 |
| [^a-z] | 负值字符范围。匹配任何不在指定范围内的任意字符。例如，'\[^a-z]' 可以匹配任何不在 'a' 到 'z' 范围内的任意字符。 |
| \d     | 匹配一个数字字符。等价于 [0-9]。                             |
| \D     | 匹配一个非数字字符。等价于\[^0-9]。                          |
| \w     | 匹配字母、数字、下划线。等价于'[A-Za-z0-9_]'。               |
| \W     | 匹配非字母、数字、下划线。等价于 '\[^A-Za-z0-9_]'。          |

### 九、数组

#### 1、基础使用

- 作用

  - 数组就是将一组数据，用统一的结构来保存和使用，对于一组数据来说，如果不使用数组，则必须定义多个变量

- 定义

  - ```php
    $students = array("LeBron James","Kyle Kuzma","Alex Caruso","Anthony Davis",
                      "Carmelo Anthony","Russell Westbrook");
    ```

- 基本操作

```php
// 取数组的长度
$len = count($students);
echo $len."<br/>";

// 通过下标取值，在PHP中，从下标0开始
echo $students[1]."<br/>";
$students[2] = "YikJiang";

// 打印数组
print_r($students);
echo '<p/>';

//删除最后一个值
array_pop($students)."<br/>";
print_r($students);
echo '<p/>';
```

#### 2、索引数组

```php
$students = array("LeBron James","Kyle Kuzma","Alex Caruso","Anthony Davis","Carmelo Anthony","Russell Westbrook");
```

> 上述定义的数组，就是索引数组，以下标取值。

```php
//数组的遍历：使用循环生成下标的方式
for ($i = 0; $i<count($students);$i++){
    echo $students[$i]."<br/>";
}
//数组的遍历：foreach遍历
echo '<p/>';
foreach($students as $s){
    echo $s."<br/>";
}

// 使用原始的随机数生成器，也可以实现随机点名
echo rand(5,10);  //生成[5,10]范围的随机整数
echo '<p/>';

$index = rand(0,count($students)-1);
echo $students[$index];
echo '<p/>';
// 数组去重
$grade = array(97,43,12,55,65,12,54,12,45,65,45);
$new = array_unique($grade);
print_r($new);
echo "<p/>";

//排序
$grade = array(97,43,12,55,65,12,54,12,45,65,45);
sort($grade);
foreach($grade as $y){
    echo $y."<br/>";
}
```

#### 3、关联数组

```php
<?php
//关联数组，以key=>value组成的键值对，取值的时候用key来取值，而不是下标
//索引数组的key就是0、1、2、3、4这种数字
$student_01 = array("name" => "LeBron James",'age'=>37,'addr' => '圣玛丽高中','phone' => '18222372119');
$student_02 = array("name" => "Kyle Kuzma",'age'=>27,'addr' => '犹他大学','phone' => '18222372119');
$student_03 = array("name" => "Alex Caruso",'age'=>28,'addr' => '德克萨斯农工大学','phone' => '18222372119');
$student_04 = array("name" => "Anthony Davis",'age'=>29,'addr' => '肯塔基大学','phone' => '18222372119');
$student_05 = array("name" => "Carmelo Anthony",'age'=>38,'addr' => '雪城大学','phone' => '18222372119');
$student_06 = array("name" => "Russell Westbrook",'age'=>34,'addr' => '加州大学洛杉矶分校','phone' => '18222372119');
$student_07 = array("name" => "Dwight Howard",'age'=>37,'addr' => '亚特兰大西南基督学院','phone' => '18222372119');

echo $student_01['name']."<br/>";
echo "<p/>";
$student_01['phone'] = '888888';
//遍历数组的value
foreach ($student_01 as $stu){
    echo $stu . "<br/>";
    
}
    echo "<p/>";
//遍历数组的key和value
foreach($student_07 as $key=>$value){
    echo $key. "==" . $value . "<br/>";
    
}
    echo "<p/>";
$keys = array_keys($student_02);
foreach($keys as $key){
    echo $student_06[$key] . "<br/>";
    
}
    echo "<p/>";
//end()函数可以输出数组的最后一个值,无所谓是那种数组
echo end($student_01);
    echo "<p/>";

if (in_array('LeBron James',$student_01)){
    echo 'YikJiang'.'<br/>';
}
//把字符串打散为数组
$source = "Typora.exe-1780-Console-8-71,676 K";
$myarray = explode("-",$source);
foreach($myarray as $b){
    echo "$b"."<br/>";
}
//把数组合并成字符串
$grade = array(97,43,12,55,65,12,54,12,45,65,45);
$result = implode(',',$grade);
echo $result."<br/>";
?>
```

## 前后端交互处理

### 一、简介

​		前后端的交互过程就是HTTP协议的处理过程：请求与响应的处理过程。单纯只有前端，无法使用后台服务器的能力，或者无法访问数据库。如果单纯只有的后端，也无法形成业务流程，无法为客户产生价值 

![image-20220609113811556](https://yang-typora.oss-cn-beijing.aliyuncs.com/202206091138655.png)

**三种方式**：

1、 资源获取型：GET请求+URL地址

2、数据提交型：POST请求+URL地址+请求正文

3、AJAX提交：利用异步提交的方式，在不刷新页面的情况下，提交数据给后台x

### 二、POST请求

1、必须要使用`form`标签将所有表单元素包括起来

2、必须要在`form`标签中指定`acion`属性(URL地址)

3、必须要在`form`标签中指定`method`属性的提交方式为`POST`(默认为GET)

4、必须要确保在`form`的标签内，至少有一个提交按钮

```php
<form action="login.php" method="post">
	<div class="login">
		<input type="text" name="username" />
	</div>
	<div class="login">
		<input type="password" name="password" />
	</div>
	<div class="login">
		<input type="text" name="vocde" />
	</div>
	<div class="login">
		<!--*type="submit" 代表按钮类型为提交表单-->
		<button type="submit">登录</button>
	</div>
</form>
```

### 三、AJAX请求

- 不刷新界面更新网页
- 在页面加载后从服务器请求数据
- 在页面加载后从服务器接受数据
- 在后台服务器发送数据

![AJAX](https://yang-typora.oss-cn-beijing.aliyuncs.com/202206091630257.gif)

#### 1、引入jQuery的JS库

```
<script type="text/javascript" src="jquery-3.4.1.min.js"></script>
```

#### 2、不再需要form，只需要任意一个人元素发起一个JS时间，让JS代码进行处理

```php
<script>
	function doPost(){
		//获取表单元素的值
		var username = $("#username").val();
		var passowrd = $('#password').val();
		var vcode = $('#vcode').val();
		//通过字符串拼接为一个请求正文
		var param = 'username='+ username +'&password=' + passowrd + '&vcode=' + vcode;
		// 利用AJAX发送post请求，并获取响应
		//参数1：发送到哪里；参数2：发送的数据；参数3：响应; 
		//定义匿名函数，参数为data,称之为回调 
		$.post('login.php',param,function(data){
			//处理响应的JS代码
			$('#username').val(data);
		});

	}   

</script>
```

## Session & Cookie



![image-20220612221701067](https://yang-typora.oss-cn-beijing.aliyuncs.com/202206122217192.png)