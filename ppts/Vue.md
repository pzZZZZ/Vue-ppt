title: Vue2技术分享
speaker: pzzz
url: https://github.com/ksky521/nodeppt
transition: slide1
files: /js/demo.js,/css/demo.css,/js/zoom.js
theme: moon
usemathjax: yes

[slide]
<h1 style="text-align:center"><img src="https://cn.vuejs.org/images/logo.png" style="width:215px;height:215px;"></h1>

# Vue---渐进式JavaScript 框架
<small>分享者:pzzz</small>
[slide]

[magic data-transition="horizontal3d"]
# 为什么选择Vue
-----
* 轻量级：*20kb* min+gzip 运行大小 {:&.bounceIn}
* Vue.js 不仅简单、容易上手、配置设施齐全，同时拥有中文文档。
* *组件化*开发便于复用
* 模版语法便于控制
* 生态完善
* 双向数据绑定
* vue 作者会上**知乎**，有先天优势。
====

## 社区状况
-----
<img src="/img/duibi.jpg">
====
## 有哪些团队使用了Vue?
-----
* 趣店集团，饿了么，异乡好居，稀土掘金，凡普信贷，苏宁易购，天猫团队，小米 {:&.zoomIn}
* 途牛，滴滴打车，微博，头条 等前端团队都在使用Vue.js。


[/magic]

[slide style="background-image:url('/img/bg1.png')"]
# Vue的正确使用姿势？
> Vue.js+Vuex+Vue-resource/axios/what-fetch+Vue-router+webpack+es6+less/scss/styles/postcss

* 这么多？都是什么？ {:&.moveIn}
* Vue.js 不多解释啦 该框架的核心部分
* Vuex 是一个专为 Vue.js 应用程序开发的状态管理模式。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。
* vue-resource/axios/what-fetch 对Web请求和处理响应的插件。
* vue-router 对SPA页面路由进行管理的插件。
* webpack 模块打包机：它做的事情是，分析你的项目结构，找到JavaScript模块以及其它的一些浏览器不能直接运行的拓展语言（Scss，TypeScript等），并将其打包为合适的格式以供浏览器使用。
* es6 ES2015提供了很多新的API和接口更方便进行开发
* less/scss/styles/postcss css预处理工具
[slide]
# Vue项目的目录结构
## 一般目录结构
```
    ├── README.md                       项目介绍
    ├── index.html                      入口页面
    ├── build                           构建脚本目录
    │   ├── build-server.js                 运行本地构建服务器，可以访问构建后的页面
    │   ├── build.js                        生产环境构建脚本
    │   ├── dev-client.js                   开发服务器热重载脚本，主要用来实现开发阶段的页面自动刷新
    │   ├── dev-server.js                   运行本地开发服务器
    │   ├── utils.js                        构建相关工具方法
    │   ├── webpack.base.conf.js            wabpack基础配置
    │   ├── webpack.dev.conf.js             wabpack开发环境配置
    │   └── webpack.prod.conf.js            wabpack生产环境配置
    ├── config                          项目配置
    │   ├── dev.env.js                      开发环境变量
    │   ├── index.js                        项目配置文件
    │   ├── prod.env.js                     生产环境变量
    │   └── test.env.js                     测试环境变量
    ├── mock                            mock数据目录
    │   └── hello.js
    ├── package.json                    npm包配置文件，里面定义了项目的npm脚本，依赖包等信息
    ├── src                             源码目录    
    │   ├── main.js                         入口js文件
    │   ├── app.vue                         根组件
    │   ├── components                      公共组件目录
    │   │   └── title.vue
    │   ├── assets                          资源目录，这里的资源会被wabpack构建
    │   │   └── images
    │   │       └── logo.png
    │   ├── routes                          前端路由配置
    │   │   └── index.js
    │   ├── store                           应用级数据配置（state）
    │   │   └── index.js
    │   └── views                           页面目录
    │       ├── hello.vue
    │       └── notfound.vue
    ├── static                          纯静态资源，不会被wabpack构建。

```
[slide]
# 如何快速构建项目？
> 引入Vue-cli工具[快速构建Vue项目的工具]
<img src="/img/vue-cli.png">

[slide]


[magic data-transition="horizontal3d"]
## 什么是SPA页面 ？
-----
* 可以在页面切换间平滑过渡，增加Loading动画 {:&.zoomIn}
* 可以在各个页面间传递数据，不依赖URL。
* 可以选择性的保留状态，如音乐网站，切换页面时不会停止播放歌曲。
* 所有的标签都可以用来跳转，不仅仅是a标签。
* 避免了公共JS的反复执行，如无需在各个页面打开时都判断是否登录过等等。
* 减少了请求体积，节省流量，加快页面响应速度。
====

## 如何实现？
-----

