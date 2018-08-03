<template>
    <div id="my" class="my">
        <headComponent ></headComponent>
        <div style="margin-top:-10px;height:1px"></div>
        <div class="div_s1" >
				<div class="div_s_con1" >
					<div class="div_s_con11"  >
						<img src="../../assets/wechat/my_img.png"  />
					</div>
					<div class="div_s_con21" >
						<div id="" class="div_s_con2_font1">
							德瑜
						</div>
						<div id="" class="div_s_con2_font21" >
							微信号:laodeyu705291963
						</div>
					</div>
					<div class="div_s_con31">
						<img src="../../assets/wechat/my_code.png"/>
					</div>
					
				</div>
			</div>
			<div class="div_s01" v-on:click="wallet()">
				<div class="">
					<img src="../../assets/wechat/my_q.png" />
				</div>
			</div>
			<div class="div_s11" >
				<div class="">
					<img src="../../assets/wechat/my_s.png" />
				</div>
				<hr >
				<div class="">
					<img src="../../assets/wechat/my_x.png" />
				</div>
				<hr >
				<div class="">
					<img src="../../assets/wechat/my_k.png" />
				</div>
				<hr >
				<div class="">
					<img src="../../assets/wechat/my_b.png" />
				</div>
			</div>
			<div class="div_s01" >
				<div class="">
					<img src="../../assets/wechat/my_setting.png" />
				</div>
			</div>
         <bottomComponent></bottomComponent>
        </div>
    
</template>
<script>
import bottomComponent from './Bottom.vue'
import headComponent from './head_top.vue'
export default {
    data(){
        return{
        } 
    },
    components: {
	  bottomComponent,
	  headComponent
    } ,
     methods:{
      wallet(){
		  this.$router.push({path:"/wallet"})
	  }
			
		   
	   
    },
	
}
</script>
<style>
         	* {
				padding: 0px;
				margin: 0px;
				border: 0px;
			}
			
			.my {
				background-color: #EBEBEB;
				height: 600px;
				text-align: left;
			}
			
			.div_s1 {
				height: 85px;
				margin-top: 20px;
				background-color: white;
			}
			
			.div_s01 {
				height: 50px;
				margin-top: 20px;
				background-color: white;
			}
			
			.div_s11 {
				height: 198px;
				margin-top: 20px;
				background-color: white;
			}
			
			.div_s_con1 {
				margin: 10px 10px 10px 15px;
			}
			
			.div_s_con11 {
				float: left;
				margin-right: 15px;
				padding-top: 8px;
			}
			
			.div_s_con21 {
				float: left;
				margin: 20px 0px 20px 1px;
			}
			
			.div_s_con2_font1 {
				font-family: '黑体';
				font-size: 17px;
			}
			
			.div_s_con2_font21 {
				margin-top: 10px;
				font-family: '黑体';
				font-size: 15px;
				color: #A0A0A0;
			}
			
			.div_s_con31 {
				float: right;
				margin-top: 30px;
			}
			
			hr {
				border-bottom: 1px solid #EEEEEE;
				margin: 0px 16px 0px 16px;
			}
</style>


