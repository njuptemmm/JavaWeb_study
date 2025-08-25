## JS+Vue+Ajax

### JS基础

#### JS引入

一般方法是JS代码定义在外部 JS文件中，然后引入到 HTML页面中

- 在HTML文档中，可以在任意地方，放置任意数量的<script></script>
- 一般会把脚本置于<body>元素的底部，可改善显示速度

- 在html文件中，通过<script></script>引入js文件`demo.js`，如下

```html
<script src="js/demo.js"></script>
```

下面对于实际的使用进行举例，其中就用两种方法分别实现js的输入

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS基础语法</title>
</head>
<body>
    <!--
    <script>
        //方式一: 写入浏览器的body区域->也就是写在网页的中间
        document.write("Hello JS (document.write)");

        //方式二: 弹出框->打开网页之后会弹出的内容
        window.alert("Hello JS (window.alert)");

        //方式三: 控制台->使用浏览器打开之后使用F12能够打开开发者模式，在其中控制台的部分可以看到输出的结果。在此基础之上，可以在一边查询到源代码，里面就会显示你编程时候使用的源代码，其中引用到不同文件夹的文件也可以直接进行跳转
        console.log("Hello JS (console.log)")
    </script>
    -->  
    <script src="./js/2-1.js"></script>

</body>
</html>
```

![image-20250821151054780](C:\Users\23816\AppData\Roaming\Typora\typora-user-images\image-20250821151054780.png)

#### JS变量及其输出

- 接下来，我们再来讲解JS中的变量。在js中，变量的声明和java中还是不同的。
  - JS中主要通过 `let` 关键字来声明变量的。
  - JS是一门弱类型语言，变量是可以存放不同类型的值的。
- 在JS中，如果声明一个场景，需要使用`const`关键字。一旦声明，常量的值就不能改变 （不可以重新赋值）。

表达字符串的时候

```HTML
  <script>
    let name = 'Tom';
    let age = 18;
    console.log('大家好, 我是新入职的' + name + ', 今年' + age + '岁了, 请多多关照'); //原始方式 , 手动拼接字符串
    console.log(`大家好, 我是新入职的${name}, 今年${age}岁了, 请多多关照`); //使用模板字符串方式拼接字符串
  </script>
```

#### JS函数

##### 函数：

```javascript
function add(a, b){
    return a + b;
}
let result=add(10,20);
```

##### 匿名函数：

```javascript
var add = function (a,b){
    return a + b;
}

var add = (a,b) => {
    return a + b;
}

let result=add(10,20);//这样子设定的函数照样可以在后面直接利用参数a和b来完成相关函数操作

```

几种定义函数的方法都是类似的，最后调用的方法都是和C语言的调用方法类似

```javascript
let user = {
    name: "Mike",
    APIKEY:"sk-123",
    add: function (a, b) {
        return a + b;
    }
}
document.write(user.add(10, 20));
document.write(user.name);
```

##### 回调函数

```javascript
// 这是你的主函数，它接受一个回调函数作为参数
function calculate(num1, num2, callback) {
    console.log("主函数开始计算...");
    // 假设这里有一些复杂的逻辑或异步操作
    
    // 在主函数内部，调用了作为参数传入的 callback 函数
    const result = callback(num1, num2); 
    
    console.log("计算结果是：", result);
}

// 这是 add 函数
var add = (a, b) => {
    return a + b;
};

// --- 现在，我们把 add 作为回调函数传递给 calculate ---

// 我们在调用 calculate 时，将 add 作为一个参数传了进去
calculate(5, 3, add); 
// 输出:
// 主函数开始计算...
// 计算结果是： 8
```

在main函数定义的时候我们可以将一个函数作为参数加入主函数中，之后可以作为一个函数当作参数传进去，之后就可以使用这个函数，就是回调函数。

#### 表格

使用的只有` <table>、<thead>、<tbody> <tfoot>`

```html
<table>
  <thead>
    <tr>
      <th>姓名</th>
      <th>年龄</th>
      <th>城市</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>张三</td>
      <td>30</td>
      <td>北京</td>
    </tr>
    <tr>
      <td>李四</td>
      <td>25</td>
      <td>上海</td>
    </tr>
  </tbody>
