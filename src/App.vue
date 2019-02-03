<template>
  <div id="app">
    <Avatar :icons="['twitter','twitch', 'youtube', 'pinterest', 'spotify']" bg-image="https://ubisafe.org/images/circle-vector-avatar-3.png"/>
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
}
</style>
