<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Scroll class="marquee_scroll" :scroll-list="scrollList"></Scroll>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Scroll from './components/scroll.vue'

export default {
  name: 'app',
  components: {
    // HelloWorld,
    Scroll
  },
  data(){
    return{
      scrollList:[{id:0,content:'绝地求生粉兔套装道具11'},
      {id:1,content:'绝地求套装道具2'},
      {id:2,content:'账号169*****0090的用户获得了'},
      {id:3,content:'绝地求生粉兔套装道具9'},
      {id:4,content:'账号169*****0090的用户获得了11'}]
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
.marquee_scroll li{
  color: #f00;
}
</style>
