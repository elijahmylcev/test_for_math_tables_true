<template>
  <General />
</template>

<script>
import General from './components/general.vue'

export default {
  name: 'App',
  components: {
    General
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
  padding: 0 40px;
}

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
</style>
