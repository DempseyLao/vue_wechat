<template>
   	<div class="all">
			<div id="" class="head_st">
				<!--==头部导航信息-->
				<div class="" style="float: left;">
					<img src="../../assets/img/login/jingdong_logo.jpg" />
				</div>
				<div class="" style="float: right;">
					<img src="../../assets/img/login/new.jpg" />
				</div>
			</div>
			<!--网络安全法信息-->
			<div class="login_mid_content">
				<div class="login_mid_content_div2">{{msg}}</div>
			</div>
			<!--===中部登录-->
			<div id="" class="login_mi_lo">
				<div id="" style="" class="login_mi_lo_div2">
					<div class="" style="float: left;">
						<img src="../../assets/img/login/1_login.jpg" />
					</div>
					<div class="login_mi_lo_div2_chi2" style="float: right;">
						<div class="login_div_i" v-show="issho">
							<div id="">
								<img src="../../assets/img/login/login_head.jpg" />
							</div>
							<div class="login_div_smdd">
								<div class="Sweep_code_login"  v-bind:class="{'class-b':isB}" v-on:click="toggle()">
									<span id="" class="font_hover">
										扫码登录
									</span>
								</div>
								<div class="Account_entry" v-on:click="toggl()">
									<span id="Account" class="font_hover">
										账户登录
									</span>

								</div>

							</div>
                            <div v-show="input_rule"  style="font-size:6px;color:red;padding-top: 10px">只允許，大小写英文和数字!</div>
							<div class="External_login_height">
                                
								<div class="Input_area" v-bind:style="{ border: activeColor_accpunt}">
									
									<div id="">
                                        
                                        <div style="float: left;"><img src="../../assets/img/login/pe.png" /></div>
										<input v-model="account" placeholder="邮箱/用户名/已验证手机"  @blur="account_input"  class="Input_area_input"/>
									</div>
								</div>

								<div class="Input_area2" v-bind:style="{ border: activeColor_pwd}">
									
									<div id="" v-if="yes" >
                                        <div style="float: left;"><img src="../../assets/img/login/unc.png" /></div>
										<input v-model="pwd" type="password" placeholder="密码" @blur="validate" class="Input_area_input2"  />
                                         <div style="float: right;"  v-on:click="eys_close()"><img src="../../assets/img/login/c_eys.png" /></div>
									</div>
                                    <div id="" v-else >
                                        <div style="float: left;"><img src="../../assets/img/login/unc.png" /></div>
										<input v-model="pwd"  placeholder="密码" @blur="validate" class="Input_area_input2" />
                                         <div style="float: right;" v-on:click="eys_open()"><img src="../../assets/img/login/eys.png" /></div>
									</div>
                                   
								</div>

								<div class="Forget_password">
									忘记密码
								</div>
								<div class="login_button" id="login" v-on:click="login()">
									<img src="../../assets/img/login/dl.png" />
								</div>
							</div>
							<div id="" class="other">
								<div id="" style="float: left;">
									<img src="../../assets/img/login/qq.png" /><img src="../../assets/img/login/wx.png" />
								</div>
								<div id="" style="float: right;">
									<img src="../../assets/img/login/ljzc.png" />
								</div>
							</div>
						</div>
						<div v-show="isShow" class="login_div_i">
							<div id="">
								<img src="../../assets/img/login/login_head.jpg" />
							</div>
							<div class="login_div_smdd">
								<div class="Sweep_code_login" v-on:click="toggle()">
									<span id="Sweep_code" class="font_hover">
										扫码登录
									</span>

								</div>
								<div class="Account_entry" v-on:click="toggl()">
									<span id="" class="font_hover">
										账户登录
									</span>

								</div>

							</div>
							<div  class="External_login_height2">
								<div class="scan_QR_code" v-show="ewmshow">
									<img src="../../assets/img/login/ewm.png" />
								</div>
								<div class="scan_QR_code" v-on:click="ewm2()" v-show="ewmshow2">
									<img src="../../assets/img/login/ewm_sx.png" />
								</div>
								<div class="">
									<img src="../../assets/img/login/ewm_inf.png" />
								</div>
							</div>
							<div id="" class="other">
								<div id="" style="float: left;">
									<img src="../../assets/img/login/qq.png" /><img src="../../assets/img/login/wx.png" />
								</div>
								<div id="" style="float: right;">
									<img src="../../assets/img/login/ljzc.png" />
								</div>

							</div>
						</div>
					</div>
				</div>
			</div>
			<!--====底部信息-->
			<div class="login_foot" style="text-align: center;">
				<img src="../../assets/img/login/foot.jpg" />
			</div>
		</div>
