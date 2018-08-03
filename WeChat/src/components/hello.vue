<template>
    <div>
      
        <button type="button" @click="goHome">回到首页</button>
        <button type="button" @click="gonnew">登陆页面</button>
        <button type="button" @click="WeChat">微信页面</button>
        <button type="button" @click="test">测试页面</button>
    </div>
</template>
<script>
export default {
    name:"hello",
    data(){
        return {
            msg:"hello world!"
        }
    },
    mounted(){

    },
    methods:{
        goHome(){
            this.$router.push({path:"/"})
        },
        gonnew(){
            this.$router.push({path:"/hw"})
        }
        ,
        WeChat(){
            this.$router.push({path:"/wechat"})
        },
        test(){
            this.$router.push({path:"/test"})
        }
    }
}
</script>

