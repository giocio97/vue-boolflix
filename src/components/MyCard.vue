<template>
 <div class="card">
  <ul>
    <li>{{ movieObjet.title}}</li>
    <li>{{ movieObjet.original_title}}</li>
    <li> <lang-flag :iso="movieObjet.original_language"/> </li>
    <li>{{ movieObjet.vote_average}}</li>


  </ul>
 </div>
 
</template>

<script>
import LangFlag from 'vue-lang-code-flags'

export default {
    name: "MyCard",
    props: {
        movieObjet: Object
    },
    components: { 
      LangFlag,
     }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card{
   
   flex-basis:calc(20% - 5px);
   text-align: center;
   
   background-color: #2e3a46;
   color: white;
   
   
   
//     img{
//       width: 160px;
     
//       object-fit: contain;
//       margin: 20px;
      
//    }

//    h4{
//       color: white;
//    }
//    span{
//       color: grey;
//    }
   
  
   
}
</style>
