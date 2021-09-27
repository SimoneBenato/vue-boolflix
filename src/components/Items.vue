<template>
  <div class="text-center">
    <div class="cover">
      <img :src="`https://image.tmdb.org/t/p/w300${info.poster_path}`" alt="">
    </div>
    <div class="description">
      <h3 class="fw-bold fs-3">{{ info.title }}</h3>
      <h5 class="fs-5">{{ info.original_title }}</h5>
      <div>Language: {{ info.original_language }}</div>
      <div>Vote: <span class="fw-bold">{{ info.vote_average }}</span></div>
      <div>Total Vote: {{ info.vote_count}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Items',
  props: ['info']
}
</script>

<style scoped lang="scss">
.cover {
  height: 100%;
  width: 100%;

  img {
    width: 100%;
    height: 100%;
  }

}
.description {
  display: none;
}

img {
    &:hover {
      display: none;

    &:hover .description{
        display: block;
      }
    }
  }

</style>

