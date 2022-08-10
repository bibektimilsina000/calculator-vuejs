<template>
  <mainComp />
</template>

<script>
import mainComp from './components/mainComp.vue'
import '@/assets/tailwind.css';

export default {
  name: 'App',
  components: {
    mainComp
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
