<template>
  <div class="container-fluid p-3 header">
    <div class="row d-flex justify-content-between align-items-center p-2">
      <div class="col-3">
        <h1 class="fw-bold fs-3">BOOLFLIX</h1>
      </div>
      <div class="col-3">
        <input @keyup='resetSearch' v-model='inputText' type="text" placeholder="Serch a movie" class="">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data() {
      return {
        inputText: '',
      }
    },
  methods: {
    resetSearch() {
      this.$emit('userSerch', this.inputText);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .header {
    background-color: black;

     h1 {
    color: #E50914;
  }
  }
 
</style>
