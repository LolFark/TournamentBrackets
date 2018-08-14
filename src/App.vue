<template>
  <div id="app">
    <h1 class="Title">Player entry</h1>
    <img alt="Vue logo" src="./assets/logo.png">
    <Players></Players>
  </div>
</template>

<script>
import Players from './components/Players.vue'

export default {
  name: 'app',
  components: {
    Players
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
  .Title {
    font-size: 50px;
  }
</style>
