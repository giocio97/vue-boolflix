<template>

<div>
    <input  type="text" placeholder="search"
     v-model="inputSearch" 
     @keyup.enter ="$emit(`mySearch`, inputSearch)"/>
    
</div>
   



 
</template>

<script>



export default {
  name: 'UserSearch',
   
  data(){
    return{
     inputSearch: "",

    }
    
  },
  

   
    

  

 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
