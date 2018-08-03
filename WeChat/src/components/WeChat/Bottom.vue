<template>
    <div class="navdown">
			<div id="menu">
				<div v-on:click="wx_btn()">
					<img src="../../assets/wechat/wc_btn1.png" v-if="linbtn"/>
                    <img src="../../assets/wechat/wc_btn.png" v-else/>
				</div>
				<div v-on:click="wx_lin()">
					<img src="../../assets/wechat/wc_lin.png"  v-if="linshow"/>
                    <img src="../../assets/wechat/wc_lin1.png" v-else />
				</div>
				<div v-on:click="wx_find()">
					<img src="../../assets/wechat/wc_find.png" v-if="linfind"/>
                    <img src="../../assets/wechat/wc_find1.png" v-else/>
				</div>
				<div  v-on:click="wx_my()">
					<img src="../../assets/wechat/wc_my.png" v-if="linmy"/>
                    <img src="../../assets/wechat/wc_my1.png"  v-else/>
				</div>
			</div>
		</div>
</template>
<script>
var href=0;
export default {
     name:"bottom",
    data(){
        return {
           linbtn:true,
           linshow:true,
           linfind:true,
           linmy:true
        }
    },
    mounted(){
     if(href==1){
        this.linshow=false
          
     }
     if(href==2){
          
          this.linbtn=false
     }
     if(href==3){
          
          this.linfind=false
     }
     if(href==4){
          
          this.linmy=false
     }
    if(href==0){
          
          this.linbtn=false
     }
    },
    methods:{
    wx_lin(){
   
    this.$router.push({path:"/mail"})
    href=1
    },
    wx_btn(){
    
    this.$router.push({path:"/wechat"})
    href=2
    },
    wx_find(){
   
    this.$router.push({path:"/find"})
     href=3
    },
    wx_my(){
     this.$router.push({path:"/my"})
     href=4
    },  
    }
}
</script>
<style>
	.navdown {
			background-color: #FCFCFC;
			background-size: auto;
			width: 100%;
			height: 60px;
			position: fixed;
			bottom: 0;
			/**距离底部为0*/
			left: 0;
			z-index: 1;
		}
		
		#menu div {
			width: 25%;
			float: left;
		}
</style>



