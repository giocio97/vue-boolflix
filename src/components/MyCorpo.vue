<template>
<div>
  <header>
  <img src="../assets/img/logobolflix.png" alt="logo">
  <UserSearch @mySearch = "searchMovie"/>
 </header>

<main>



     <section>
     
        <MyCard
        v-for="(item, index) in myMovieList "
        :key="index"
        :movieObjet="item"
        />
  </section>
</main>

</div>
 
</template>

<script>

import axios from "axios"
import MyCard from '@/components/MyCard.vue'
import UserSearch from '@/components/UserSearch.vue'



export default {
  name: 'MyCorpo',
   components: {
    MyCard,
    UserSearch,
    
},
  data(){
    return{
        apiUrl: "https://api.themoviedb.org/3/search/multi?api_key=abd08d0dfd232b91ae3e260ac7989207&language=it-IT&page=1&include_adult=false",
       


        myMovieList: [],
        userText: "",
    }
  },

  created(){
    this.getMovie();
  },

  methods:{
    getMovie(){
       

        if(this.userText !== ""){

          let currentUrl =this.apiUrl + "&query=" + this.userText;
          console.log(1,currentUrl);
           axios
          .get(currentUrl)
          .then((result) => {
            this.myMovieList = result.data.results;
            console.log(2,result);
            console.log(3,this.myMovieList);
          })
          .catch((error)=> {
            console.log("errore", error);
          })
        }
       
   
    },

    searchMovie(filmUser){
       console.log(4,this.userText);
      this.userText = filmUser;
      this.getMovie();


    }
  }
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header{
background-color: #000000;
height: 5vh;
display: flex;
justify-content:space-between;
padding: 10px;




}

main{
  background-color: #313234;
  text-align: center;
   min-height: 95vh;
  
   
  section{
   
    
    display: flex;
   justify-content: center;
   justify-items: flex-start;
    flex-wrap: wrap;
    padding: 30px;
    gap: 5px;
     
}
}
</style>
