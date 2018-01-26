#基于css3完成三种动画
<https://github.com/lixiaoyang1996/testCss>

###一、碰撞球动画（雨滴）（这是基于js与简单动画Canvas完成效果）
**程序逻辑**:
        1、设置Canvas元素的大小和浏览器窗口一样
           1.1:获取Canvas元素
            1.2:获取浏览器窗口大小
            1.3:给Canvas元素设置大小
            1.4:当浏览器窗口大小发生变化时，重新设置一下Canvas大小
        2、如何利用Canvas绘制图形
            2.1:拿到绘画区域
        3、怎么实现Canvas动画
            3.1:每隔1/60s画一张画
            3.2:每次画的画中间的球位置都不一样
        4、画小球球，200个

**核心代码**:
        ```
        function create(num) {
            for (var i = 0; i < num; i++) {
                var bubble = new Bubble(); //生出一个小球
                bubble.init();
                bubble.draw();
                aBubble.push(bubble);//每一个新生成的小球球放到数组里
            }
        }
        create(300);
        setInterval(function () {
            canCon.clearRect(0,0,w,h);
            for(var item of aBubble){
                item.move();
                // console.log(item);
            }
        }, 1000 / 60);
        ```
        
**效果展示:**
![Aaron Swartz](https://raw.githubusercontent.com/lixiaoyang1996/testCss/master/img/test.png)



###二、旋转太极图（基于简单css动画完成效果）
**程序逻辑**:
1、构建静态图
2、利用transform和animation完成动态效果
3、规范css代码以及完善HTML界面符合图标布局

**核心代码**:
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
**效果展示:**
![Aaron Swartz](https://raw.githubusercontent.com/lixiaoyang1996/testCss/master/img/taiChi.png)

###三、网站列表效果图（基于简单css动画完成效果）
**程序逻辑**:
1、构建静态图
2、利用transform完成动态效果
3、规范css代码以及完善HTML界面符合图标布局

**核心代码**:
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
**效果展示:**
![Aaron Swartz](https://raw.githubusercontent.com/lixiaoyang1996/testCss/master/img/index.png)




