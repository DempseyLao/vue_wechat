<template>
    <div id="all">
		
        <headComponent></headComponent>
    <ul class=""  style="position: fixed;right: 0;top: 45px;z-index: 1;margin: 4px;list-style-type:none;text-align: center;height: 100%;font-family: 黑体;font-size: 16px;">
				<li  v-for="(num,index) in list" :key="index" v-on:click="num_test_list(index)">
					{{num.name}}
				</li>
			</ul>	
			
			<div class=" public_all d_jump" id="public">
				<div class="public_out">
					<div id="" class="public_img">
						<img src="../../assets/wechat/new_friend.png" />
					</div>
					<div id="" class="public_name">
						新的朋友
					</div>
				</div>
				<div class="public_out">
					<div id="" class="public_img">
						<img src="../../assets/wechat/Group_chat.png" />
					</div>
					<div id="" class="public_name">
						群聊
					</div>
				</div>
				<div class="public_out">
					<div id="" class="public_img">
						<img src="../../assets/wechat/label.png" />
					</div>
					<div id="" class="public_name">
						标签
					</div>
				</div>
				<div class="public_out">
					<div id="" class="public_img">
						<img src="../../assets/wechat/Public_number.png" />
					</div>
					<div id="" class="public_name">
						公众号
					</div>
				</div>
			</div>
			
				<Operate></Operate>
				 
				<div style="height:60px"></div>
            <bottomComponent></bottomComponent>
    </div>
    
</template>
<script>

import bottomComponent from './Bottom.vue'
import headComponent from './head_top.vue'
export default {
	name:'name_list',
    data(){
        return{
         list: [ {name:'↑'}, {name:'A'},{name:'B'},{name: 'C'}, {name:'D'},{name:'E'}, {name:'F'}, {name:'G' },{name:'H'},{name: 'I'},{name:'J'},{name:'K'},{name: 'L'},{name: 'M'},{name: 'N'},{name: 'O'},{name:'P'},{name:'Q'}, {name:'R'}, {name:'S'},{name: 'T'}, {name:'U'}, {name:'V'},{name:'W'}, {name:'X'},{name:'Y'}, {name:'Z'},{name: '#'}]    
		
        ,
		index:-1,
		
        } 
    },
    components: {
		 Operate: function(resolve) {
				require(['@/components/wechat/list.vue'], resolve)
			},
	  bottomComponent,
	  headComponent,
	 
    } ,
     methods:{
       num_test_list(index){
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

</script>
<style>
* {
				padding: 0px;
				margin: 0px;
				border: 0px;
				font-family: 黑体;
				
			}
			
			.public_out {
				margin: 8px 18px 8px 14px;
				height: 45px;
				border-bottom: 1px solid #EEEEEE;
				
			}
			.public_img {
				float: left;
				margin-right: 14px;
			}
			
			.public_name {
				
				padding-top: 10px;
			}
			
			.public_all {
				margin-top: 60px;
				height: 205px;
				text-align: left
			}
			.list_sty{
        height:20px;padding-left:15px;text-align: left;background-color:#EBEBEB ;color: #A5A5A5;font-size: 12px;
			}
</style>


