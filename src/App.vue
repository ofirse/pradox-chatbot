<template>
  <div id="app">
    <load-chat/>
  </div>
</template>

<script>
import LoadChat from './components/LoadChat.vue'

export default {
  name: 'App',
  components: {
    LoadChat
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
</style>
