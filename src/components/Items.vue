<template>
  <div class="text-center">
    <h3 class="fw-bold fs-3">{{ info.title }}</h3>
    <h5 class="fs-5">{{ info.original_title }}</h5>
    <div>Language: {{ info.original_language }}</div>
    <div>Vote: <span class="fw-bold">{{ info.vote_average }}</span></div>
    <div>Total Vote: {{ info.vote_count}}</div>
  </div>
</template>

<script>
export default {
  name: 'Items',
  props: ['info']
}
</script>

poster_path
<style scoped lang="scss">

</style>