> 使用Vue-router管理单页面路由

> Vue.js的路由管理模块

====
[/magic]
[slide]
<iframe data-src="https://router.vuejs.org/zh-cn/" src="about:blank;"></iframe>

# 使用文档



[slide]

# 样式展示 {:&.flexbox.vleft}
> nodeppt 让每个人都爱上做分享！



[slide]
## 基本语法指南
----

<pre><code class="markdown">/* 先写总的配置 */
title: 这是title，网页名称
speaker: 演讲者名称
url: https://github.com/ksky521/nodeppt
transition: 全局转场动效
files: 引入的js和css文件，多个以半角逗号隔开
theme: 皮肤样式
highlightStyle: 代码高亮样式，默认monokai_sublime
usemathjax: yes 启用MathJax渲染公式

/* 以&#91;slide&#93; 隔开每个ppt页面 */
&#91;slide&#93;
## 二级标题
这里写内容即可

&#91;slide&#93;
...
</code>
</pre>



[slide style="background-image:url('/img/bg1.png')"]

# 支持添加背景图片 {:&.flexbox.vleft}

使用方法：&#91;slide style="background-image:url('/img/bg1.png')"&#93;

完全style写法，更加灵活，视频背景、repeat背景更不在话下

[slide]
## 使用LaTex公式：
$$ x = {-b \pm \sqrt{b^2-4ac} \over 2a}.    s = ut + \frac{1}{2}at^2 $$
矩阵：\\( x = {\begin{bmatrix} 1 & 2 & 3 \\\\ 4 & 5 & 6 \end{bmatrix}}  \\)

[slide]
## 支持.class/#id/自定义属性样式
----

```html
使用：.class{:.class}
使用：#id{:#id}
组合使用：{:.class.class2 width="200px"}
父元素样式使用&：{:&.class}
```

[slide]

## 主页面样式
### ----是上下分界线
----

nodeppt是基于nodejs写的支持 **Markdown!** 语法的网页PPT

nodeppt：https://github.com/ksky521/nodeppt



