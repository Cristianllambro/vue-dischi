<template>
  <div id="app">
    <header-content @genSearch="stringSearch" />
    <main-content :modSearch = strGenerate />
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
  },
  data () {
    return {
      strGenerate: '',
    }
  },
  methods: {
    stringSearch(element) {
      this.strGenerate = element;
      console.log(element)
    }
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';

</style>
