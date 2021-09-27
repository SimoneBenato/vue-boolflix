<template>
  <div class="container-fluid main">
    <div class="container flex-wrap">
      <div class="row gy-3 d-flex">
        <div v-for="(item, index) in itemsListMain" :key="index"  class="col-3 card d-flex justify-content-end">
          <Item :key="index"  :info="item" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Item from '../components/Items.vue';


export default {
  props: {
    itemsListMain: Array
  },
  components: {
    Item
  },
  name: 'Main',
  data() {
    return {
      
      
      searchText: ''
    }
  },
  methods: {
   
     
  },
}
</script>


<style scoped lang="scss">
  .main {
    min-height: 100vh;
    background: rgb(0,0,0);
    background: linear-gradient(180deg, rgba(0,0,0,1) 0%, rgba(94,94,94,1) 100%);

    .card {
      background-color: transparent;
      border: transparent;
    }
  }
  
</style>
