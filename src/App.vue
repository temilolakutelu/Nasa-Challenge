<template>
  <TopHeader />
  <MainContent />
</template>

<script> 
import TopHeader from './components/Header.vue'
import MainContent from './components/Content.vue'

export default {
  name: 'App',
  components: {
    TopHeader, MainContent
  }
}
</script>

<style>
</style>