</table>
```

`<tr></tr>`就是用来表示表格中的每一行的数值，也就是我们在运算中使用的数值。

`<td></td>`表示的是表个中间每一格中的数值。

#### 对象

```js
let user = {
    name: "Mike",
    APIKEY:"sk-123",
    add: function (a, b) {
        return a + b;
    }
}
document.write(user.add(10, 20));
document.write(user.name);
```

JSON

JSON是在JS中使用的一种数据格式（可以进一步认为是一种**文本格式**）

当你需要将一个 JavaScript 对象发送到服务器时（例如，提交一个表单），你不能直接发送一个对象，因为网络传输的数据必须是文本格式。此时，你可以使用 `JSON.stringify()` 方法将 JavaScript 对象转换为一个 JSON 字符串。

```js
const user = {
  name: "Bob",
  email: "bob@example.com"
};

// 将对象转换为 JSON 字符串
const jsonString = JSON.stringify(user);
// jsonString 现在是 '{"name":"Bob","email":"bob@example.com"}'
```

当你从服务器收到一个 JSON 响应时，它是一个字符串。为了在 JavaScript 代码中使用这个数据，你需要将其转换回一个 JavaScript 对象。此时，`JSON.parse()` 方法就派上用场了。

```js
// 假设这是从服务器收到的 JSON 字符串
const responseJson = '{"id": 123, "productName": "Laptop", "price": 999.99}';

// 将 JSON 字符串解析为 JavaScript 对象
const product = JSON.parse(responseJson);
// product 现在是一个 JavaScript 对象：
// { id: 123, productName: 'Laptop', price: 999.99 }

// 现在你可以轻松地访问和使用这个对象
console.log(product.productName); // 输出: Laptop
```

所以说JSON格式是js对象转化之后的结果，从而实现在服务器中的数据传输

JSON相关的函数（也就是前面我们提及的那两个）：

- **`JSON.parse()`**：**解析**。用于将 JSON 字符串转换成一个 JavaScript 对象。

- **`JSON.stringify()`**：**序列化**。用于将一个 JavaScript 对象或值转换为 JSON 字符串。



**JSON中不允许出现的内容**

- 函数、Symbol、undefined、BigInt

- 循环引用

- 日期对象会被序列化为 ISO 字符串（需手动再转为 Date）

- 原型链、属性描述符（writable、enumerable…）全部丢失

  

#### JS DOM

它让你可以在一个 **非浏览器环境**（比如 Node.js）中使用类似浏览器的方式来操作 HTML 文档。

用处：让JavaScript能够**与网页内容进行交互**。

- DOM的核心思想：将网页的内容当做对象来处理，标签的所有属性在该对象上都可以找到，并且修改这个对象的属性，就会自动映射到标签身上。（从而实现与界面进行交互之后能够完成）
- document对象
  - 网页中所有内容都封装在document对象中
  - 它提供的属性和方法都是用来访问和操作网页内容的，如：document.write(…)
- DOM操作步骤:
  - 获取DOM元素对象
  - 操作DOM对象的属性或方法 (查阅文档)

**这个是后面很多工作的基础，我们会在后面的工作中继续详细谈及相关的使用方法**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JS-DOM</title>
</head>
<body>

  <h1 id="title1">11111</h1>
  <h1>22222</h1>
  <h1>33333</h1>

  <script>
    //1. 修改第一个h1标签中的文本内容
    //1.1 获取DOM对象
    // let h1 = document.querySelector('#title1');
    //let h1 = document.querySelector('h1'); // 获取第一个h1标签

    let hs = document.querySelectorAll('h1');

    //1.2 调用DOM对象中属性或方法
    hs[0].innerHTML = '修改后的文本内容';
  </script>
</body>
</html>
```

### JS事件监听

```javascript
事件源.addEventListener('事件类型', 要执行的函数);
```

在上述的语法中包含三个要素: 

- 事件源: 哪个dom元素触发了事件, 要获取dom元素
- 事件类型: 用什么方式触发, 比如: 鼠标单击 click, 鼠标经过 mouseover
- 要执行的函数: 要做什么事

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-事件-事件绑定</title>
</head>

<body>
    <input type="button" id="btn1" value="点我一下试试1">
    <input type="button" id="btn2" value="点我一下试试2">
        
    <script>
        document.querySelector("#btn1").addEventListener('click', ()=>{
            alert("按钮1被点击了...");
        })
    </script>
</body>
</html>
```

其中我们需要集中考虑到是

```javascript
document.querySelector("#btn1").addEventListener('click', ()=>{
            alert("按钮1被点击了...");
        })
