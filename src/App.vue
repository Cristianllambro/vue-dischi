<template>
  <div id="app">
    <header-content />
    <main-content />
  </div>
</template>

<script>
import HeaderContent from './components/HeaderContent.vue'
import MainContent from './components/MainContent.vue'

export default {
  name: 'App',
  components: {
    HeaderContent,
    MainContent,
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';

</style>
