<template>
  <div class="flip-card">
    <div class="text-center flip-card-inner">
      <div class="cover flip-card-front">
        <img :src="`https://image.tmdb.org/t/p/w300${info.poster_path}`" alt="Wtf?">
      </div>
      <div class="description flip-card-back text-light">
        <p class="fw-bold">{{ info.title }}</p>
        <p class="">{{ info.original_title }}</p>
        <div>Language: {{ info.original_language }}</div>
        <div>Vote: <span class="fw-bold">{{ info.vote_average }}</span></div>
        <div>Total Vote: {{ info.vote_count}}</div>
        <div><span class="fw-bold">Overview: </span>{{ info.overview }}</div>
      </div>
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

.flip-card {
  background-color: transparent;
  width: 300px;
  height: 600px;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-back {
  background-color: rgba(0,0,0,0.9);
  color: white;
  transform: rotateY(180deg);
  overflow-y: scroll;
}
</style>

