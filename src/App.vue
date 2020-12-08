<template>
  <div id="app">
    <Header theTitle="Popular TV Shows"/>
    <Card v-bind:cardList="cards"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Card from './components/Card.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Card
  }
,
  data(){
    return {
      cards:[
        {id:1, title: "Title 1", completed:false},
        {id:2, title: "Title 2", completed:true},
        {id:3, title: "Title 3", completed:false},
        {id:4, title: "Title 4", completed:true}
      ]
    }
  },
  mounted(){
    axios.get('https://api.themoviedb.org/3/tv/popular?api_key=8cec4250eceaead9d513647b6d319b88&language=en-US&page=1')
    .then((res) =>{
      this.cards = res.data.results.slice(0,4);
    })
  }
}
</script>

<style>
#app {
  * {
    margin: 0;
    padding: 0;
  }
}
</style>
