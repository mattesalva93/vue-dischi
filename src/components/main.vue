<template>
  <main>
    <div class="container p-5">
      <div class="row">
        <filter-select 
        @filtra="getFilter"
        :listageneri="listaGeneri"
        />
      </div>
      <div v-if="!loading" class="row row-cols-5">
        <disco-singolo
         v-for="(element, index) in genereFiltrato"
         :key="index"
         :disco="element" />
      </div>
      <div v-else class="row row-cols-5">
        <div class="col-12 d-flex justify-content-center align-items-center">
          loading...
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import discoSingolo from './sub-components/Disco-singolo.vue'
import filterSelect from './sub-components/Filter-select.vue';
import axios from 'axios';

export default {
  name: 'Main',
  components: { 
    discoSingolo,
    filterSelect,
    },
  data(){
    return{
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      dischiArray: [],
      genereSelezionato: "",
      loading: true,
    }
  },
  created(){
    this.getDischi();
  }, 
  computed: {
    listaGeneri(){
      const generiFiltrati = [];
      this.dischiArray.forEach(element => {
        if(!generiFiltrati.includes(element.genre))
        generiFiltrati.push(element.genre);
      });
      return generiFiltrati;

    },
    genereFiltrato(){
      return this.dischiArray.filter( (element) => {
        return element.genre.includes(this.genereSelezionato);
      });
    },
  },
  methods: {
    getDischi(){
        axios
            .get(this.apiUrl)
            .then( (risposta) => {
                // handle success
                this.dischiArray = risposta.data.response;
                this.loading = false;
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            ;
        },
    getFilter(genreSelected){
        this.genereSelezionato = genreSelected;
        console.log(this.genereSelezionato);
    },
    }
}

</script>

<style lang="scss" scoped>
@import '../assets/style/globals.scss';
main{
  background-color: $spotifybackgroundcolor;
}
</style>