```

- document是DOM树的根对象，能够调用相关的方法
- .querySelector("#btn1")
  - 这是一个 **DOM 方法**，用于从文档中**查找**（查询）并返回第一个匹配指定 CSS 选择器的元素。
  - 在这里，`#btn1` 是一个 **CSS 选择器**。`#` 符号表示它正在查找一个 `id` 属性为 `btn1` 的元素。
- **`.addEventListener('click', ...)`**:
  - 这是获取到 DOM 元素后，最常用的一个方法。它的作用是为该元素**添加一个事件监听器**。
  - 它接收两个参数：
    1. `'click'`: 这是要监听的事件类型。在这里，我们监听的是 `click` 事件，也就是**鼠标点击**。
    2. `()=>{ alert("按钮1被点击了..."); }`: 这是一个 **回调函数 (Callback Function)**，通常使用箭头函数 (`=>`) 语法。它定义了当事件被触发时需要执行的**操作**。（暂时不用考虑这个为什么是回调函数，只要知道能够这样使用就可以了）

下面是另一个更加进阶的例子

```javascript
const trs = document.querySelectorAll('tr');

      for (let i = 1; i < trs.length; i++) {

        trs[i].addEventListener('mouseenter', function () {//mouse&enter

          this.style.backgroundColor = '#f2e2e2';

        });

        trs[i].addEventListener('mouseleave', function () {//mouse&leave

          this.style.backgroundColor = '#fff';

        });

      }
```

**`const trs = document.querySelectorAll('tr');`**

- **`.querySelectorAll('tr')`**: 这是一个强大的 DOM 方法，它根据括号里的 CSS 选择器（`'tr'`）来查找文档中所有匹配的元素。
  - 与 `querySelector` 不同的是，`querySelectorAll` 会返回一个包含所有匹配元素的 **NodeList**（节点列表）。即使只有一个元素匹配，它也会返回一个包含该单个元素的 NodeList。
  - 在这个例子中，它会找到页面上所有的 `<tr>` 标签，并把它们收集起来，形成一个类数组对象。
  - `<tr>` 标签在 HTML 中用于定义 **表格中的行 (Table Row)**
- **`const trs`**: 使用 `const` 关键字声明一个常量 `trs`，将前面获取到的 NodeList 赋值给它。这个变量现在就是所有表格行的“集合”。

#### 常用事件

