<template>
  <!--<HelloWorld msg="Hello World!"/>-->
  <Nations />
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Nations from './components/Nations.vue';

export default {
  name: 'App',
  components: {
    //HelloWorld,
    Nations
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
