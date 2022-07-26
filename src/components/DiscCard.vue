<template>
  <div class="card">
    <img :src="disc.poster" :alt="disc.title">
    <h4>{{disc.title}}</h4>
    <div class="author">{{disc.author}}</div>
    <div class="release">{{disc.year}}</div>
  </div>
</template>

<script>
export default {
    name: 'DiscCard',
    props: {
      disc: Object,
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/vars';

.card {
    width: calc((100% / 5) - 20px);
    background-color: $light_blue;
    margin-bottom: 50px;
    padding: 20px;
    color: gray;
    text-align: center;

    img{
      max-width: 100%;
      height: auto;
    }

    h4 {
      color: #FFF;
      font-size: 1.2rem;
    }

    .author,
    h4 {
      margin: 1rem 0;
    }
}

</style>