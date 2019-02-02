<template>
  <div id="app">
    <Avatar :icons="['twitter','twitch','pinterest','youtube', 'spotify']"/>
  </div>
</template>

<script>
import Avatar from './components/Avatar/Avatar.vue'

export default {
  name: 'app',
  components: {
    Avatar
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