![803e36de-166b-4ca3-96d9-62e0b2bfbf3f](D:\OneDrive\Pictures\Screenshots\803e36de-166b-4ca3-96d9-62e0b2bfbf3f.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-事件-常见事件</title>
</head>

<body>
    <form action="" style="text-align: center;">
        <input type="text" name="username" id="username">
        <input type="text" name="age" id="age">
        <input id="b1" type="submit" value="提交">
        <input id="b2" type="button" value="单击事件">
    </form>

    <br><br><br>

    <table width="800px" border="1" cellspacing="0" align="center">
        <tr>
            <th>学号</th>
            <th>姓名</th>
            <th>分数</th>
            <th>评语</th>
        </tr>
        <tr align="center">
            <td>001</td>
            <td>张三</td>
            <td>90</td>
            <td>很优秀</td>
        </tr>
        <tr align="center" id="last">
            <td>002</td>
            <td>李四</td>
            <td>92</td>
            <td>优秀</td>
        </tr>
    </table>
    
    <script>
        //click: 鼠标点击事件
        document.querySelector('#b2').addEventListener('click', () => {
            console.log("我被点击了...");
        })
        
        //mouseenter: 鼠标移入
        document.querySelector('#last').addEventListener('mouseenter', () => {
            console.log("鼠标移入了...");
        })

        //mouseleave: 鼠标移出
        document.querySelector('#last').addEventListener('mouseleave', () => {
            console.log("鼠标移出了...");
        })

        //keydown: 某个键盘的键被按下
        document.querySelector('#username').addEventListener('keydown', () => {
            console.log("键盘被按下了...");
        })

        //keydown: 某个键盘的键被抬起
        document.querySelector('#username').addEventListener('keyup', () => {
            console.log("键盘被抬起了...");
        })

        //blur: 失去焦点事件
        document.querySelector('#age').addEventListener('blur', () => {
            console.log("失去焦点...");
        })

        //focus: 元素获得焦点
        document.querySelector('#age').addEventListener('focus', () => {
            console.log("获得焦点...");
        })

        //input: 用户输入时触发
        document.querySelector('#age').addEventListener('input', () => {
            console.log("用户输入时触发...");
        })

        //submit: 提交表单事件
        document.querySelector('form').addEventListener('submit', () => {
            alert("表单被提交了...");
        })
    </script>
</body>

</html>
```

各种相关的有关于事件的触发器就是上面我们实现的相关功能。



### VUE开发

vue的功能：基于数据渲染出用户看到的界面

#### vue3代码

VUE3代码开始实例

```html
<!-- vue3相关的学习工作-->
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8" />
  <title>Vue 3 Demo</title>
</head>
<body>
  <div id="app">
    <!--其中就是对于这一块代码命名成app便于后面的寻找-->
    Here is the place to show 
  </div>

  <!-- 1. 引入 Vue 3 的 ESM 构建 -->
  <script type="module">
    import { createApp, ref } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';

    <!--使用setup()优势是能够调用各种组合函数-->  
    createApp({
      setup() { 
        const message = ref('Hello Vue 3!');
        return { message };
      }
    }).mount('#app');
      
    <!--使用data()就是就不能使用vue3自带的各种组合函数，只能够完成对应的值的更换-->
     createApp({
		return{
			message:"hello Vue"	
     }
     }) .mount('#app')
      
  </script>
</body>
</html>
```

1️⃣ `<script type="module">`

- 浏览器一旦看到 `type="module"`，就把整段代码当成 **ES Module** 处理。
- 模块拥有独立作用域，不会污染全局；支持 `import`/`export`、自动延迟执行（等 DOM 解析完再跑）。

2️⃣ `import { createApp, ref } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';`

- 从 CDN 拉取 Vue 的 **浏览器版 ESM 构建**（文件后缀 `.esm-browser.js`）。
- 该文件已去掉 Node 专用代码，只保留浏览器需要的运行时，体积较小。
- 解构导入两个 API：->位于网络的文件中，浏览器通过HTTP将其下载并且按照JS的模块进行解析
  • `createApp`：生成应用实例；
  • `ref`：创建响应式引用（包装基本类型值）。

3️⃣ `createApp({ … })`

- 创建一个 **Vue 应用实例**。
- 传入的对象就是顶层组件的选项（这里只有一个 `setup`）。

4️⃣ `setup() { … }`->反正就是每个组件实例在创建阶段只会调用一次 

- **Composition API** 的入口钩子，在组件创建时执行一次。
- 内部可以用任何组合式函数，逻辑更灵活、可复用。

5️⃣ `const message = ref('Hello Vue 3!');`

- `ref` 把字符串 `'Hello Vue 3!'` 变成 **响应式对象** `{ value: 'Hello Vue 3!' }`。
- 使用`data()`的时候使用`message:str1`就可以将message转化成 **响应式对象** 
- 模板或渲染函数里读取 `message.value` 时会自动收集依赖；后续改值会触发视图更新。

6️⃣ `return { message };`

- `setup` 的返回值会暴露给模板。
- 这里把 `message` 交出去，模板中就可以直接使用 `{{ message }}`（Vue 自动解开 `.value`）。

7️⃣ `.mount('#app')`

- 告诉 Vue：把生成的 DOM 插到 **id 为 app 的元素** 里，并接管其内部渲染。
- 这一步完成后，页面 `<div id="app">{{ message }}</div>` 会被渲染成
  `<div id="app">Hello Vue 3!</div>`，且数据保持响应式。

执行时序小结
DOM 解析完成 → 浏览器执行模块 → 下载 vue.esm-browser.js → 执行 createApp → 运行 setup → 生成并挂载 vnode → 页面呈现「Hello Vue 3!」。

#### vue3指令

- v-for

  - 遍历容器的元素或者对象的属性

  - ```html
    <tr v-for="(item,index) in items" :key="item.id">{{item}}</tr>
    ```

  - **参数：**

    - items 为遍历的数组
    - item 为遍历出来的元素
    - index 为索引/下标，从0开始 ；可以省略，省略index语法： `v-for = "item in items"`

- v-bind

  - 能让固定的值变成动态的，从而能够实现不同数值的变化

  - ```html
    <!-- 完整写法 -->
    <标签 v-bind:属性名="JS表达式"></标签>
    
    <!-- 简写（最常用）-->
    <标签 :属性名="JS表达式"></标签>
    ```

    ```html
    <img :src="imgUrl">          <!-- 图片地址动态变化 -->
    <a    :href="link">跳转</a>  <!-- 链接动态变化 -->
    <input :disabled="isSend">   <!-- 禁用状态动态变化 -->
    <div  :class="clsObj">       <!-- class 动态变化 -->
    <div  :style="styleObj">     <!-- style 动态变化 -->
    ```

  - 以着上面img为例，原来src是固定的地址，但是有了`v-bind`就能够实现是src是动态的

- v-if&v-show

  - 共同使用方法：对于（一般是表格中某一格的值）进行选择而是用

  - ```html
    <!-- 基于v-show指令来展示职位这一列 -->
    <td>
        <span v-show="emp.job === '1'">班主任</span>
        <span v-show="emp.job === '2'">讲师</span>
        <span v-show="emp.job === '3'">学工主管</span>
        <span v-show="emp.job === '4'">教研主管</span>
        <span v-show="emp.job === '5'">咨询师</span>
    </td>
    ```

    进行选择的展示

  - 区别

    - v-if：直接对于DOM节点进行增删
    - v-show:只是对于CSS的display进行切换
    - 实际使用中：
      - 弹窗/权限控制 → `v-if`（一次性的出现/消失）
      - Tab 页签切换 → `v-show`（来回点很多次）

- v-model

  - 用于解决“需要用户输入，又想让输入结果实时写回变量”

  - 使用v-model

    - ```html
      <input v-model="keyword">
      ```

  - 不是v-model

    - ```html
      <input
        :value="keyword"                 <!-- ① 值输出 -->
        @input="keyword = $event.target.value">  <!-- ② 值写回 -->
      ```

    - 必须拆开为两步：
      a. 用 `:value` 把变量值渲染到输入框；
      b. 用 `@input` 把输入框的值实时写回变量。

  - **在v-model中绑定的变量必须要在data中进行定义**

- v-on

  - 用来绑定事件一个方法

  - ```html
    <!--在模块中进行定义的方法：将这个事件与方法结合-->
    <div id="app">
        <button type="botton" v-on:click="handle">Clike me_1</button>
        <button type="botton" @click="handle">Click me_2</button>
        {{message}}
    </div >
    ```

    ```html
    <script type="module">
        import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';
        createApp({
            data(){
                return{
                     message:"emmmm"
                };
            },
            methods:{//在methods中有着方法的完整定义，前面模块中的是将事件click与整个方法handle进行了结合，达到最后的触发事件之后能够运行方法。
                handle(){
                    console.log("Clike&Clike");
            }
          }
        }).mount('#app')//同时对于一个whatApp来说，其只能对应一个模块；于是说我们要对应多个模块需要分别进行处理
      </script>
    ```

  - 我们是在后面的js文件中对于变量进行声明(e.g.`message:"emmm"`)，在methods中对于对于方法进行实现，然后我们在前面的模块中进行引用**引用**

### Ajax

**浏览器与服务器在后台悄悄通信，只更新局部内容**

实际使用的时候使用的难度比较高，我们下面是用的Axios是对于Ajax的一个封装

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Axios入门程序</title>
</head>
<body>

  <button id="getData">GET</button>
  <button id="postData">POST</button>
  
  <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
  <script>
    //GET请求
    document.querySelector('#getData').onclick = function() {
      axios({
        url:'https://mock.apifox.cn/m1/3083103-0-default/emps/list',
        method:'get'//使用get来获取数据
      }).then(function(res) {
        console.log(res.data);
      }).catch(function(err) {
        console.log(err);
      })
    }
    /*
    其中res的结构：
    res.data        → 真正的业务数据（这里就是文件 1 中的 {"code":1,"msg":"success","data":[…]}）
    res.status      → 200
    res.headers     → 响应头
    是否成功看的时status，为200就能说明是成功过的；
    直接输出data就是对于数据进行输出
    */
    
    //POST请求
    document.querySelector('#postData').onclick = function() {
      axios({
        url:'https://mock.apifox.cn/m1/3083103-0-default/emps/update',
        method:'post'
      }).then(function(res) {
        console.log(res.data);
      }).catch(function(err) {
        console.log(err);
      })
    }
  </script>
</body>
</html>
```

在后面我们使用的get请求模块的数据块就使用我们使用的模板





