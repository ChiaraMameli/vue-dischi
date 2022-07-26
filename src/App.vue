<template>
<div>
  <BaseHeader />
  <ContentSection />
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
  }
}
</script>

<style lang="scss">
@import './assets/sass/style.scss';
</style>
