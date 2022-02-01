<template>
  <main>
    <div class="container p-5">
      <div class="row">
        <genre-select 
        @filtra="getGenre"
        />
      </div>
      <div class="row row-cols-5">
        <disco-singolo
         v-for="(element, index) in genereFiltrato"
         :key="index"
         :disco="element" />

      </div>
    </div>
  </main>
</template>

<script>
import discoSingolo from './sub-components/Disco-singolo.vue'
import GenreSelect from './sub-components/Genre-select.vue';
import axios from 'axios';

export default {
  name: 'Main',
  components: { 
    discoSingolo,
    GenreSelect 
    },
  data(){
    return{
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      dischiArray: [],
      genereSelezionato: "",
    }
  },
  created(){
    this.getDischi();
  }, 
  computed: {
    genereFiltrato(){
      return this.dischiArray.filter( (element) => {
        return element.genre.includes(this.genereSelezionato);
      });
    }
  },
  methods: {
    getDischi(){
        axios
            .get(this.apiUrl)
            .then( (risposta) => {
                // handle success
                this.dischiArray = risposta.data.response;
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            ;
        },
    getGenre(genreSelected){
      this.genereSelezionato = genreSelected;
      console.log(this.genereSelezionato);
    }
    }
}

</script>

<style lang="scss" scoped>
@import '../assets/style/globals.scss';
main{
  background-color: $spotifybackgroundcolor;
}
</style>