<template>
  <div id="app" class="pt-2 bg-dark">
    <MyList/>
  </div>
  
</template>

<script>
import MyList from './components/MyList.vue'

export default {
  name: 'App',
  components: {
    MyList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
}
</style>
