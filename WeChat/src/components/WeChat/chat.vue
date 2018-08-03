<template>
   <div id="all" class="all_chat">
			<div class="head_top">
				<div class="" style="float: left;">
					<img src="../../assets/wechat/black_back.png" style="padding-top: 7px;" v-on:click="comback()" />
				</div>
				<div class="chat_title">
					{{chat_title}}
				</div>
				<div id="" style="float: right;">
					<img src="../../assets/wechat/more.png" style="padding-top: 10px;" />
				</div>
			</div>
             <contents></contents>
			<div class="foot_topic" v-show="foot_input">
				<div class="" style="height: 50px;">
					<div class="" style="float: left;width: 13%;" v-on:click="toc()">
						<img src="../../assets/wechat/say.png" style="padding-top: 7px;padding-left:0px" />
					</div>
					<div class="chat_input">
						<input type="" name="" id="" value="" class="input_sty" />
					</div>

					<div class="" style="float: right;width:100px;">
						<img src="../../assets/wechat/img_face.png" />
						<img src="../../assets/wechat/append_other.png" style="padding: 5px 10px 0px 5px;"   v-on:click="append_other()"/>
					</div>
				</div>
				<div class="chat_add_content" v-show="add_chat_com">
					<div class="out_div">
						<div class="out_div_1">
							<div class="spa_float">
								<img src="../../assets/wechat/c_img.png" />
							</div>
							<div class="spa_float">
								<img src="../../assets/wechat/c_p.png" />
							</div>
							<div class="spa_float">
								<img src="../../assets/wechat/c_s.png" />
							</div>
							<div class="spa_right">
								<img src="../../assets/wechat/c_w.png" />
							</div>
						</div>

						<div class="">
							<div class="spa_float">
								<img src="../../assets/wechat/c_h.png" />
							</div>
							<div class="spa_float">
								<img src="../../assets/wechat/c_z.png" />
							</div>
							<div class="spa_float">
								<img src="../../assets/wechat/c_y.png" />
							</div>
							<div class="spa_right">
								<img src="../../assets/wechat/c_m.png" />
							</div>
						</div>

					</div>

				</div>
			</div>
			<div class="foot_topic" style="height: 50px;" v-show="foot_say">
				<div class="" style="float: left;width: 12%;" v-on:click="input()">
					<img src="../../assets/wechat/append.png" style="padding: 6px 20px 0px 10px;" />
				</div>
				<div class="" style="width: 50%;float: left;margin-left: 20px;">
					<img src="../../assets/wechat/a_say.png" style="padding-top: 5px;" />
				</div>
				<div class="" style="float: right;width:calc(30%-20px);">
					<img src="../../assets/wechat/img_face.png" />
					<img src="../../assets/wechat/append_other.png" style="padding: 5px 10px 0px 5px;"  v-on:click="append_other()"/>
				</div>
			</div>
		</div>
</template>
<script>
import contents from './chat_content.vue'
export default {
    data(){
        return{
        chat_title:"",
        add_chat_com:false,
		foot_say:false,
		foot_input:true,
        } 
    },
    components: {
		 contents
    } ,
    mounted(){
      this.chat_title=this.$route.params.name
    }
    , methods:{
      comback(){
          this.$router.go(-1)
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
    beforeCreate: function() {
        document.getElementsByTagName("body")[0].className="all_chat";
    },
    beforeDestroy: function() {
        document.body.removeAttribute("class","all_chat");
	}
	
}

</script>
<style>
            * {
				padding: 0px;
				margin: 0px;
				border: 0px;
			}
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
			
			.foot_topic {
				text-align: end;
				border-top: 1px solid #DBDBDB;
				background-color: #F4F4F4;
				background-size: auto;
				width: 100%;
				position: fixed;
				bottom: 0;
				/**距离底部为0*/
				left: 0;
				z-index: 1;
			}
			
			.all_chat {
				background-attachment: fixed;
				background-color: #EBEBEB;
                
			}
			
			.chat_title {
				float: left;
				font-family: '黑体';
				font-size: 15px;
				color: white;
				padding-top: 16px;
			}
			
			.chat_input {
				border-bottom: 1px solid #DBDBDB;
				float: left;
				width: 57%;
			}
			
			.input_sty {
				height: 35px;
				padding-top: 7px;
				width: 100%;
				background-color: transparent;
				outline: none;
			}
			
			.chat_add_content {
				height: 240px;
				text-align: center;
				border-top: 1px solid #DBDBDB;
			}
			
			.out_div {
				padding: 0px 20px 0px 20px;
				height: 20px;
			}
			
			.out_div_1 {
				float: none;
				margin-bottom: 10px;
				width: 100%;
			}
			
			.spa_float {
				width: 25%;
				float: left;
			}
			
			.spa_right {
				width: 25%;
				float: right;
			}
</style>

