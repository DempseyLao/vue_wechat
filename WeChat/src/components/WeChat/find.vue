<template>
    <div id="find" class="find">
    <headComponent ></headComponent>
            <div style="margin-top:-10px;height:1px"></div>
			<div class="div_s"   v-on:click="friend_space()">
				<div class="" style="float: left;">
					<img src="../../assets/wechat/f_friend.png" />
				</div>
			</div>
			<div class="div_s1_find" >
				<div class="" >
					<img src="../../assets/wechat/f_s.png" />
				</div>
                <hr >
				<div class="" >
					<img src="../../assets/wechat/f_y.png" />
				</div>
			</div>
			<div class="div_s1_find" >
				<div class="">
					<img src="../../assets/wechat/f_k.png" />
				</div>
				<hr >
				<div class="">
					<img src="../../assets/wechat/f_su.png" />
				</div>
			</div>
			<div class="div_s1_find" >
				<div class="">
					<img src="../../assets/wechat/f_o.png" />
				</div>
				<hr >
				<div class="">
					<img src="../../assets/wechat/f_p.png" />
				</div>
			</div>
			<div class="div_s1_find" >
				<div class="">
					<img src="../../assets/wechat/f_g.png" />
				</div>
				<hr >
				<div class="">
					<div id="" style="float: left;">
						<img src="../../assets/wechat/f_yx.png" />
					</div>
					<div class="" style="float: right;">
						<img src="../../assets/wechat/f_yx_inf.png" />
					</div>

				</div>
			</div>
			<div class="div_s" >
				<div class="">
					<img src="../../assets/wechat/f_x.png" />
				</div>
			</div>
			<div cl
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
      friend_space(){
		  this.$router.push({path:"/friend_space"})
	  }
			
		   
	   
    },
	
}
</script>
<style>
            * {
				padding: 0px;
				margin: 0px ;
				border: 0px;
			}
			
			.find {
				background-color: #EBEBEB;
				height: 750px;
                text-align: left
			}
			
			.div_s {
				height: 50px;
				margin-top: 20px;
				background-color: white;
               
                
			}
			
			.div_s1_find {
				height: 100px;
				margin-top: 20px;
				background-color: white;
                
			}
			
			hr {
				border-bottom: 1px solid #EEEEEE;
				margin: 0px 16px 0px 16px;
                
			} 
            
</style>


