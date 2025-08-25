# [JavaWeb]()

## HTML+CSS

### 基本结构

```html
<html>
     <head>
          <title>HTML 快速入门</title>
     </head>
     <body>
                
     </body>
</html>
```

类似于前面使用的环境配置

**css样式**：CSS（层叠样式表，Cascading Style Sheets）是**描述 HTML / XML 等结构化文档如何呈现**的一门声明式语言。它把“内容”与“表现”分离，让我们用极少的代码就能批量**控制页面颜色、布局、字体、动画等视觉效果**。

![image-20250818154135401](C:\Users\23816\AppData\Roaming\Typora\typora-user-images\image-20250818154135401.png)

### css样式的使用

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章</title>
  <!-- 2. 内部样式 -->
  <style>
    .publish-date {
      color: #b2b2b2;
    }
  </style>
  <!-- 3. 外部样式 -->
  <!-- <link rel="stylesheet" href="css/news.css"> -->
</head>
<body>

  <!-- 定义网页标题, 标题内容： 【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章 -->
  <h1 id="title">【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章</h1>
  
  <!-- 定义一个超链接, 链接地址：https://news.cctv.com/, 链接内容：央视网 -->
  <a href="https://news.cctv.com/" target="_blank">央视网</a>

  <!-- 1. 行内样式 -->
  <!-- <span style="color: #b2b2b2;">2024年05月15日 20:07</span> -->

  <span class="publish-date">2024年05月15日 20:07</span>

</body>
</html>
```

**CSS选择器**：指出应用css样式的是哪一类的元素

**常用标签**：对于html文件中要实现的功能进行标注：

![image-20250818154433468](C:\Users\23816\AppData\Roaming\Typora\typora-user-images\image-20250818154433468.png)

- `<video><img>`在其后面配置其他信息：` <video src="video/news.mp4" controls  width="80%"></video>`
- `<br>`表示进行换行
- `<p><b><u><i><s>`需要前后有对应`</p>`的出现。用对于其中所夹得部分进行格式的设置

### 直接设置标签

下面来看一个比较完整的例子

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章</title>
  <style>
    .publish-date {
      color: #b2b2b2;
    }
    
    /* 设置超链接取消下划线效果 */
    a {
      text-decoration: none;
    }

    /* 设置段落首行缩进 */
    p {
      text-indent: 2em; /* 首行缩进2em */
      line-height: 2; /* 行高2倍 */
    }

    /* 新增样式 */
    .news-content {
      width: 70%; /* 宽度占70% */
      margin: 0 auto; /* 横向居中 */
    }
  </style>
</head>
<body>
    <!-- 包裹新闻内容的容器 -->
    <div class="news-content">
      <!-- 定义网页标题, 标题内容： 【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章 -->
      <h1 id="title">【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章</h1>
      
      <!-- 定义一个超链接, 链接地址：https://news.cctv.com/, 链接内容：央视网 -->
      <a href="https://news.cctv.com/" target="_blank" >央视网</a>

      <span class="publish-date">2024年05月15日 20:07</span>
      <br>
      <br>

      <!-- 定义一个视频, video/news.mp4 -->
      <video src="video/news.mp4" controls width="100%"></video>
      <p>
        <strong>央视网消息</strong>（新闻联播）：作为共抓长江大保护的标志性工程，长江十年禁渔今年进入第四年。总书记指出，长江禁渔是为全局计、为子孙谋的重要决策。牢记总书记嘱托，沿江省市持续推进长江水生生物多样性恢复，努力保障退捕渔民就业生活。这段时间，记者深入长江两岸，记录下禁渔工作取得的重要阶段性成效和广大干部群众坚定不移推进长江十年禁渔的扎实行动。
      </p>
      <p>
        行走在长江沿线，科研人员发现很多可喜现象。
      </p>
      <!-- 定义一张图片, img/1.gif -->
      <img src="img/1.gif" alt=""  width="100%">
      <p>
        在长江南源，一处小头裸裂尻鱼新的栖息地被发现，鱼的数量大约超3万尾，为水生态保护提供了珍贵数据。
      </p>
      <p>
        在长江中游，追踪显示，人工增殖放流的中华鲟成功入海率已经从45%左右提升至60%以上；鄱阳湖鱼类小型化、低龄化趋势得到遏制，栖息地生存环境得以改善。
      </p>
      <p>
        在长江下游，今年3月起，南京秦淮河入江口首次出现野生中华绒螯蟹大规模洄游现象，种群数量明显增加。
      </p>
      <img src="img/2.jpg"  width="100%">
      <p>
        水生生物资源恢复向好，见证了长江十年禁渔三年多来的阶段性成果。
      </p>
      <p>
        实施长江十年禁渔，是以同志为核心的党中央从中华民族长远利益出发作出的重要决策。党的十八大以来，总书记多次深入长江沿线考察调研，详细了解长江十年禁渔的实施情况，他指出，要坚定推进长江十年禁渔，巩固好已经取得的成果。
      </p>
      <img src="img/3.jpg"  width="100%">
      <p>
        按照部署，自2021年1月1日起，在长江干流、大型通江湖泊、重要支流和长江口部分海域实行为期十年的禁渔，常年禁止天然渔业资源的生产性捕捞。禁渔三年多来，相关评估显示，长江干流和鄱阳湖、洞庭湖水生生物完整性指数由禁渔前最差的“无鱼”提升了两个等级。2022年，长江江豚数量达到1249头，实现历史性止跌回升。长江干流水质连续4年全线保持Ⅱ类。
      </p>
      <p>
        实施长江十年禁渔，解决好渔民上岸后的生产生活问题，禁渔才有稳定扎实的社会基础。
      </p>
      <img src="img/4.jpg"  width="100%">
      <p>
        安徽退捕转产的3万多名渔民，在政府的引导下接受就业培训。在当涂县，免费学习养殖技术，养殖生态螃蟹成了退捕渔民的新选择。
      </p>
      <p>
        在拥有洞庭湖超六成水域的湖南岳阳，政府帮扶上岸渔民建起养殖场，发展风干鱼产业，还带领他们学习直播带货，拓宽销路。
      </p>
      <p>
        在渔民退捕上岸的鄱阳湖棠荫岛，当地在继续保护好生态的前提下，正探索规划利用独特的自然资源发展旅游产业。禁渔三年多来，有关部门对23.1万退捕渔民逐一建档立卡，多渠道提升就业、社保水平。
      </p>
      <img src="img/5.jpg"  width="100%">
      <p>
        长江十年禁渔实施以来，沿江省市合力攻坚、久久为功，长江大保护不断向纵深推进，持续巩固禁渔成果。下一步，沿江省市还将加强水生生物重要栖息地修复，建立退捕渔民动态精准帮扶服务，完善跨区域、跨部门执法合作机制，确保一江清水绵延后世、惠泽人民。
      </p>
      <img src="img/6.jpg" >
    </div>
</body>
</html>
```

