<template>
 
 <header>
  <img src="../assets/img/logobolflix.png" alt="logo">
  <UserSearch @mySearch = "searchMovie"/>
 </header>
</template>

<script>
import UserSearch from '@/components/UserSearch.vue'

export default {
   name: 'MyIntestazione',
   components: {
    
    UserSearch,
    
},  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header{
background-color: #000000;
height: 5vh;
display: flex;
justify-content:space-between;
padding: 5px;




}
</style>
