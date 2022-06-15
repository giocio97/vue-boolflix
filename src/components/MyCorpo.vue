<template>
<main>

  <UserSearch @mySearch = "searchMovie"/>

     <section>
     
        <MyCard
        v-for="(item, index) in  filteredMovie"
        :key="index"
        :movieObjet="item"
        />
  </section>
</main>

 
</template>

<script>

import axios from "axios"
import MyCard from '@/components/MyCard.vue'
import UserSearch from './components/Search.vue'



export default {
  name: 'MyCorpo',
   components: {
    MyCard,
    UserSearch,
    
},
  data(){
    return{
        apiUrl:"https://api.themoviedb.org/3/search/movie?api_key=abd08d0dfd232b91ae3e260ac7989207&language=it-IT",
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
          .get(this.apiUrl)
          .then((result) => {
            this.myMovieList = result.data.results;
            console.log(result);
            console.log(this.myMovieList);
          })
          .catch((error)=> {
            console.log("errore", error);
          })
        }
       
   
    },

    searchMovie(filmUser){
       console.log(this.userText);
      this.userText = filmUser;

    }
  },
  computed:{
    filteredMovie(){
      if (this.userText === ""){
      return this.myMovieList;
      } else{
        return this. myMovieList.filter(item => {
          return item.title.toLowerCase().includes(this.userText.toLowerCase());
        
      });
      }
    },
  },
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
