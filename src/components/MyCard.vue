<template>
 <div class="card">
  
    <img :src="`https://image.tmdb.org/t/p/w342/${movieObjet.poster_path}`" :alt="movieObjet.title">
    <h4>{{ movieObjet.title}}</h4>
    <span>{{ movieObjet.original_title}}</span><br>
    <span> <lang-flag :iso="movieObjet.original_language"/> </span><br>
    <i v-for="i in starCalc(movieObjet.vote_average)" :key="i"> <font-awesome-icon  icon="fa-solid fa-star"/></i>
   
    <!-- <span>{{ movieObjet.vote_average}}</span> -->


  
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
     },
     methods:{
      starCalc(vote){
        let calc = parseInt(Math.round(vote/ 2));
        return calc;
      },
      starVuote(vuote){
      let stelleVuote =  parseInt(5 - Math.round(vuote/ 2));
      return stelleVuote;
      },

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
