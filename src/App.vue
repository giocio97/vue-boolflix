<template>
  <div id="app">
  <MyIntestazione/>
   <MyCorpo/>
  </div>
</template>

<script>
import MyIntestazione from './components/MyIntestazione.vue'
import MyCorpo from './components/MyCorpo.vue'


export default {
  name: 'App',
  components: {
   MyIntestazione,
    MyCorpo
}
}
</script>

<style lang="scss">

// @import “../../../node_modules/@fortawesome/fontawesome-free/scss/fontawesome”;

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  
  
}
</style>
