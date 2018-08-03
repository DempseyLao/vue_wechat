<template>
   <div id="alla" class="space" >
     <div class="space_headtop">
			<div class="" style="float: left;">
				<img src="../../assets/wechat/white_back.png"  v-on:click="comback()"/>
			</div>
			<div class="" style="float: right;">
				<img src="../../assets/wechat/Camaro.png" />
			</div>
		</div>
		<div class="space_min_img" v-on:click="add1()">
			<div class="space_font">
				<h4 id="" style="margin-right: 15px;float: left;">
            	德瑜
            </h4>
				<img src="../../assets/wechat/my_img.png" />
			</div>

		</div>
		<div class="" style="height: 30px;">

		</div>
		<div id="" class="space_topic">
			<div class="space_topic_img">
				<img src="../../assets/wechat/head1.png" />
			</div>
			<div class="" style="float: none;">
				<div class="space_topic_name">
					13 周澎杰
				</div>
				<div class="space_topic_content">
					朋友圈卖机票的吱一声呗~
				</div>
				<div class="" style="">
					<div class="space_topic_time">
						11分钟前
					</div>
					<div class="space_topic_icon">
						<img src="../../assets/wechat/topic.png" />
					</div>
				</div>
			</div>
			<div class="space_border">

			</div>
		</div>
		<div id="" class="space_topic">
			<div class="space_topic_img">
				<img src="../../assets/wechat/head1.png" />
			</div>
			<div class="" style="float: none;">
				<div class="space_topic_name">
					13 周澎杰
				</div>
				<div class="space_topic_content">
					朋友圈卖机票的吱一声呗~
				</div>
				<div class="" style="">
					<div class="space_topic_time">
						11分钟前
					</div>
					<div class="space_topic_icon">
						<img src="../../assets/wechat/topic.png" />
					</div>
				</div>
			</div>
			<div class="space_border">

			</div>
		</div>

    <div class='popContainer' v-show="top_add1" v-on:click="add1()"> <div><img src="../../assets/wechat/friend_space_img.png" alt=""></div></div>
    </div>
</template>
<script>
export default {
    data(){
        return{
          top_add1:false
        } 
    },
     methods:{
          add1:function(){
                	this.top_add1 = !this.top_add1
				},
		 comback(){
          this.$router.go(-1)
      }
		  	
		   
	   
    },
	
}
</script>
<style>
div.popContainer{
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background:rgba(46, 45, 45, 0.2)none repeat scroll !important; 
    text-align: center;
    padding-top: 50%;
}

			* {
				padding: 0px;
				margin: 0px;
				border: 0px;
			}
			
            .space{
                text-align: left
            }
			.space_headtop {
				background-color: transparent;
				background-size: auto;
				width: 100%;
				height: 30px;
				position: fixed;
				top: 0;
				/**距离底部为0*/
				left: 0;
				z-index: 1;
			}
			
			.space_min_img {
				background-image: url(../../assets/wechat/friend_img.png);
				height: 300px;
				width: 100%;
                margin-top: -60px
			}
			
			.space_font {
				float: right;
				margin-top: 270px;
				font-family: 宋体;
				color: white;
				margin-right: 20px;
			}
			
			.space_topic {
				margin-top: 20px;
				font-family: '黑体';
			}
			
			.space_topic_img {
				float: left;
				margin: 0px 10px 0px 10px;
			}
			
			.space_topic_name {
				color: #667493;
				font-size: 16px;
				font-family: '黑体';
				padding: 5px;
			}
			
			.space_topic_content {
				font-size: 16px;
				font-family: '黑体';
			}
			
			.space_topic_time {
				float: left;
				padding: 10px 0px 10px 0px;
				color: #7E7E7E;
				font-size: 13px;
			}
			
			.space_topic_icon {
				float: right;
				padding: 10px 0px 10px 0px;
			}
			
			.space_border {
				margin: 40px 0px 0px 0px;
				border-bottom: 2px solid #F9F9F9;
			}
</style>

