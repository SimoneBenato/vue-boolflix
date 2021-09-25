<template>
  <div id="app">
    <Header @userSerch="generateList"/>
    <Main :itemsListMain="itemsListApp"/>
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
      APIUrl: 'https://api.themoviedb.org/3/search/movie?api_key=3b70406fd45cbe88921bb08417d62a09&query=',
      itemsListApp: [],
      serched: ''
    }
  },
  
  methods: {
    generateList(string) {
      this.serched = string
      this.getItems()
    },
    getItems() {
      axios
          .get(this.APIUrl + this.serched)
          .then( res => {
            // console.log(res.data);
            this.itemsListApp = res.data.results;
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