[slide]
## 表格示例
### 市面上主要的css预处理器：Less\Sass\Stylus
---
| Less | Sass | Stylus
:-------|:------:|-------:|--------
环境 |js/nodejs | Ruby(这列右对齐) | nodejs(高亮) {:.highlight}
扩展名 | .less | .scss/.sass | .styl
特点 | 老牌，用户多，支持js解析 | 功能全，有成型框架，发展快 | 语法多样，小众
案例/框架 | [Bootstrap](http://getbootstrap.com/) | [Compass](http://beta.compass-style.org) [Bootstrap](http://getbootstrap.com/css/#sass) [Foundation](http://foundation.zurb.com/) [Bourbon](http://bourbon.io) [Base.Sass](https://github.com/jsw0528/base.sass) |


[slide]
## text
-----

<span class="text-danger">.text-danger</span> <span class="text-success">.text-sucess</span><span class="text-primary">.text-primary</span>

<span class="text-warning">.text-warning</span><span class="text-info">.text-info</span><span class="text-white">.text-white</span><span class="text-dark">.text-dark</span>


<span class="blue">.blue</span><span class="blue2">.blue2</span><span class="blue3">.blue3</span><span class="gray">.gray</span><span class="gray2">.gray2</span><span class="gray3">.gray3</span>

<span class="red">.red</span><span class="red2">.red2</span><span class="red3">.red3</span>

<span class="yellow">.yellow</span><span class="yellow2">.yellow2</span><span class="yellow3">.yellow3</span><span class="green">.green</span><span class="green2">.green2</span><span class="green3">.green3</span>

[slide]
## label and link
<span class="label label-primary">.label.label-primary</span><span class="label label-warning">.label.label-warning</span><span class="label label-danger">.label.label-danger</span><span class="label label-default">.label.label-default</span><span class="label label-success">.label.label-success</span><span class="label label-info">.label.label-info</span>

<a href="#">link style</a> <mark>mark</mark>

[slide]
## blockquote
----

> nodeppt可能是迄今为止最好用的web presentation <small>三水清</small>


下面是另外一种样式

> 这是一个class是：pull-right的blockquote <small>small一下</small> {:&.pull-right}

[slide]
## buttons
----

<button class="btn btn-default">.btn .btn-default</button>  <button class="btn btn-primary">.btn.btn-lg.btn-primary</button> <button class="btn btn-warning">.btn.btn-waring</button> <button class="btn btn-success">.btn.btn-success</button> <button class="btn btn-danger">.btn.btn-danger</button>

<button class="btn btn-lg btn-default">.btn.btn-lg.btn-default</button> <button class="btn btn-xs btn-success">.btn.btn-xs.btn-success</button> <button class="btn btn-sm btn-primary">.btn.btn-sm.btn-primary</button> <button class="btn btn-rounded btn-warning">.btn.btn-rounded.btn-waring</button>  <button class="btn btn-danger" disabled="disabled">disabled.btn.btn-danger</button>


<button class="btn btn-success"><i class="fa fa-share mr5"></i></button>

[slide]
## icons: Font Awesome
------

<i class="fa fa-apple"></i>
<i class="fa fa-android"></i>
<i class="fa fa-github"></i>
<i class="fa fa-google"></i>
<i class="fa fa-linux"></i>
<i class="fa fa-css3"></i>
<i class="fa fa-html5"></i>
<i class="fa fa-usd"></i>
<i class="fa fa-pie-chart"></i>
<i class="fa fa-file-video-o"></i>
<i class="fa fa-cog"></i>


[slide]

## 代码格式化
### 使用 `highlightjs` 进行语法高亮
----
<div class="columns-2">
    <pre><code class="javascript">(function(window, document){
    var a = 1;
    var test = function(){
        var b = 1;
        alert(b);
    };
    //泛数组转换为数组
    function toArray(arrayLike) {
        return [].slice.call(arrayLike);
    }
}(window, document));
    </code></pre>
    <pre><code class="javascript">(function(window, document){
    var a = 1;
    var test = function(){
        var b = 1;
        alert(b);
    };
    //泛数组转换为数组
    function toArray(arrayLike) {
        return [].slice.call(arrayLike);
    }
}(window, document));
    </code></pre>
</div>

[slide data-on-enter="testScriptTag"]
## 支持 HTML 和 markdown 语法混编
----

<div class="file-setting">
    <p>这是html</p>
</div>
<p id="css-demo">这是css样式</p>
<p>将html代码直接混编到**markdown**文件中即可</p>

我是js控制的颜色 black {:#testScriptTag}

<script>
    function testScriptTag(){
        document.getElementById('testScriptTag').style.color = 'black';
    }

</script>
<style>
#css-demo{
    color: red;
}
</style>


[slide]
## iframe效果
----
<iframe data-src="http://www.baidu.com" src="about:blank;"></iframe>

[slide]
# 内置多套皮肤

[slide]
## 支持多种皮肤
----

<div class="columns6">
    <a href="?theme=color" class="label-danger">color</a>
    <a href="?theme=blue" class="label-primary">blue</a>
    <a href="?theme=dark" class="label-info">dark</a>
    <a href="?theme=green" class="label-success">green</a>
    <a href="?theme=light" class="label-warning">light</a>
</div>

[slide]
# 多窗口和远程控制演示

[slide]
## 多窗口演示
## 双屏演示不out！
---
本页面网址改成 [url?_multiscreen=1](?_multiscreen=1)，支持多屏演示哦！

跟powderpoint/keynote一样的双屏功能，带有备注信息。

[slide]
# nodeppt动效和转场演示

[slide]
# 第一部分：介绍单页slide内动效

[slide]

[magic data-transition="earthquake"]
## 演示magic标签效果
-----
<div class="columns3">
    <img src="/girl.jpg" height="450">
    <img src="/girl.jpg" height="450">
    <img src="/girl.jpg" height="450">
</div>
========
## 演示earthquake转场效果
-----
<div class="columns4">
    <img src="/girl.jpg" height="320">
    <img src="/girl.jpg" height="320">
    <img src="/girl.jpg" height="320">
    <img src="/girl.jpg" height="320">
</div>
[/magic]


[slide]
[magic data-transition="cover-circle"]
## 换个magic动效效果
----
![](/girl.jpg)
====
![](/girl.jpg)
[/magic]


[slide]
## 动效：fadeIn
----
* 列表支持渐显动效哦 {:&.fadeIn}
    * 使用方法
    * markdown列表第一条加上：{:&.动效类型}
* 动效类型
    * fadeIn
    * rollIn
    * bounceIn
    * moveIn
    * zoomIn

[slide]
## 动效：zoomIn
----
* 列表支持渐显动效哦 {:&.zoomIn}
* 动效类型
    * fadeIn
    * rollIn
    * bounceIn
    * moveIn
    * zoomIn

[slide]
## 动效：bounceIn
----
* 列表支持渐显动效哦 {:&.bounceIn}
* 动效类型
    * fadeIn
    * rollIn
    * bounceIn
    * moveIn
    * zoomIn

[slide]
# nodeppt支持多达20多个转场动效

[slide]
## 20种转场动效随心换
----
 * <a href="?transition=slide">slide</a>/<a href="?transition=slide2">slide2</a>/<a href="?transition=slide3">slide3</a>
 * [newspaper](?transition=newspaper)
 * [glue](?transition=glue)
 * [kontext](?transition=kontext)/[vkontext](?transition=vkontext)
 * [move](?transition=move)/[circle](?transition=circle)
 * [horizontal](?transition=horizontal)/[horizontal3d](?transition=horizontal3d)
 * [vertical3d](?transition=vertical3d)
 * [zoomin](?transition=zoomin)/[zoomout](?transition=zoomout)
 * [cards](?transition=cards)
 * [earthquake](?transition=earthquake)/[pulse](?transition=pulse)/[stick](?transition=stick)...


[slide data-transition="glue"]

## 这是一个glue的动效
----
使用方法（全局设置） 1：

> transition: glue


[slide data-transition="glue"]

## 这是一个glue的动效
----
使用方法 2：

&#91;slide data-transition="glue"&#93;

[slide data-transition="zoomin"]

## 这是一个zoomin的动效
----
使用方法：

&#91;slide data-transition="zoomin"&#93;

[slide data-transition="vertical3d"]

## 这是一个vertical3d的动效
----
使用方法：

&#91;slide data-transition="vertical3d"&#93;

[slide]
# nodeppt快捷键介绍
[slide]
## 快速翻页
----
1. 输入页码，然后enter
2. 使用O键，开启纵览模式，然后翻页

[slide]
## 动效样式强调
----

这段话里面的**加粗**和*em*字体会动效哦~

按下【H】键查看效果


[slide]
## 支持zoom.js
----

增加了zoom.js的支持，在演示过程中使用`alt`+鼠标点击，则点击的地方就开始放大，再次`alt+click`则回复原状

[slide]

## 图片，点击全屏
----

![小萝莉](/girl.jpg "小萝莉")


[slide]

## 图片，禁止全屏
----

<img src="/girl.jpg" class="no-screenfull">

[slide]
[note]
##这里是note

使用n键，才能显示
[/note]
## 使用note笔记
### note笔记是多窗口，或者自己做一些笔记用的
---
按下键盘【N】键测试下note，

markdown语法如下：
```markdown
[note]
这里是note，{ 要换成中括号啊！！
{/note]
```
[slide]

## 使用画笔
### 使用画笔做标记哦~你也可以随便作画啊！
---
按下键盘【P】键：按下鼠标左键，在此处乱花下看看效果。

按下键盘【B/Y/R/G/M】：更换颜色，按下【1~4】：更换粗细

按下键盘【C】键：清空画板


[slide]

## 宽度不够？？
---
按下键盘【W】键，切换到更宽的页面看效果，第二次按键返回

 |less| sass | stylus
:-------|:------:|-------:|--------
环境 |js/nodejs | Ruby(这列右对齐) | nodejs(高亮) {:.highlight}
扩展名 | .less | .sass/.scss | .styl
特点 | 老牌，用户多，支持js解析 | 功能全，有成型框架，发展快 | 语法多样，小众
案例/框架 | [Bootstrap](http://getbootstrap.com/) | [compass](http://compass-style.org) [bourbon](http://bourbon.io) |

[slide]
## 使用overview模式
---
按下键盘【O】键。看下效果。

在overview模式下，方向键下一页，【enter】键进入选中页

或者按下键盘【O】键，退出overview模式



[slide]

# 介绍下nodeppt的函数和事件

[slide]
支持单个slide事件：build/enter/leave/keypress，事件统一在&#91;slide&#93;
中使用`data-on-X`来指定一个全局函数名

* build：当触发下一步操作的时会触发，event具有stop方法
* keypress：在当前页面按键触发，event具有stop方法
* enter/leave：进入/离开 此页面触发的事件，event无stop方法


[slide data-on-leave="outcallback" data-on-enter="incallback" ]
## 使用回调
----

* &#91;slide data-on-leave="fnName"&#93;
    * 进入执行回调incallback函数
* &#91;slide data-on-enter="fnName"&#93;
    * 退出执行outcallback函数

亦可以组合写：

> &#91;slide data-on-leave="foo" data-on-enter="bar"&#93;


<p id="incallback"></p>
<p id="outcallback"></p>

[slide]
## 远程执行函数
----
在多屏和远程模式中，可以使用`proxyFn`来远程执行函数。

```html
<script>
function globalFunc(){
}
</script>
<button onclick="Slide.proxyFn('globalFunc')" class="btn btn-default">远程执行函数</button>
```

<button onclick="Slide.proxyFn('globalFunc','args')" class="btn btn-default">测试远程执行函数</button>
<a href="?_multiscreen=1#33">在多屏中测试远程执行</a>
<script>
    function globalFunc(a){
        alert('proxyFn success: '+a+location.href);
    }
</script>

[slide]

## 更多玩法
---
https://github.com/ksky521/nodeppt

什么？这些功能还不够用？

socket远程控制可以在手机上摇一摇换页哦~

查看项目目录ppts获取更多帮助信息
