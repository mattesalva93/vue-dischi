<template>
  <main>
    <div class="container p-5">
      <div class="row row-cols-5">
        <disco-singolo />
        <disco-singolo />
        <disco-singolo />
        <disco-singolo />
        <disco-singolo />
        <disco-singolo />
        <disco-singolo />
        <disco-singolo />
        <disco-singolo />
      </div>
    </div>
  </main>
</template>

<script>
import discoSingolo from './sub-components/Disco-singolo.vue'
export default {
  name: 'Main',
  components: { 
    discoSingolo 
    },
}
</script>

<style lang="scss" scoped>
@import '../assets/style/globals.scss';
main{
  background-color: $spotifybackgroundcolor;
}
</style>