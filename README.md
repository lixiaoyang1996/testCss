#基于 css3 完成三种动画
<https://github.com/lixiaoyang1996/testCss>

###一、碰撞球动画（雨滴）（这是基于 js 与简单动画 Canvas 完成效果）

* **程序逻辑**:

  * 设置 Canvas 元素的大小和浏览器窗口一样
    * 获取 Canvas 元素
    * 获取浏览器窗口大小
    * 给 Canvas 元素设置大小
    * 当浏览器窗口大小发生变化时，重新设置一下 Canvas 大小
  * 如何利用 Canvas 绘制图形
    * 拿到绘画区域
  * 怎么实现 Canvas 动画
    * 每隔 1/60s 画一张画
    * 每次画的画中间的球位置都不一样
  * 画小球球，200 个

* **核心代码**:
  `function create(num) { for (var i = 0; i < num; i++) { var bubble = new Bubble(); //生出一个小球 bubble.init(); bubble.draw(); aBubble.push(bubble);//每一个新生成的小球球放到数组里 } } create(300); setInterval(function () { canCon.clearRect(0,0,w,h); for(var item of aBubble){ item.move(); // console.log(item); } }, 1000 / 60);`
* **效果展示:**
  ![Aaron Swartz](https://raw.githubusercontent.com/lixiaoyang1996/testCss/master/img/test.png)

###二、旋转太极图（基于简单 css 动画完成效果）

* **程序逻辑:**

  * 构建静态图
  * 利用 transform 和 animation 完成动态效果
  * 规范 css 代码以及完善 HTML 界面符合图标布局

* **核心代码**:

```
  <i class="taichi"></i>

  animation: onepiece 1s infinite alternate linear;
  /*动画:动画名称 播放时长 不停的播 到过来播 匀速播*/

  transform-origin: 100% 50%
  /*提前1s*/

  @keyframes onepiece {
    from {
        /*一开始*/
        transform: scale(0.5);
    }
    to {
        /*最终*/
        transform: scale(1.5);
    }
}
```

* **效果展示:**
  ![Aaron Swartz](https://raw.githubusercontent.com/lixiaoyang1996/testCss/master/img/taiChi.png)

###三、网站列表效果图（基于简单 css 动画完成效果）

* **程序逻辑**:

  * 构建静态图
  * 利用 transform 完成动态效果
  * 规范 css 代码以及完善 HTML 界面符合图标布局

* **核心代码**:

```
.box ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    height: 100%;
}

.box ul li {
    width: 310px;
    height: 185px;
    border: 3px solid gray;
    box-shadow: 0 0 3px #222;
}

.box ul li img {
    width: 100%;
    height: 100%;
}

.box .title {
    width: 100%;
    height: 100%;
    background-color: rgba(255, 255, 255, .5);
    transform: translateY(-180px) scale(0);
    transition: .5s;
}

.box ul li:hover .title {
    transform: translateY(-180px) scale(1);
}
```

* **效果展示:**
  ![Aaron Swartz](https://raw.githubusercontent.com/lixiaoyang1996/testCss/master/img/index.png)

<!-- + **效果展示:**
![Aaron Swartz](https://raw.githubusercontent.com/lixiaoyang1996/testCss/master/img/test.png) -->

###四、3D 曼陀罗导航栏效果图（基于简单 css 动画完成效果）

* **程序逻辑**:

  * 构建静态图
  * 利用 transform 完成动态效果
  * 规范 css 代码以及完善 HTML 界面符合图标布局

* **核心代码**:

```
.menu >li {
    /*选择子元素*/
    float: left;
}

.submenu {
    height: 0;
    perspective: 400px;
    /*镜深*/
}

.submenu li {
    transform: rotateY(90deg);
    transform-style: preserve-3d;
    transition: 0.5s;
}

.menu>li:hover .submenu li {
    transform: rotateY(0deg);
}

.menu li:hover .submenu li:nth-child(1) {
    transition-delay: 0ms;
}

.submenu li:nth-child(8) {
    transition-delay: 0ms;
}
```

* **效果展示:**
  ![Aaron Swartz](https://raw.githubusercontent.com/lixiaoyang1996/testCss/master/img/nav.png)

###四、简单旋转以及定位完成愤怒的小鸟（基于简单 css 动画完成效果）

* **程序逻辑**:

  * 构建静态图
  * 利用 transform 完成动态效果
  * 规范 css 代码以及完善 HTML 界面符合图标布局
  * 合理化标签，用伪类取代标签，实现页面简单化

* **核心代码**

```
    <div class="box">
        <div class="zoom">
        </div>
    </div>

   .box:before {
    content: '';
    position: absolute;
    height: 0px;
    width: 0px;
    top: 0px;
    left: 0px;
    right: 0px;
    bottom: 0px;
    margin: auto;
    border-top: red solid 100px;
    border-left: red solid 100px;
    border-right: transparent solid 100px;
    border-bottom: transparent solid 100px;
    border-radius: 50%;
    transition: .5s;
}

    .box:hover:before {
    transform: rotate(180deg);
}
```

* **效果展示**
  ![Aaron Swartz](https://raw.githubusercontent.com/lixiaoyang1996/testCss/master/bird.png)
