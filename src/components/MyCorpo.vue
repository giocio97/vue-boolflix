<template>
<main>

  <!-- <SelectGenere @mySearch = "searchGenere"/> -->

     <section>
     
        <Card
        v-for="(item, index) in myMovieList"
        :key="index"
        :movieObjet="item"
        />
  </section>
</main>

 
</template>

<script>

import axios from "axios"
import Card from '@/components/Card.vue'


export default {
  name: 'MyCorpo',
   components: {
    Card,
    
},
  data(){
    return{
        apiUrl:"https://api.themoviedb.org/3/search/movie?api_key=abd08d0dfd232b91ae3e260ac7989207&language=it-IT&query=una + notte + da + leoni &page=1&include_adult=true",
        myMovieList: [],
        userText: "",
    }
  },

  created(){
    this.Movie();
  },

  methods:{
    getMovie(){
        axios
        .get(this.apiUrl)
        .then((result) => {
        this.myMovieList = result.data.results;
        console.log(result);
        console.log(this.myMovieList);
       
    })
    },

    searchGenere(filmUser){
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
          return item.original_title.toLowerCase().includes(this.userText.toLowerCase());
        
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
