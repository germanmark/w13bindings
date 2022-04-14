<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <ParentComp/>

  </div>
</template>

<script>
import ParentComp from '@/components/nested/ParentComp.vue'

export default {
  name: 'App',
  components: {
    ParentComp
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
  margin-top: 60px;
}

*{
  background-color: bisque;
}
</style>
