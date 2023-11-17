<template>
  <button>숫자 세기: {{ count }}</button>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import nice_p01 from './components/nice.vue'

export default {
  name: 'App',
  components: {
    nice_p01,
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
