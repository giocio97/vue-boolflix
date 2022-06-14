<template>
 <div class="card">
  <ul>
    <li>{{title}}</li>
    <li>{{original_title}}</li>
    <li>{{original_language}}</li>
    <li>{{vote_average}}</li>


  </ul>
 </div>
 
</template>

<script>
export default {
   name: 'Card',
   props:{
    movieObjet:Object
   } 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card{
   
   flex-basis:calc(20% - 5px);
   text-align: center;
   
   background-color: #2e3a46;
   
   
   
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
