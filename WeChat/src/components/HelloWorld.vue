<template>
  <div class="hello" style="text-align: center;">
    <h1 >{{ msg }}</h1>
    <h2>Dempsey Lao Test making</h2>
    <p>
     <div type="button" @click="gonnew" ><img src="../assets/img/login/jingdong_logo.jpg" /></div>
     <p>
   <div id=""  @click="WeChat" style="font-family: 黑体;text-align: center;">
			<div class="" style="display: inline-block;margin-left:9px">
			<div class="" style="float: left;">
				<img src="../assets/background.png" style="width:63px"/>
			</div>
			<div class="" style="float:left;font-size: 48px;font-weight:bold;color:#85DA46 ;padding-left: 7px;">
				微信
			</div>
			<div id="" style="padding: 13px 0px 0px 20px;font-size: 25px;float: left;">
				欢迎登陆
			</div>
			</div>
		</div>
     
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js WebApp'
    }
  }
  ,
    methods:{
     
         gonnew(){
            this.$router.push({path:"/hw"})
        }
        ,
        WeChat(){
            this.$router.push({path:"/wechat"})
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.bg-bubbles {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
}
ul,li {
    margin: 0;
    padding: 0;
}
.hello{
  text-align: center
}


</style>
