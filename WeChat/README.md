# 使用vue开发京东和微信

> A Vue.js project WeChat

## 建立 安装

``` bash
# 安装配置文件
npm install

# 运行程序
npm run dev

# 打包发布
npm run build

# 运行情况分析报告
npm run build --report
```
## 运行代码所需的环境和资源

``` bash
# 安装vscode、git、node.js

vscode、git、node.js的安装都可以百度找到，在这里不多做介绍


```
### 欢迎页面
- HelloWorld.vue 页面 主要为登录跳转程序进入的主页
![Image text](https://raw.githubusercontent.com/DempseyLao/pictures/master/index.png)

### 前端JD实现的功能
- newcomponent/newcomponents/jingdong.vue 京东登陆页面
- 京东页面布局
- 京东扫码、输入选择切换
- 扫码（二维码）定时失效
- 输入框规则限制正则表达式、（限制与显示效果）
### 前端WeChat实现的功能
``` bash
# 前端的数据用easy_mock模拟，以接口api方式配合axios、vue-resource以方便动态数据获取和动态功能实现

vscode、git、node.js的安装都可以百度找到，在这里不多做介绍

```


#### Bottom.vue 
  底部导航实现路由跳转、导航选中状态
  ``` js
  在各个主页面中，使用es6语法 import bottomComponent from './Bottom.vue' 配合引用 <bottomComponent></bottomComponent>
  ```  
#### head_top.vue
  头部导航、搜索栏和快捷功能
  ``` js
  在各个页面中，使用es6语法 import headComponent from './head_top.vue' 配合引用<headComponent></headComponent>
  ``` 
#### wechat.vue
  微信模块的主页主要实现，信息加载，好友数据显示，屏幕滑动指令（上滑加载小程序功能模块）下滑关闭，
  
  
  ``` js
  //手指离开屏幕控制滑动事件
 document.addEventListener("touchend", function(e) {
        var endx, endy;
        endx = e.changedTouches[0].pageX;
        endy = e.changedTouches[0].pageY;
        var direction = getDirection(startx, starty, endx, endy);
        switch (direction) {
            case 0:
                break;
            case 1:
			   a=false;
                break;
			case 2:
				a=true
				this.Small_program=true;
                break;
            case 3:
                console.log("向左←");
                break;
            case 4:
                console.log("向右→");
                break;
            default:
        }
	}, false);
  ```  
#### head_top.vue
  头部导航、搜索栏和快捷功能
  ``` js
  在各个页面中，使用es6语法 import headComponent from './head_top.vue' 配合引用<headComponent></headComponent>
  ``` 

## 开发经验与总结

``` bash
# 开发经验与总结在我GitHub laodeyu存储库

 具体地址为：https://github.com/DempseyLao/laodeyu/tree/dev
 
 访问地址选择Dev分支

```
For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
