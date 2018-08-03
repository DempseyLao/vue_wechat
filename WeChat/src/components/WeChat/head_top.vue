<template>
<div id="head_top" >
    <div class="head_top">
			<div class="" style="float: left;">
				<img src="../../assets/wechat/WeChat.png"/>
			</div>
			<div id="" style="float: right;">				
				<img src="../../assets/wechat/search.png"  v-on:click="search()"/>
				<img src="../../assets/wechat/add.png" v-on:click="add()"/>
			</div>
		</div>
	<div v-show="top_add" class="head_posit" >
            	<div class="has">
            		<img src="../../assets/wechat/head_tok.png"/>
            	</div>
            	<div class="has">
            		<img src="../../assets/wechat/head_add.png"/>
            	</div>
            	<div class="has">
            		<img src="../../assets/wechat/head_s.png"/>
            	</div>
            	<div class="has">
            		<img src="../../assets/wechat/head_pay.png"/>
            	</div>
            	<div class="has">
            		<img src="../../assets/wechat/head_help.png"/>
            	</div>
            </div>	
 </div> 
</template>
<script>
export default {
    data(){
        return{
          top_add:false
        } 
    },
     methods:{
          add:function(){
                	this.top_add = !this.top_add
				},
		 search(){
			  this.$router.push({path:"/search"})
		 }
		  	
		   
	   
    },
	
}
</script>
<style>
	.head_top {
			background-color: #303030;
			background-size: auto;
			width: 100%;
			height: 50px;
			position: fixed;
			top: 0;
			/**距离底部为0*/
			left: 0;
			z-index: 1;
			
		}
	.has{
			border-bottom: 1px solid #2B2C30;
		}
	.head_posit{
		height: 252px;
		position: fixed;
		top: 50px;
		right:15px;
		width: 208px;
		background-color:#393A3F ;
		text-align: left
	}
</style>


