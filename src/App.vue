<template>
  <div id="app">
    <songNowPlaying/>
  </div>
</template>

<script>
import songNowPlaying from './components/songNowPlaying.vue';

export default {
  name: 'App',
  components: {
    songNowPlaying
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  text-align: center;
}
</style>
