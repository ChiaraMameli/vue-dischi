<template>
<div>
  <BaseHeader :genres-list="genresList" @change-option="setSelectedGenre"/>
  <ContentSection :selected-genre="selectedGenre" @fetched-genres="setGenresList"/>
</div>
</template>

<script>
import BaseHeader from './components/BaseHeader.vue'
import ContentSection from './components/ContentSection.vue'
export default {
  name: 'App',
  components: {
    BaseHeader,
    ContentSection
  },
  data(){
    return{
      selectedGenre: '',
      genresList: [],
      }
  },
  methods: {
    setSelectedGenre(genre){
      this.selectedGenre = genre;
    },
    setGenresList(genres){
      this.genresList = genres;
    }
  }
}
</script>

<style lang="scss">
@import './assets/sass/style.scss';
</style>