其中我们可以见到两种前面没有谈到的对于格式进行确认的方法

```html
    /* 设置超链接取消下划线效果 */
<style>
	a {
      text-decoration: none;
    }

     /* 设置段落首行缩进 */
    p {
      text-indent: 2em; /* 首行缩进2em */
      line-height: 2; /* 行高2倍 */
    }
    
    /* 新增样式 */
    .news-content {
      width: 70%; /* 宽度占70% */
      margin: 0 auto; /* 横向居中 */
    }	
</style>
    <div class="news-content">
        
	</div>
	

```

在进行配置的时候我们是对于使用的**标签**进行设置，也就是说之后这些标签覆盖的部分都会更改（本来我们就是使用`<p>`来对于段落进行设置，我们提前对于这些标签进行修改可以完成在对应部分的配置）

另外一种方法是我们使用样式也就是设定一个样式的模样之后再在后面使用。其中`.news-content`就是我们设置的样式的名称；配合后面的`<div class="news-content"></div>`我们可以选择一整块的数据从而完成对于一整块的数据进行设置



- `<div>`标签：
  - 一行只显示一个（独占一行）
  - 宽度默认是父元素的宽度，高度默认由内容撑开
  - 可以设置宽高（width、height）
- `<span>`标签：
  - 一行可以显示多个
  - 宽度和高度默认由内容撑开
  - 不可以设置宽高（width、height）



### flex布局

了解上面的知识之后我们便可以开始使用AI辅助我们完成相关的设置工作
其中我们常常会在上面使用flex布局来进行处理。

- flex是flexible Box的缩写，意为"弹性布局"。采用flex布局的元素，称为Flex容器（container），它的所有子元素自动成为容器成员，称为Flex项目（item）。
- 通过给父容器添加flex属性,来控制子元素的位置和排列方式。



### 表单

- 表单场景: 表单就是在网页中负责数据采集功能的，如：注册、登录的表单。 
- 表单标签: `<form>`
- 表单属性:
  - `action`: 规定表单提交时，向何处发送表单数据，表单提交的URL。
  - `method`: 规定用于发送表单数据的方式，常见为： GET、POST。
    - `GET`：表单数据是拼接在url后面的， 如： xxxxxxxxxxx?username=Tom&age=12，url中能携带的表单数据大小是有限制的。
    - `POST`： 表单数据是在请求体（消息体）中携带的，大小没有限制。
- 表单项标签: 不同类型的input元素、下拉列表、文本域等。
  - `input`: 定义表单项，通过type属性控制输入形式
  - `select`: 定义下拉列表
  - `textarea`: 定义文本域

![image-20250819174133693](C:\Users\23816\AppData\Roaming\Typora\typora-user-images\image-20250819174133693.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML-表单项标签</title>
</head>
<body>

<!-- value: 表单项提交的值 -->
<form action="/save" method="post">
     姓名: <input type="text" name="name"> <br><br>

     密码: <input type="password" name="password"> <br><br> 

     性别: <input type="radio" name="gender" value="1"> 男
          <label><input type="radio" name="gender" value="2"> 女 </label> <br><br>
     
     爱好: <label><input type="checkbox" name="hobby" value="java"> java </label>
          <label><input type="checkbox" name="hobby" value="game"> game </label>
          <label><input type="checkbox" name="hobby" value="sing"> sing </label> <br><br>
     
     图像: <input type="file" name="image">  <br><br>

     生日: <input type="date" name="birthday"> <br><br>

     时间: <input type="time" name="time"> <br><br>

     日期时间: <input type="datetime-local" name="datetime"> <br><br>

     学历: <select name="degree">
               <option value="">----------- 请选择 -----------</option>
               <option value="1">大专</option>
               <option value="2">本科</option>
               <option value="3">硕士</option>
               <option value="4">博士</option>
          </select>  <br><br>

     描述: <textarea name="description" cols="30" rows="10"></textarea>  <br><br>
     
     <input type="hidden" name="id" value="1">

     <!-- 表单常见按钮 -->
     <input type="button" value="按钮">
     <input type="reset" value="重置"> 
     <input type="submit" value="提交">   
     <br>
</form>

</body>
</html>
```

## 
