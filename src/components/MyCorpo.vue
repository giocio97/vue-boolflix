<template>
<main>

    <UserSearch @mySearch = "searchMovie"/>

     <section>
     
        <MyCard
        v-for="(item, index) in myMovieList "
        :key="index"
        :movieObjet="item"
        />
  </section>
</main>

 
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
        apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=abd08d0dfd232b91ae3e260ac7989207&language=it-IT&page=1&include_adult=false",
       


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
main{
  background-color: #1e2d3b;
  text-align: center;
   height: calc(100vh - 5vh);
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
