<template>
  <div id="app">
    <hello></hello>
    <demo> </demo>
  </div>
</template>

<script>
import Hello from './components/Hello'
import demo from './components/transition1'

export default {
  name: 'app',
  components: {
    Hello,
    demo
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
