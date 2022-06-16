<template>
  <div id="app">
  
   <MyCorpo/>
  </div>
</template>

<script>


import MyCorpo from './components/MyCorpo.vue'


export default {
  name: 'App',
  components: {
   
    MyCorpo
}
}
</script>

<style lang="scss">


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
