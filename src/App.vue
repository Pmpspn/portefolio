<template>
  <Home/>
  <Content/>
</template>

<script>
import Home from './components/Home.vue'
import Content from './components/Content.vue'

export default {
  name: 'App',
  components: {
    Content,
    Home
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #161B33;
}
</style>
