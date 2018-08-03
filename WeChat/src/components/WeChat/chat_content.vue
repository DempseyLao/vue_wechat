<template>
    <div class="" id="mDiv" >
    <div class="topic_chat_ri">
       <div class="box u-tri2">个则是的我只是个可爱的测试案列e</div><img src="static/friend/25.png" class="topic_chat_ri_con"/>
    </div>
    <div class="topic_chat_lef" >
    <div class="topic_chat_lef_div" >
    	<img src="static/friend/25.png" class="topic_chat_lef_cont"/><div class="box2 u-tri">nizahhhshs 哈哈哈哈哈哈我只是个则是的我只是个可爱的测试案列e</div>
    </div>
     </div>
     </div>
</template>
<script>
export default {
	name:'content',
    data(){
        return{
         
	
		
        } 
    },
   
     methods:{
     
		   
	   
	},
	mounted: function () {
  

  },
	
}

</script>
<style>
            
            * {
				margin: 0;
				padding: 0;
				font-family: "黑体";
			}
			
			.box {
				position: relative;
				display: inline-block;
				max-width: 200px;
				padding: 4px 8px;
				border-radius: 2px;
				background-color: #A0E759;
				line-height: 20px;
				font-size: 14px;
			}
			
			.box2 {
				position: relative;
				display: inline-block;
				max-width: 200px;
				padding: 4px 8px;
				border-radius: 2px;
				background-color: white;
				line-height: 20px;
				font-size: 14px;
			}
			
			.u-tri:before {
				position: absolute;
				left: -24px;
				top: 4px;
				content: '';
				border-top: 8px solid transparent;
				border-bottom: 8px solid transparent;
				border-left: 12px solid transparent;
				border-right: 12px solid white;
			}
			
			.u-tri2:before {
				position: absolute;
				right: -24px;
				top: 4px;
				content: '';
				border-top: 8px solid transparent;
				border-bottom: 8px solid transparent;
				border-right: 12px solid transparent;
				border-left: 12px solid #A0E759;
			}.topic_chat_ri {
				float: right;
				margin: 10px;
			}
			
			.topic_chat_ri_con {
				margin-left: 20px;
			}
			
			.topic_chat_lef {
				margin: 10px;
				float: left;
			}
			
			.topic_chat_lef_div {
				margin-right: 10px;
			}
			
			.topic_chat_lef_cont {
				margin-right: 20px;
				padding-bottom: 20px;
			}
</style>

