<template>
  <div id="app">
    <Avatar :icons="icons" :bg-image="url" :duration="duration"/>
  </div>
</template>

<script>
import Avatar from './components/Avatar/Avatar.vue'

export default {
  name: 'app',
  components: {
    Avatar
  },
  data() {
    return {
      url: 'https://ubisafe.org/images/circle-vector-avatar-3.png',
      duration: 5, // seconds
      icons: ['twitter','twitch', 'youtube', 'pinterest', 'spotify']
    }
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
