<template>
  <div id="app">
    <Header @userSerch="generateList"/>
    <Main :itemsListMain="itemsListApp" :seriesListMain="seriesListApp"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
    return {
      apiMovies: 'https://api.themoviedb.org/3/search/movie?api_key=3b70406fd45cbe88921bb08417d62a09&query=',
      apiSeries: 'https://api.themoviedb.org/3/search/tv?api_key=3b70406fd45cbe88921bb08417d62a09&query=',
      itemsListApp: [],
      seriesListApp: [],
      serched: ''
    }
  },
  
  methods: {
    generateList(string) {
      this.serched = string
      this.getItems()
      this.getSeries()
    },
    getItems() {
      axios
          .get(this.apiMovies + this.serched)
          .then( res => {
            // console.log(res.data);
            this.itemsListApp = res.data.results;
          })
          .catch( err => {
            console.log("Error ", err);
          })
    },
    getSeries() {
      axios
          .get(this.apiSeries + this.serched)
          .then( res => {
            // console.log(res.data);
            this.seriesListApp = res.data.results;
          })
          .catch( err => {
            console.log("Error ", err);
          })
    }  
  }
}
</script>

<style lang="scss">
@import "./styles/general.scss";
</style>
