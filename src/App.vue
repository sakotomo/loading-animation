<template>
  <div id="app">
    <Loading :loading="loading"/>
  </div>
</template>

<script>
import Loading from './components/Loading'

export default {
  data: function (){
    return {
      // If you want to stop loading animation, please change here -> loading:false
      loading:true
    }
  },
  name: 'App',
  components: {
    Loading
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
</style>
