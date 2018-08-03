<template>
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

 
 
</template>
<script>

import bottomComponent from './Bottom.vue'
import headComponent from './head_top.vue'
var a=false;
export default {
	name:'index',
    data(){
        return{
		 
		 Small_program:false,
		 account: [],
		 msg:"wechat_index"
        }
       
	},
	 created:function(){     
                
        }   
	,
	 components: {
	  bottomComponent,
	  headComponent
	},
    methods:{

       Small_program_open(val_name,index){
			this.Small_program=false;
			a=false;
			console.log(index);
			console.log(val_name)
			this.$router.push({
                        path: '/chat',
                        name: 'chat',
                        params: {
                            name: val_name,
                            dataObj: this.msg
						}
			})
		   
	   }
	},
	created(){
            this.$http.get('https://www.easy-mock.com/mock/5b5a9004e51b9b054104fa4a/account',{
            }).then(function(data){
				this.account=data.body.account;
				
            },function(res){
                console.log(res.status);
            })     
        },
    mounted(){ 
		
	setInterval(() => {
         if(a==true){
			
	  this.Small_program=true;
	  
	}	
	else{
		 this.Small_program=false;
	} 
                 }, 100);
	
    var startx, starty;
    //获得角度
    function getAngle(angx, angy) {
        return Math.atan2(angy, angx) * 180 / Math.PI;
    };
 
    //根据起点终点返回方向 1向上 2向下 3向左 4向右 0未滑动
    function getDirection(startx, starty, endx, endy) {
        var angx = endx - startx;
        var angy = endy - starty;
        var result = 0;
 
        //如果滑动距离太短
        if (Math.abs(angx) < 2 && Math.abs(angy) < 2) {
            return result;
        }
 
        var angle = getAngle(angx, angy);
        if (angle >= -135 && angle <= -45) {
            result = 1;
        } else if (angle > 45 && angle < 135) {
            result = 2;
        } else if ((angle >= 135 && angle <= 180) || (angle >= -180 && angle < -135)) {
            result = 3;
        } else if (angle >= -45 && angle <= 45) {
            result = 4;
        }
 
        return result;
    }
    //手指接触屏幕
    document.addEventListener("touchstart", function(e) {
        startx = e.touches[0].pageX;
        starty = e.touches[0].pageY;
    }, false);
    //手指离开屏幕
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
	
	}
}


 


</script>
<style>
*{
 	padding:0px;
 	margin:0px;
	 
 	border:0px;
 }	
		.Small_program {
			height: 160px;
			background-color: #E5E5E5;
			width: 100%;
			margin-top:-10px;
			
		}
		
		.Small_program div {
			
			padding-top: 35px;
			width: 25%;
			float: left;
		}
		
		.con_out {
			height: 60px;
			border-bottom: 1px solid #ECECEF;
		}
		
		.margin_div {
			margin: 10px 14px 10px 14px;
		}
		
		.left_img {
			float: left;
			margin-right: 14px;
		}
		.mid_con{
			font-family: 黑体;float: left;
		}
		.mid_con_div1{
			padding-top: 3px;color: black;text-align: left
		}
        .mid_con_div2{
        	font-size: 13px;color: #9F9FA0;padding-top: 7px;float: left;
        }
        .right_time{
        	float: right;font-size: 11px;color: #9F9FA0;padding-top: 3px;
        }

</style>
