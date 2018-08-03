<template>
    <div class="search" >
        <div style="margin-top:-60px"></div>
			<div class="" style="width: 100%;">
				<div class="search_back" >
					<img src="../../assets/wechat/back.png"  v-on:click="comback()" />
				</div>
				<div class="search_input">
					<input type="" name="" id="" value="" placeholder="搜索"/>
				</div>
				<div class="search_record" >
					<img src="../../assets/wechat/record.png" />
				</div>
				<div class="search_bottom" >
					
					</div>
             
				</div>
				<center >搜索指定内容</center>
				<div class="search_font" >
					<div class="search_font_style" >
						朋友圈
					</div>
					<div class="search_font_style1">
						文章
					</div>
					<div class="search_font_style">
						公众号
					</div>
					<div class="search_font_style">
						小说
					</div>
					<div class="search_font_style1">
						音乐
					</div>
					<div class="search_font_style">
						表情
					</div>
				</div>
				</div>
</template>
<script>
export default {
    data(){
        return{
        } 
    },
 
     methods:{
      comback(){
          this.$router.go(-1)
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
			
			input {
				outline: none;
				background-color: transparent;height: 35px;width: 100%;
                font-family:黑体;font-size:15px;
			}
			.search{
				height: 750px;background-color: #F2F2F2;
			}
			.search_back{
				float: left;padding-top: 8px;width: 6%;
			}
			.search_input{
				float: left;padding-top: 5px;width: 70%;margin-left: 8%;
			}
			.search_record{
				float: right;padding-top: 8px;padding-right: 5px
			}
			.search_bottom{
				margin: 0px 5px 0px 10px;border-bottom:1px solid  #71B25A;padding-top: 38px;float: none;
			}
			center{
				margin:60px 0px 30px 0px ;font-family: 黑体;font-size: 14px;color: #B5B5B5;
			}
			.search_font{
				width: 100%;text-align: center;color:#42AF3F;font-family:黑体;font-size: 14px;
			}
			.search_font_style{
				width: 32%;float: left;margin: 10px 0px 20px 0px;
			}
			.search_font_style1{
				width: 33%;float: left;margin: 10px 0px 20px 0px;border-right: 1px solid #E8E8E8;border-left: 1px solid #E8E8E8;
			}
            
</style>