</template>
<script>

 export default {
     
     data() {
            return {
              msg: '依据《网络安全法》，为保障您的账户安全和正常使用，请尽快完成手机号验证！ 新版《京东隐私政策》已上线，将更有利于保护您的个人隐私。',
              isShow: true,
			  issho: false,
			  ewmshow: true,
			  ewmshow2: false,
			  account: "",
              pwd: "",
              isB: true,
              Sweep_code_login:true,
              yes:true,
              activeColor_accpunt:"",
              activeColor_pwd:"",
              input_rule:false
            }
        },
        methods: {
            
					toggle() {
						this.isShow = true;
						this.issho = false;
						$("#Sweep_code").css("color", "orangered")
						$("#Sweep_code").css("font-weight", "bold");
					},
					toggl() {
						this.isShow = false;
						this.issho = true;
						$("#Account").css("color", "orangered")
						$("#Account").css("font-weight", "bold");
					},
					ewm() {
						this.ewmshow = false;
						this.ewmshow2 = true;

					},
					ewm2() {
						this.ewmshow = true;
						this.ewmshow2 = false;
					},
					login() {
                     if(this.pwd.length!=0){    
                     var reg=/^[a-zA-Z0-9_]+$/;     
                     if(!reg.test(this.pwd)||!reg.test(this.account)){    
                     alert("您输入有非法字符，請修改!");   
                     }
                     else{
                     if( this.account==1 &&  this.pwd==1) {
                            // alert("登录成功！")
                            this.$router.push({path:"/hello"})
						} else {
                       alert("登录失败~請檢查賬號密碼") ;
						}
                     }  
                    }
                    else{
                        alert("賬號密碼不能為空")
                    }
                    
                    },
                    validate(){
                     if(this.pwd.length!=0){    
                     var reg=/^[a-zA-Z0-9_]+$/;     
                     if(!reg.test(this.pwd)){    
                    console.log("对不起，您输入的字符串类型格式不正确!");
                     this.activeColor_pwd=" solid 1px red"
                     this.input_rule=true

                     }
                      else{
                        this.activeColor_pwd=" solid 1px #0DBC79"
                        this.input_rule=false
                     }      
                     }    
                    },
                    account_input(){
                      if(this.account.length!=0){    
                     var reg=/^[a-zA-Z0-9_]+$/;     
                     if(!reg.test(this.account)){    
                    console.log("对不起，您输入的字符串类型格式不正确!"); 
                        this.activeColor_accpunt=" solid 1px red"
                         this.input_rule=true
                     } 
                     else{
                        this.activeColor_accpunt=" solid 1px #0DBC79"
                        this.input_rule=false
                     }   
                     }     
                    },
                    eys_close(){
                       this.yes=false;
                    },
                    eys_open(){
                       this.yes=true; 
                    }

                    
                },
        mounted(){
        setTimeout(() => {
          this.ewm();
                }, 5000);
    }

                
}
$("#Sweep_code").css("color", "orangered")
$("#Sweep_code").css("font-weight", "bold");


//  var data2 = Mock.mock({
// 				'account|1': 1,
// 				'pwd|1': 1
//             });


</script>


<style>
input {
	outline: none;
}

.login_div_i {
	width: 350px;
	background-color: white;
}

.login_div_smdd {
	height: 50px;
	text-align: center;
	margin: 0 auto;
	font-size: 17px;
	border-bottom: solid 1px #F4F4F4;
}

.Sweep_code_login {
	float: left;
	width: 175px;
	padding-top: 10px;
	border-right: solid 1px #F4F4F4;
}

.font_hover:hover {
	color: orangered;
	font-weight: bold;
}

.Account_entry {
	padding-top: 10px;
}

.External_login_height {
	height: 225px;
}

.External_login_height2 {
	height: 265px;
}

.Input_area {
	border: solid 1px #BDBDBD;
	margin: 22px 22px 0px 22px;
}

.Input_area2 {
	border: solid 1px #BDBDBD;
	margin: 20px 22px 0px 22px;
}

.Input_area_input2 {
	height: 36px;
	border: none;
	width: 210px;
}
.Input_area_input {
	height: 36px;
	border: none;
	width: 252px;
}

.Forget_password {
	margin: 20px 20px 0px 20px;
	float: right;
	font-size: 12px;
}

.login_button {
	margin: 60px 20px 0px 22px;
	float: none;
}

.other {
	height: 50px;
	background-color: #FCFCFC;
}

.scan_QR_code {
	text-align: center;
	margin: 0 auto;
	padding-top: 20px;
}
.all {
	height: 700px;
}

.head_st {
	height: 82px;
	text-align: center;
	width: 1000px;
	margin: 0 auto;
}

.login_mid_content {
	width: 100%;
	height: 40px;
	text-align: center;
	background-color: #FFF8F0;
}

.login_mid_content_div2 {
	padding-top: 10px;
	font-size: 12px;
}

.login_mi_lo {
	background-color: #0251C8;
	height: 476px;
	
}

.login_mi_lo_div2 {
	text-align: center;
	margin: 0 auto;
	width: 1000px;
}

.login_mi_lo_div2_chi2 {
	height: 430px;
	padding-top: 20px;
}

.login_foot {
	text-align: center;
}


</style>


