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
``` js
- Bottom.vue 底部导航实现路由跳转、导航选中状态 
  在各个主页面中，使用es6语法 import bottomComponent from './Bottom.vue' 配合引用共同组件

``` 

## 开发经验与总结

``` bash
# 开发经验与总结在我GitHub laodeyu存储库

 具体地址为：https://github.com/DempseyLao/laodeyu/tree/dev
 
 访问地址选择Dev分支

```
For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
