<template>
  <div id="app">
<!--    <router-link to="/home">首页</router-link>-->
<!--    <router-link to="/about">关于</router-link>-->
<!--    <button @click="homeClick">首页</button>-->
<!--    <button @click="aboutClick">关于</button>-->
    <router-link to="/home">首页</router-link>
<!--    <router-link :to="'/login/'+ userId">用户</router-link>-->
<!--    <router-link :to="{path:'/profile',query:{name:'lyc',age:18,sex:'男'}}">档案</router-link>-->
    <router-link to="/about">关于</router-link>
    <button @click="userClick">用户</button>
    <button @click="profileClick">档案</button>
    <keep-alive exclude="Profile">
      <router-view />
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      userId:'lisi',
    }
  },
  methods:{
    // homeClick(){
    //   this.$router.replace('/home');
    // },
    // aboutClick(){
    //   this.$router.replace('/about');
    // }
    userClick(){
      this.$router.push('/login/' +this.userId)
    },
    profileClick(){
      this.$router.push({
        path:'/profile',
        query:{
          name:'lyc',
          age:18,
          sex:'男'
        }
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.active{
 color: #0069d9;
}
</style>
