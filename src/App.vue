<template>
  <div id="app">
    <img src="https://imgur.com/KknoBJh.jpg" alt width="100%">
  
    <infinity/>
   <img src="https://imgur.com/uGIKDM6.png" alt width="100%">
    

  </div>
</template>

<script>
import infinity from './components/infinity.vue'

export default {
  name: 'App',
  components: {
    infinity
  }
}
</script>

<style>
#app {
  background-image: url(https://imgur.com/BFFEZMh.png);
  background-size: cover;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
</style>
