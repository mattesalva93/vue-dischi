<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Header from './components/header.vue'
import Main from './components/main.vue'


export default {
  name: 'App',
  components: {
    Header,
    Main

    
  }
}
</script>

<style lang="scss">
@import './assets/style/globals.scss';

</style>
