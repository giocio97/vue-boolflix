<template>

<div>
    <input  type="text" placeholder="search"
     v-model="inputSearch" 
     @keyup.enter ="$emit(`UserSearch`, this.inputSearch)"/>
    <button @click.prevent="$emit(`UserSearch`, this.inputSearch)">VAI</button>
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
