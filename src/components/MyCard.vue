<template>
 <div class="card">
  
    <img :src="`https://image.tmdb.org/t/p/w342/${movieObjet.poster_path}`" :alt="movieObjet.title">
      <div class="hovercard">
          <h4> Titolo: {{ movieObjet.title}}</h4>
         <span>Titolo originale: {{ movieObjet.original_title}}</span><br>
         <span> Lingua: <lang-flag :iso="movieObjet.original_language"/> </span><br>
         <span>voto: <i v-for=" i in starCalc(movieObjet.vote_average)" :key="i">  <font-awesome-icon  icon="fa-solid fa-star"/></i></span>
         <i v-for=" y in  starVuote(movieObjet.vote_average)" :key="y">  <font-awesome-icon icon="fa-regular fa-star" /></i>

      </div>
   
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
   
   // background-color: #2e3a46;
   color: white;
  
    img{
     
     &:hover{
      opacity: 0.5;
      
     };
     

   }

   .hovercard{
      
     
         &:hover{
         display: block;
         
      };
   }


   
   

   
  
   
}
</style>
