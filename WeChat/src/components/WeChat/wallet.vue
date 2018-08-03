<template>
    <div id="all_wallet">
			<div class="wallet_top" >
				<div class="" style="float: left;" v-on:click="comback()">
					<img src="../../assets/wechat/back_t.png" style="padding-top: 9px;" />
				</div>
				<div class="wallet_chat_title">
					我的钱包
				</div>
				<div id="" style="float: right;">
					<img src="../../assets/wechat/s_more.png" class="wallet_s_more" />
				</div>
			</div>
			<div class="wallet_main">
				<div class="wallet_main_st">
					<div class="wallet_main_float">
						<img src="../../assets/wechat/Payment_of_payment.png" />
					</div>
					<div class="wallet_main_float">
						<img src="../../assets/wechat/Small_change.png" />
						<div class="wallet_main_font">
							¥100000000.30
						</div>
					</div>
					<div class="wallet_main_float">
						<img src="../../assets/wechat/Bank_card.png" />
					</div>
				</div>
			</div>
			<div id="" class="wallet_space">

			</div>
			<div class="wallet_cont_title">
				<div id="" style="padding: 13px 0px 0px 15px;">
					腾讯服务
				</div>
			</div>
			<div class="wallet_cont_div">
				<div class="wallet_cont_div_cid1">
					<img src="../../assets/wechat/wall_x.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid2">
					<img src="../../assets/wechat/wall_s.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid3">
					<img src="../../assets/wechat/wall_l.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid4">
					<img src="../../assets/wechat/wall_sh.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid5">
					<img src="../../assets/wechat/wall_q.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid6">
					<img src="../../assets/wechat/wall_c.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_last" >
					<img src="../../assets/wechat/wall_t.png" class="wallet_cont_img" />
				</div>
			</div>
			<div id="" class="wallet_space">

			</div>
			<div class="wallet_cont_title">
				<div id="" style="padding: 13px 0px 0px 15px;">
					第三方服务
				</div>
			</div>
			<div class="wallet_cont_div1">
				<div class="wallet_cont_div_cid1">
					<img src="../../assets/wechat/wall_h.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid2">
					<img src="../../assets/wechat/wall_d.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid3">
					<img src="../../assets/wechat/wall_j.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid4">
					<img src="../../assets/wechat/wall_m.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid5">
					<img src="../../assets/wechat/wall_dy.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid6">
					<img src="../../assets/wechat/wall_chwl.png"class="wallet_cont_img"/>
				</div>
				<div class="wallet_cont_div_cid4">
					<img src="../../assets/wechat/wall_jd.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid5">
					<img src="../../assets/wechat/wall_mb.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid6">
					<img src="../../assets/wechat/wall_mg.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_last">
					<img src="../../assets/wechat/wall_wph.png" class="wallet_cont_img" />
				</div>
				<div class="wallet_cont_div_cid5">
					<img src="../../assets/wechat/wall_zz.png" class="wallet_cont_img" />
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
				font-family: "黑体";
			}
			
		
			
			.wallet_top {
				background-color: #686F79;
				background-size: auto;
				width: 100%;
				height: 50px;
				position: fixed;
				top: 0;
				/**距离底部为0*/
				left: 0;
				z-index: 1;
			}
			
			.wallet_chat_title {
				float: left;
				font-family: '黑体';
				font-size: 17px;
				color: white;
				padding-top: 15px;
			}
			
			.wallet_s_more {
				padding-top: 10px;
				padding-right: 10px;
			}
			
			.wallet_main {
				height: 153px;
				background-color: #686F79;
				margin-top: -10px
			}
			
			.wallet_main_st {
				text-align: center;
				width: 100%;
				padding-top: 20px;
			}
			
			.wallet_main_float {
				float: left;
				width: 33%;
			}
			
			.wallet_main_font {
				font-size: 14px;
				color: #BFC2C6;
			}
			
			.wallet_space {
				background-color: #F0EFF4;
				height: 10px;
			}
			
			.wallet_cont_title {
				height: 40px;
				color: #5A595F;
				font-size: 15px;
                text-align: left
			}
			
			.wallet_cont_div {
				height: 348px;
				text-align: center;
			}
			
			.wallet_cont_div_cid1 {
				float: left;
				width: 32%;
				border: 1px solid #EDEDED;
				height: 115px;
				border-left: none;
			}
			
			.wallet_cont_img {
				padding-top: 20px;
			}
			
			.wallet_cont_div_cid2 {
				float: left;
				width: 33%;
				border: 1px solid #EDEDED;
				height: 115px;
				border-left: none;
			}
			
			.wallet_cont_div_cid3 {
				float: left;
				width: 33%;
				border: 1px solid #EDEDED;
				height: 115px;
				border-left: none;
				border-right: none;
			}
			
			.wallet_cont_div_cid4 {
				float: left;
				width: 32%;
				border: 1px solid #EDEDED;
				height: 115px;
				border-left: none;
				border-top: none;
			}
			
			.wallet_cont_div_cid5 {
				float: left;
				width: 33%;
				border: 1px solid #EDEDED;
				height: 115px;
				border-left: none;
				border-top: none;
			}
			
			.wallet_cont_div_cid6 {
				float: left;
				width: 33%;
				border: 1px solid #EDEDED;
				height: 115px;
				border-left: none;
				border-right: none;
				border-top: none;
			}
			
			.wallet_cont_div_last {
				float: left;
				width: 32%;
				border-right: 1px solid #EDEDED;
				height: 115px;
			}
			
			.wallet_cont_div1 {
				height: 465px;
				text-align: center;
			}
</style>


