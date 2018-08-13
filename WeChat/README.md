# 使用vue开发京东和微信

> A Vue.js project WeChat

## 建立 安装

``` bash
# 建立项目存放文件夹（任意即可）
Git bush here
使用命令Git clone https://github.com/DempseyLao/vue_wechat.git
或者直接下载zip到目录（解压进行下一步）

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
#### index.html 
  单页面应用入口
  
#### main.js 
  主程序进入、全局引用与模块加载
  ``` js
import Vue from 'vue'
import App from './App'
import router from './router'
import axios from 'axios'
// import YDUI from 'vue-ydui';
// import 'vue-ydui/dist/ydui.rem.css';

// Vue.use(YDUI);
Vue.prototype.$ajax = axios
Vue.config.productionTip = false

/* eslint-disable no-new */
new Vue({
  el: '#app',
  router,
  components: { App },
  template: '<App/>'
})
```
#### Bottom.vue 
  底部导航实现路由跳转、导航选中状态
  ``` js
  在各个主页面中，使用es6语法 import bottomComponent from './Bottom.vue' 配合引用 <bottomComponent></bottomComponent>
  ```  
 #### index.js 
  组件引用、路由定义、组件模块名字定义
  ``` js
import Vue from 'vue'
import Router from 'vue-router'
import HelloWorld from '@/components/HelloWorld'
import Hello from '@/components/hello'
import hw from '@/components/newcomponents/jingdong'
import wechat from '@/components/wechat/wechat'
import mail from '@/components/wechat/mail_list'
import find from '@/components/wechat/find'
import my from '@/components/wechat/my'
import search from '@/components/wechat/search'
import chat from '@/components/wechat/chat'
import friend_space from '@/components/wechat/friend_space'
import  VueResource  from 'vue-resource'
import list from '@/components/wechat/list'
import wallet from '@/components/wechat/wallet'
import chat_content from '@/components/wechat/chat_content'
Vue.use(VueResource) 
Vue.use(Router)

export default new Router({
  routes: [
    {
      path: '/',
      name: 'HelloWorld',
      component: HelloWorld
    }
    ,
    {
      path: '/hello',
      name: 'HelloWorld2',
      component: Hello
    }
    ,
    {
      path: '/hw',
      name: 'HelloWorld3',
      component: hw
    }
    ,
    {
      path: '/wechat',
      name: 'wechat',
      component: wechat
    }
    ,
    {
      path: '/mail',
      name: 'mail',
      component: mail
    }
    ,
    {
      path: '/find',
      name: 'find',
      component: find
    }
    ,
    {
      path: '/my',
      name: 'my',
      component: my
    }
    ,
    {
      path: '/search',
      name: 'search',
      component: search
    }
    ,
    {
      path: '/chat/:name',
      name: 'chat',
      component: chat
    }
    
    ,
    {
      path: '/friend_space',
      name: 'friend_space',
      component: friend_space
    }
    ,
    {
      path: '/list',
      name: 'list',
      component: list
    }
    ,
    {
      path: '/wallet',
      name: 'wallet',
      component: wallet
    }
    ,
    {
      path: '/chat_content',
      name: 'chat_content',
      component: chat_content
    }
  ]
})
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
  ``` js
created(){//在页面创建的时候get easy-mock事先第一好的模拟数据 api调用
            this.$http.get('https://www.easy-mock.com/mock/5b5a9004e51b9b054104fa4a/account',{
            }).then(function(data){
				this.account=data.body.account;
				
            },function(res){
                console.log(res.status);
            })     
        },
  ```  
  ``` html
<!-- 利用vue的v-show，v-on， v-for 方法实现上滑下滑显示隐藏小程序模块、点击传参路由跳转、循环遍历信息-->
   	<div id="all">		
		<headComponent></headComponent>
		<div class="Small_program" v-show="Small_program" >
			<div id="" >
				<img src="../../assets/wechat/s1.png"  />
			</div>
			<div id="" >
				<img src="../../assets/wechat/s2.png"/>
			</div>
			<div id="" >
				<img src="../../assets/wechat/s3.png"/>
			</div>
			<div id="" >
				<img src="../../assets/wechat/s4.png"/>
			</div>
		</div>
		<div id="content" v-on:click="Small_program_open(accounts.name,index)"   v-for="(accounts,index) in account">
			<div id="" class="con_out" >
			<div id="" class="margin_div" >
				<div class="left_img" >
					<img v-bind:src="accounts.img"/>
				</div>
				<div class="mid_con" >
					<div id="" class="mid_con_div1" >
						{{accounts.name}}
					</div>
					<div id="" class="mid_con_div2" >
						{{accounts.content}}
					</div>
				</div>
				<div class="right_time" >
					 {{accounts.time}}
				</div>
			</div>
			</div>
		</div>
		<!-- <div  v-for="accounts in account" >{{accounts.name}}</div> -->
		<div style="height:50px"></div>
		<bottomComponent></bottomComponent>
		</div>
  ```  
#### chat.vue
  聊天室组件
  ``` js
 import contents from './chat_content.vue'//引入聊天详细信息模块
export default {
    data(){    //定义数据与绑定
        return{
        chat_title:"",
        add_chat_com:false,
		foot_say:false,
		foot_input:true,
        } 
    },
    components: {
		 contents  //加载模块
    } ,
    mounted(){
      this.chat_title=this.$route.params.name//获取路由传参，绑定到数据（头部名称）
    }
    , methods:{
      comback(){
          this.$router.go(-1)//跳转回上级页面
	  } 
	  ,
	append_other(){
		 this.add_chat_com=!this.add_chat_com
		 this.foot_say=false;
		 this.foot_input=true
	},
	toc(){
		this.foot_say=true;
		this.foot_input=false
	},
	input(){
		this.foot_say=false;
		this.foot_input=true
	}
    },
    beforeCreate: function() {  //页面加载前创建
        document.getElementsByTagName("body")[0].className="all_chat";
    },
    beforeDestroy: function() { //结束前销毁
        document.body.removeAttribute("class","all_chat");
	}
	
}
  ``` 
  
#### chat_content.vue
  聊天室信息内容组件
``` 
涉及到后端数据库设计与传值，具体的解决方案在https://github.com/DempseyLao/laodeyu/tree/dev

文档：https://github.com/DempseyLao/laodeyu/blob/dev/2018%E5%B9%B48%E6%9C%882%E6%97%A5%E6%98%9F%E6%9C%9F%E5%9B%9B.docx

2018年8月2日星期四.docx
```
#### Mail_list.vue
  通讯录组件
``` js
import bottomComponent from './Bottom.vue'
import headComponent from './head_top.vue'
export default {
	name:'name_list',
    data(){
        return{ //定义数组
         list: [ {name:'↑'}, {name:'A'},{name:'B'},{name: 'C'}, {name:'D'},{name:'E'}, {name:'F'}, {name:'G' },{name:'H'},{name: 'I'},{name:'J'},{name:'K'},{name: 'L'},{name: 'M'},{name: 'N'},{name: 'O'},{name:'P'},{name:'Q'}, {name:'R'}, {name:'S'},{name: 'T'}, {name:'U'}, {name:'V'},{name:'W'}, {name:'X'},{name:'Y'}, {name:'Z'},{name: '#'}]    
		
        ,
		index:-1,
		
        } 
    },
    components: {
		 Operate: function(resolve) { //信息通讯录信息按需加载
				require(['@/components/wechat/list.vue'], resolve)
			},
	  bottomComponent,
	  headComponent,
	 
    } ,
     methods:{
       num_test_list(index){  //点击滑动跳转到对应锚点
         // 用 class="d_jump" 添加锚点
        let jump = document.querySelectorAll('.d_jump')
        let total = jump[index].offsetTop-56
        let distance = document.documentElement.scrollTop || document.body.scrollTop
        // 平滑滚动，时长500ms，每10ms一跳，共50跳
        let step = total / 50
        if (total > distance) {
          smoothDown()
        } else {
          let newTotal = distance - total
          step = newTotal / 50
          smoothUp()
        }
        function smoothDown () {
          if (distance < total) {
            distance += step
　　　　　　　document.body.scrollTop = distance
            document.documentElement.scrollTop = distance
            setTimeout(smoothDown, 10)
          } else {
            document.body.scrollTop = total
            document.documentElement.scrollTop = total
          }
        }
        function smoothUp () {
          if (distance > total) {
            distance -= step
　　　　　　　document.body.scrollTop = distance
            document.documentElement.scrollTop = distance
            setTimeout(smoothUp, 10)
          } else {
            document.body.scrollTop = total
            document.documentElement.scrollTop = total
          }
       } 
			
		   
	   }
	},
	mounted: function () {
    this.$nextTick(function () {
      window.addEventListener('scroll', this.onScroll)
		})

  },
	
}
```
#### list.vue
通讯录详细通讯人详细与归类
```html
  <!-- 循环出排序信息（a-z#） -->
   v-for="(num,index) in list2" :key="index"   
  <!--循环加载通讯录个人信息并归类（调用转化英文和截取字符串方法） -->
   v-for="(num2,index) in list_TEST" :key="index" v-if="num.name==chineseToPinYin(num2.name)
```
#### find.vue 、friend_space.vue、my.vue、wallet.vue、search.vue
#### 等vue组件不需要模拟数据大部分为静态页面配合一些简单的方法这里不多做介绍，
#### 其中朋友圈信息、我的钱包等功能~需要在后期v2.0版本更新补齐
## 开发经验与总结

``` bash
# 开发经验与总结在我GitHub laodeyu存储库

 具体地址为：https://github.com/DempseyLao/laodeyu/tree/dev
 
 访问地址选择Dev分支

```
For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
